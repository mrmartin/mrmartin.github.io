---
layout: post
title:  "Bounded Complexity Languages"
date:   2016-11-09 18:48:30 +0100
categories: computing
---

Recently, I have been thinking about Gödel's Incompleteness Theorem, its equivalence to the Halting Problem, and the applications of these results in solving P vs NP.

While I haven't solved the Millenium Prize problem, I came across an interesting realization: any program can be written in such a way that their upper bound comlpexity it is immediately clear from the code. This finding is explained in some depth in my white paper [here](/Bounded_Complexity_Languages.pdf).

This opens up a new way of thinking about computational complexity, one that in my opinion allows simpler inference. What's more, it potentially comes to a insightful conclusion: if an algorithm cannot be written only with for loops and without recursion, its complexity is unbounded.
