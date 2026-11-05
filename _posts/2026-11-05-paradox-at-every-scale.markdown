---
layout: post
title:  "Paradox at Every Scale: Yablo's sequence, sieved"
date:   2026-11-05 16:10:00 +0100
categories: math logic
math: true
---
{% include analytics.html %}

Yablo's paradox is an infinite list of sentences, each saying that all the later ones are untrue. No sentence refers to itself, and yet no assignment of truth-values works: if any sentence were true, the next one would be too, so none is; but then the first one is. Thirty years of argument about whether this is "really" circular have not produced a criterion for which such patterns of reference are paradoxical.

My paper, [Paradox at Every Scale]({{ '/files/paradox-at-every-scale.pdf' | relative_url }}), introduces a family on which the question can be computed. A *sieve* is a set $$R$$ of distances; the sieve system lets each sentence say that the sentences at $$R$$-distance from it are untrue. Yablo's sequence is the sieve of all distances. The key fact is that a consistent assignment of truth-values is the same thing as a *kernel* of the reference digraph, a notion from the theory of games, so all of kernel theory applies.

What comes out:

- A periodic sieve is paradoxical exactly when a finite quotient of its reference digraph has no kernel. The "hidden circularity" the paradox was accused of is a literal odd cycle in that quotient: the sieve of distances $$\equiv 1 \pmod 3$$ is a directed triangle in disguise.
- For every sieve that can be written down, paradoxicality is decidable (via Büchi and Rabin), although for digraphs in general it is $$\Sigma^1_1$$-complete.
- The size of the sieve is irrelevant. The primes and the powers of two are harmless; the even numbers are paradoxical; a tree sieve can contain a full copy of Yablo's sequence below every vertex and still be fine.
- A tree-indexed sequence left without a verdict in 2002 is settled, and the known $$\omega$$-inconsistency of the Yablo biconditionals is explained as the absence of a kernel.
- Yablo's sequence is fixed-point circular, like a fractal, but not reference circular.

Open: is the sieve of *squares* paradoxical? Any consistent assignment would be a square-difference-free set, hence of density zero, that is also "upward absorbing". I don't know whether such a set exists.
