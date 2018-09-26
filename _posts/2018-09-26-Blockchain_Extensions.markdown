---
layout: post
title:  "Blockchain Extensions"
date:   2018-09-26 09:54:30 +0100
categories: science math
---
{% include analytics.html %}

The blockchain is an incredible system: a unified ledger of verified transactions based on anonymous computations. With the opportunities this creates, there are also downsides, which in turn lead to ideas for improvement. Below are three ideas on how the blockchain could be extended which I haven't seen elsewhere.

# A cryptocurrency where transactions are verified by the buyer and seller directly

A pitfall of bitcoin is the length of time it takes to verify a transaction, often causing me to wait in the pub and get another drink long after I've paid. Wouldn't it be great if we could simply use the public-private key pair to validate transactions directly on the transaction device? But the valuable de-centralization of cryptocurrencies comes at a cost: majority voting. If there isn't a commong ledger, how does the recipient know that the coin hasn't been spent already?

What if the buyer and seller created a public key referring to their transaction? What if the transaction was uploaded to the block in a tree-like fashion, reaching all verifiers in logarithmic rather than linear time? What if the transaction rested with a minor centralized authority (like a bank), accepted by both parties after a single communication with that authority, and being pushed over the slower blockchain by the authority later, at a premium? I don't know the solution yet, but handing confirmations without waiting for blocks would make cryptocurrency a lot more usable.

This would resolve the second problem which comes with confirmation by blocks: transaction cost. If the transaction is quickly performed and confirmed by the parties performing it, there is a reduced requirement for the common ledger, so the transaction cost will go down.

# A cryptocurrency computing a useful program instead of hashes

1% of the world's electricity goes into calculating 50 billion billion hashes per second[1](#power). By comparing apples to oranges we can say estimate equivalence to 100 billion billion floating point operations per second, or 100'000 petaflops, compared to 200 petaflops for the world's currenly most powerful supercomputer, which someone was willing to pay 300 million dollars to put together. Wouldn't it be neat to make use of the computational power of 5'000 such computers for something beneficial to us all?

One way of doing this is to create a central authority which distributes the problems, someone like [iana](https://www.iana.org/), but for computational resources. We could distribute programs that fold proteins, simulate the big bang, or reconstruct veins in the human body, and require their computation to verify the ledger.

Hashes are being used now in much the same way: the blockchain defines a problem in terms of resulting hash properties. Computing a hash with that property can only be done with a lot of work, but verifying the result is easy. Hashes are used because they are complicated to compute, and the operation is irreversible. But many other problems can be formulated the same way: this is the core theory of P vs NP. So if the central authority published the polynomial-time code to verify a solution for a given input, the solution could be computed by the blockchain, and easily verified by all parties. The solver would get the reward, and the result would get concatenated and hased with the ledger.

If we can only agree on a way to do this, the world's smartest computer engineers would be working together to compute hard science for the benefit of mankind.

# A cryptocurrency computing generic programs for money

Just as in the second idea, this addresses the waste of computational resources that goes into calculating hashes. But here, let's consider a more de-centralized perspective, and one that generates profit.

It's AWS on the blockchain. Instead of getting pittance for mining new coins and performing transactions, the miners would perform arbitrary computation for a sizeable fee. For this idea too, the numbers are very much in the favour: Paople pay Amazon 0.1$ per hour per GPU, about the same as miners get for running a GPU at home, so transforming the blockchain to perform useful computations would double the miners' revenue.

Just as anyone can send transactions into the bitcoin framework, programs which follow strict rules would be uploaded, together with a reward. Miners would try them, and the one succeeding would get the payoff. The result would be hashed, verified, and integrated into the ledger.

These are some ideas on future improvement of blockchain technology. While not trivially implementable, and each leading to an increase in the complexity, they would make the blockchain a whole lot more useful.

<a name="power">1</a>: [US Senate Hearing on Energy Efficiency of Blockchain and Similar Technologies](https://www.energy.senate.gov/public/index.cfm/files/serve?File_id=8A1CECD1-157C-45D4-A1AB-B894E913737D)
