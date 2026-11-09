---
layout: post
title:  "coinfs: host Filecoin data for money, together"
date:   2026-11-09 16:00:00 +0000
categories: software filecoin
---
{% include analytics.html %}

Filecoin pays storage providers in USDFC for keeping data and proving, every day, that they still have it. A storage provider is normally a data centre with sealed sectors and a team on call. A laptop with 200 GB free is not one: it reboots, it moves house, it gets forgotten in a drawer.

[coinfs](https://github.com/mrmartin/coin_filesystem) is an open-source pool that turns many such machines into one provider. Anyone with at least 100 GB of free disk and a 100 Mbit connection runs a small daemon and joins. The pool stores Filecoin pieces across its members and splits the pool's income among them, weighted by how much each one stored and how reliably.

## How it works

A **gateway** is the pool operator. To Filecoin it looks like an ordinary PDP storage provider: it speaks the provider HTTP API that Filecoin Onchain Cloud clients use, and it answers the chain's possession challenges. Inside, it keeps only metadata in one SQLite file. Every piece a client uploads is

1. encrypted with a per-piece key derived from the pool key, so members only ever hold ciphertext,
2. Reed–Solomon coded 10-of-16, and
3. placed as 16 shards on 16 different members, spread across subnets.

Any 10 shards reconstruct any byte range, so six members can be gone at once and nothing is lost. Members are audited continuously: the gateway asks for a random 64 KiB leaf of a shard plus its Merkle path, so a member cannot keep hashes and throw away the data.

## When a member disappears

The interesting part is that nobody in a pool like this promises to stay. Three things happen to members, and all three are handled by default:

- **Gone for a while** (reboot, ISP outage, lid closed). After three missed heartbeats the member is *unreachable*: reads route around it by reconstruction and no repair starts, because repair costs everyone bandwidth and the member will probably be back. After six hours it is *offline* and its shards are lazily rebuilt elsewhere. When it returns, a burst of audits re-verifies what it holds, the outage is recorded against its uptime, and shards the pool has since rebuilt are pruned from its disk.
- **Gone for good, politely** (`coinfs node leave`). The member stops receiving new shards, every shard it holds is copied to a healthy member, and it is told when it may shut down. It is paid its full balance at the next settlement.
- **Gone for good, silently** (disk died, walked away). After seven days offline the member is declared *dead*. Its unsettled balance is forfeited and a penalty equal to the pool's repair cost is booked against its public key, so coming back under the same identity does not start with a clean slate.

If several holders of one piece vanish together and fewer than twelve shards are online, repair of that piece starts immediately rather than waiting out the grace period.

## Reliability is tracked, not assumed

Each member has a public record: uptime over 1, 7 and 30 days, audit pass rate and latency, outages, deaths, announced leaves, and a score that scales its earnings. The pool as a whole reports pieces by health, availability, repair backlog and mean time to repair, audit pass rate, incident counts, and an estimated durability derived from the observed member failure rate and observed repair time. All of it is JSON and Prometheus metrics, or `coinfs pool status` on the command line.

## Tested the only way that counts

The test suite starts a gateway and ten members in one process and walks through every lifecycle above, then checks the bytes. A second script does the same with real processes and 200 MB of random data: one member is frozen with `SIGSTOP` and the data is read back through reconstruction; another announces it is leaving and its shard is copied away before it is released and paid; a third is killed with `kill -9` and never returns, its shard is rebuilt from the survivors, and it is declared dead with its balance forfeited. Possession proofs are submitted and accepted throughout, income is distributed each epoch, and the final payouts balance to the micro-USDFC.

## What it is not, yet

All of this runs against a built-in simulation of the Filecoin contracts. The mainnet adapter can read the chain but does not yet sign transactions, and a pool would still need to register as a provider and pass Filecoin's approval monitor, which demands a fault rate under 1% and a 30-minute proving window every day. Those steps, and what they cost, are written up in the repository's README. At today's fixed price of 2.5 USDFC per TiB per month, a member offering 100 GB would earn cents. The pool will distribute whatever it earns faithfully; whether that is worth a daemon on your laptop is a question for the market.

Code and design: <https://github.com/mrmartin/coin_filesystem>, MIT licensed.
