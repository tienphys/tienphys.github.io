---
layout: post
title: "Bloch theorem"
date: 2026-07-13
mathjax: true
---

Let us consider a particle in a spatially periodic potential, $V(x+a)=V(x)$; here $a$ is called the *lattice spacing*. The total Hamiltonian of the system reads

$$
\begin{align}\label{eq:hamiltonian}
    \hat H = \frac{\hat p^2}{2m} + \hat V(x).
\end{align}
$$

We introduce the *discrete translation operator* $\hat T_a: x\to x+a$; this is motivated by the translation symmetry properties of the particle's potential. One can check that the discrete translation operator commutes with the total Hamiltonian, $[\hat T_a, H]$
%%% Spoiler starts
Here's how we show they commute
%%% Spoiler ends
Since they commute, they share the same spectra, i.e. eigenvalues and eigenvectors. 