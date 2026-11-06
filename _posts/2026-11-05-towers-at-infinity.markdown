---
layout: post
title:  "Towers at Infinity"
date:   2026-11-05 16:30:00 +0100
categories: mathematics
math: true
---
{% include analytics.html %}

# Towers at Infinity

Two infinitely tall towers. At ground level their inner walls stand at $$x = +1$$ and $$x = -1$$. With height they lean inward and converge towards $$x = 0$$, but they meet only at infinity. The object of interest is the spire of space between them: infinite in height, with a width that shrinks without ever reaching zero.

[Open the interactive visualizer fullscreen]({{ "/towers-at-infinity.html" | relative_url }}){: target="_blank" rel="noopener"}

In the visualizer you can climb the towers by dragging, zoom with the wheel or a pinch, switch the envelope between exponential and power-law decay, and roughen the walls. "Track the gap" rescales the horizontal axis to the current width, so you can see that every storey repeats the one below it.

## The mathematical object

The object is the open region

$$
\Omega = \{(x, y) : y \ge 0,\; -g(y)\,(1+\rho T_2(y)) < x < g(y)\,(1+\rho T_3(y))\}
$$

in the plane, bounded by two curves that are graphs of $$x$$ as a function of height. The envelope $$g$$ satisfies $$g(0)=1$$, is strictly decreasing and tends to $$0$$. It is modulated by nowhere-differentiable Takagi functions of period one, $$T_2$$ with base 2 and weight $$w_l$$, and $$T_3$$ with base 3 and weight $$w_r$$. The two walls therefore share an envelope and a symmetry axis but are non-congruent fractal curves, with box-counting dimensions $$2 + \log_2 w_l$$ and $$2 + \log_3 w_r$$ respectively, when those exceed 1.

For every finite $$y$$ the width of the cross-section is positive, so the walls never intersect. Their distance tends to zero, and in the compactification of the plane they meet at the single point at infinity, which is the only limit point of the boundary not on the boundary. $$\Omega$$ is therefore unbounded in height and has empty interior at infinity. Its measure is

$$
\int_0^\infty \bigl(2 + \rho\,(T_2(y) + T_3(y))\bigr)\, g(y)\, dy ,
$$

which for exponential decay $$g(y) = q^y$$ converges to a finite value, whereas for $$g(y) = (1+y)^{-p}$$ it converges exactly when $$p > 1$$. A region whose width goes to zero can still have infinite area.

The boundary length is infinite in every case, because the Takagi curves have infinite length on every interval. So $$\Omega$$ is a set of finite or infinite area with infinite perimeter, and its closure contains no point where the two walls touch.

When $$g$$ is exponential the region is self-affine: translating up by one storey and dilating $$x$$ by $$1/q$$ maps $$\Omega$$ onto itself. That is why the walls' roughness, scaled to the envelope, repeats identically at every height while the absolute width decays geometrically.
