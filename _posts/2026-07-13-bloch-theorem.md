---
layout: post
title: "Bloch theorem"
date: 2026-07-13
mathjax: true
---

Let us consider a particle in a spatially periodic potential, $V(x+a)=V(x)$; here $a$ is called the *lattice spacing*. The total Hamiltonian of the system reads

$$
\begin{align}\label{eq:hamiltonian}
    H = \frac{p^2}{2m} + V(x).
\end{align}
$$

We introduce the *discrete translation operator* $T_a: x\to x+a$; this is motivated by the translation symmetry properties of the particle's potential. One can check that the discrete translation operator commutes with the total Hamiltonian, $[T_a, H]=0$

<details class="spoiler" markdown="1">
<summary>Show why $[T_a, H]=0$</summary>

There are two ways. First, let $\psi$ be an arbitrary wavefunction.

$$
\begin{align}
T_aH\psi &= T_a\left(-\frac{\hbar^2}{2m}\frac{\partial^2\psi(x)}{\partial x^2}+V(x)\psi(x)\right),\\
&=-\frac{\hbar^2}{2m}\frac{\partial^2\psi(x+a)}{\partial x^2}+V(x+a)\psi(x+a),\\
&=-\frac{\hbar^2}{2m}\frac{\partial^2\psi(x+a)}{\partial x^2}+V(x)\psi(x+a),\\
\end{align}
$$

where we have used the fact that $V(x+a)=V(x)$. Similarly, we can show 

$$
\begin{align}
HT_a\psi =-\frac{\hbar^2}{2m}\frac{\partial^2\psi(x+a)}{\partial x^2}+V(x)\psi(x+a).
\end{align}
$$

Since $\psi$ is arbitrary, $T_aH=HT_a$, and thus $[T_a, H]=0$.

The second way is a little bit more operator-perspective. If we could guess, what specifically would $T_a$ be? It is a translation in the position-space $x$, hence the generator of translation must be based on momentum $p=\hbar k$. By how much? The lattice spacing $a$. Hence $T_a=e^{\frac{i}{\hbar}ap}=e^{ika}$. Since $T_a$ is unitary, and since $V(x)$ is periodic in $a$, $T_a V(x) T_a^\dagger=V(x+a)=V(x)$. Finally, we compute

$$
\begin{align}
T_a H(x) T_a^\dagger = H(x+a) = H(x),
\end{align}
$$

i.e. the unitary $T_a$ leaves $H$ invariant, and thus they commute.

</details>

Since they commute, they share the same spectra, i.e. eigenvalues and eigenvectors. The eigenvalues of $T_a$ are $e^{ika}$, where $k$ is called the *crystal momentum/quasimomentum*.

<details class="spoiler" markdown="1">
<summary>Show derivation of $e^{ika}$</summary>

We consider the eigenvalue problem $T_a \psi = \lambda \psi$. We notice that

$$
\begin{align}
||\psi||^2 = \psi^\dagger\psi = \psi^\dagger T_a^\dagger T_a \psi = ||T_a\psi||^2=|\lambda|^2||\psi||^2 = |\lambda^2|.
\end{align}
$$

Since $\psi$ must be normalized, $\|\lambda\|=1$, meaning $\lambda=e^{i\theta}$ or in words every eigenvalue of $T_a$ lies on the unit circle, for some real angle $\theta$. We can elaborate more on $\theta$ by acknowledging that $(T_a)^n=T_{na}$, which is a translation properties. This means $(T_a)^n\psi=T_{an}\psi=\lambda^n\psi=e^{in\theta}$. Let us define the total distance translated is $L=na$, the corresponding accumulated phase that the particle acquires is $n\theta$. We observe that the phase grows linearly with the distance, meaning $n\theta=\text{something}\times na$, and that something can only be $\theta/a$, meaning phase accumulated per unit length. It has dimensions of inverse length, which suggests it is a wavevector. So we define $k=\theta/a$ the *crystal momentum/quasimomentum*. In the end, $\lambda=e^{ika}$.

</details>

With the introduction of $k$, we can introduce the notion of the Brillouin zone. Notice that the eigenvalue is not unique, $e^{i(k+2\pi/a)a}=e^{i2\pi}e^{ika}=e^{ika}$, meaning the act of introducing $2\pi/a$ inside the argument of is not meaningful. This suggests $k$, the crystal momentum is only modulo defined $2\pi/a$. Taking $k=0$ the origin, the Brillouin zone is the zone of $k$ such that

$$
\begin{align}
-\frac{\pi}{a} < k < \frac{\pi}{a}
\end{align}
$$

Outside of the Brillouin zone, states with $k$ are physically equivalent of the states inside of it, so we can discard them. A particlular action that people usually do is to "fold" energy dispersion into the first Brillouin zone (we will try to add images later). 

Now that we've found the eigenvalues of $T_a$, we proceed with its eigenvectors. Let them be $\langle x|\psi(x)\rangle=\psi(x)$. On one hand, by definition of an eigenvector, $T_a\psi(x)=e^{ika}\psi(x)$. On the other hand, by definition of the operator $T_a$, $T_a\psi(x)=\psi(x+a)$. 