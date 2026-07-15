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

We introduce the *discrete translation operator* $T_a: x\to x+a$; this is motivated by the translation symmetry of the particle's potential. One can check that the discrete translation operator commutes with the total Hamiltonian, $[T_a, H]=0$.

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

The second way is a little more operator-flavored. If we were to guess, what specifically would $T_a$ be? It is a translation in position space $x$, so its generator must be the momentum operator $p$ (whose eigenvalue on a plane wave is $\hbar k$). By how much? The lattice spacing $a$. Hence $T_a=e^{\frac{i}{\hbar}ap}$. Since $T_a$ is unitary, and since $V(x)$ is periodic with period $a$, we have $T_a V(x) T_a^\dagger=V(x+a)=V(x)$. Finally,

$$
\begin{align}
T_a H(x) T_a^\dagger = H(x+a) = H(x),
\end{align}
$$

i.e. the unitary $T_a$ leaves $H$ invariant, and thus they commute.

</details>

Since they commute, they are simultaneously diagonalizable: there *exists* a common eigenbasis. Because our end goal is the energy eigenstates of $H$, and because knowing the eigenstates of $T_a$ constrains them, we first study the spectrum of $T_a$. The eigenvalues of $T_a$ turn out to be $e^{ika}$, where $k$ is called the *crystal momentum/quasimomentum*.

<details class="spoiler" markdown="1">
<summary>Show derivation of $e^{ika}$</summary>

We consider the eigenvalue problem $T_a \psi = \lambda \psi$. Since $T_a$ is unitary,

$$
\begin{align}
\vert\psi\vert^2 = \psi^\dagger\psi = \psi^\dagger T_a^\dagger T_a \psi = \vert T_a\psi \vert^2=\vert\lambda\vert^2\vert\psi\vert^2.
\end{align}
$$

Since $\psi\neq 0$, we may divide to get $\vert\lambda\vert=1$, i.e. every eigenvalue of $T_a$ lies on the unit circle: $\lambda=e^{i\theta}$ for some real angle $\theta$. We can pin down $\theta$ by using the composition property $(T_a)^n=T_{na}$. This gives $(T_a)^n\psi=T_{na}\psi=\lambda^n\psi=e^{in\theta}\psi$. If the total distance translated is $L=na$, then the accumulated phase is $n\theta$. The phase grows linearly with the distance, so $n\theta=(\text{const})\times na$, and the constant can only be $\theta/a$ — the phase accumulated per unit length. This quantity has dimensions of inverse length, i.e. it is a wavevector, so we define $k=\theta/a$, the *crystal momentum/quasimomentum*. In the end, $\lambda=e^{ika}$.

</details>

With $k$ in hand, we can introduce the *Brillouin zone*. Notice that the eigenvalue is not unique in $k$: $e^{i(k+2\pi/a)a}=e^{i2\pi}e^{ika}=e^{ika}$, so shifting $k$ by $2\pi/a$ changes nothing physical. Thus $k$ is only defined modulo $2\pi/a$. Taking $k=0$ as the origin, the first Brillouin zone is the set of $k$ with

$$
\begin{align}
-\frac{\pi}{a} < k \leq \frac{\pi}{a}
\end{align}
$$

Outside the Brillouin zone, states are physically equivalent to states inside it, so we discard them. A common move is to "fold" the energy dispersion into the first Brillouin zone.

Now that we have the eigenvalues of $T_a$, we turn to its eigenvectors. Let $\langle x\vert\psi\rangle=\psi(x)$. On one hand, by definition of an eigenvector, $T_a\psi(x)=e^{ika}\psi(x)$. On the other hand, by definition of the operator, $T_a\psi(x)=\psi(x+a)$. Combining the two gives the *Bloch condition*

$$
\begin{align}\label{eqn:bloch_condition}
\psi(x+a)=e^{ika}\psi(x).
\end{align}
$$

The Bloch condition is an *if-and-only-if* criterion for being an eigenvector of $T_a$. Every such $\psi$ can be rewritten in a particularly convenient form,

$$
\begin{align}
\psi_k(x)=e^{ikx}u_k(x), \qquad u_k(x+a)=u_k(x),
\end{align}
$$

and a $\psi$ written this way is called a *Bloch state*. This is not a special subclass: the Bloch form and the Bloch condition describe the *same* set of states — they are two names for "eigenvector of $T_a$ with eigenvalue $e^{ika}$."

<details class="spoiler" markdown="1">
<summary>Show that the Bloch form and the Bloch condition are equivalent</summary>

If $\psi(x)=e^{ikx}u(x)$ with $u$ periodic, then $\psi(x+a)=e^{ik(x+a)}u(x+a)=e^{ika}e^{ikx}u(x)=e^{ika}\psi(x)$, so the Bloch condition holds. Conversely, given any $\psi$ satisfying $\psi(x+a)=e^{ika}\psi(x)$, define $u(x)=e^{-ikx}\psi(x)$. Then

$$
u(x+a)=e^{-ik(x+a)}\psi(x+a)=e^{-ik(x+a)}e^{ika}\psi(x)=e^{-ikx}\psi(x)=u(x),
$$

so $u$ is periodic and $\psi=e^{ikx}u$ is in Bloch form. The two conditions are therefore equivalent.

</details>

So Bloch states are exactly the eigenstates of $T_a$. They are useful but not the end of the story, because the spectrum of $T_a$ is infinitely degenerate.

<details class="spoiler" markdown="1">
<summary>Remind me why it is infinitely degenerate</summary>

Since we only care about the degeneracy of $T_a$, drop $V(x)$ for a moment. Then $H=p^2/2m$ admits plane-wave eigenstates $(1/\sqrt{2\pi\hbar})e^{ikx}$ (not square-integrable — normalized instead with the Dirac delta) of energy $\hbar^2k^2/2m$. Indeed $T_ae^{ikx}=e^{ik(x+a)}=e^{ika}e^{ikx}$, so $e^{ikx}$ is an eigenstate of $T_a$ with eigenvalue $e^{ika}$. Here is the catch: $e^{i(k+\frac{2\pi n}{a})x}$ for any $n\in\mathbb{Z}$ is *also* an eigenstate of $T_a$ with the *same* eigenvalue $e^{ika}$ (keeping $k$ in the first Brillouin zone). Since $n$ ranges over all integers, there are infinitely many of them. In linear-algebra language, the $e^{ika}$-eigenspace is not one-dimensional but infinite-dimensional (hence degenerate). For $H$, however, these states do *not* share an energy: $e^{i(k+2\pi n/a)x}$ has energy $\hbar^2(k+2\pi n/a)^2/2m$, which increases with $\vert n\vert $ at fixed $k$. This is the origin of *bands*, precisely the higher bands folded back into the first Brillouin zone.

</details>

Because each $k$-eigenvalue is infinitely degenerate, the Bloch condition--equivalently, being a Bloch state--does *not* by itself pick out a stationary state of $H$. This is exactly why $[T_a, H]$ does not solve the entire problem: a generic $T_a$-eigenstate is *not* an $H$-eigenstate. What Bloch states show is a *block structure*: because $[T_a,H]=0$, $H$ maps each $e^{ika}$-eigenspace into itself, so $H$ is block-diagonal in the Bloch basis, one block per $k$. What remains is to diagonalize $H$ *within* each block, which would have not been necessary if all block are one-dimeonsional (non-degenerate).

We do this by substituting a Bloch state $\psi_k=e^{ikx}u(x)$ into $H\psi=E\psi$. The result is an eigenvalue problem for $u$ alone:

$$
\begin{align}
\left[\frac{(p+\hbar k)^2}{2m}+V(x)\right]u(x)&=E\,u(x),\\
u(x+a)&=u(x).
\end{align}
$$

<details class="spoiler" markdown="1">
<summary>Derivation of the explicit eigenvalue problem</summary>

The momentum operator in the position basis is $p=-i\hbar\partial_x$. Acting on $\psi=e^{ikx}u(x)$,

$$
\begin{align}
p\big(e^{ikx}u\big)=-i\hbar\big(ik\,e^{ikx}u+e^{ikx}u'\big)=e^{ikx}(\hbar k-i\hbar\partial_x)u = e^{ikx}(p+\hbar k)u.
\end{align}
$$

Applying it twice, $p^2\big(e^{ikx}u\big)=e^{ikx}(p+\hbar k)^2 u$. Substituting into $H\psi=E\psi$ and cancelling the common factor $e^{ikx}$ (which never vanishes) yields the stated equation.

</details>

The operator $H_k\equiv\frac{(p+\hbar k)^2}{2m}+V(x)$ is called the *Bloch Hamiltonian*. The point of this rewriting is that the phase factor $e^{ika}$ is gone: $k$ is now a fixed parameter. We have chosen one value of $k$, hence one $e^{ika}$-eigenspace, and are now working inside it. The function $u$ is a periodic function on a single unit cell $[0,a]$, i.e. it lives on a *finite* domain (a ring of circumference $a$). A Hermitian operator on a compact domain has a *purely discrete spectrum* (particle in a box, particle on a ring, etc.). So at fixed $k$, solving $H_k u = E u$ returns a countable ladder of energies

$$
E_1(k)\leq E_2(k)\leq \dots \leq E_n(k)\leq \dots
$$

with normalizable eigenfunctions $u_{nk}(x)$ that form a complete orthonormal basis of $L^2(\text{cell})$. The integer $n$ is precisely the *band index*.

This is analogous to the hydrogen atom in QM 1: spherical symmetry lets us fix the angular labels $\ell, m$, and within that sector we diagonalize the (radial) Hamiltonian to obtain a further discrete quantum number. The parallel is about the *procedure*: a symmetry label reduces the problem to a discrete 1D eigenproblem yielding an extra quantum number.

Finally, to recover the full solution, we take each $u_{nk}(x)$ and multiply by $e^{ikx}$:

$$
\psi_{nk}(x)=e^{ikx}u_{nk}(x), \qquad u_{nk}(x+a)=u_{nk}(x).
$$

By construction, each $\psi_{nk}$ is

1. an eigenstate of $T_a$ (it lives in the $e^{ika}$-eigenspace, hence is a Bloch state), and
2. an eigenstate of $H$ with energy $E_n(k)$, since we just diagonalized $H$ within that block.

The statement that the energy eigenstates of $H$ can be chosen to be Bloch states, labelled by a band index $n$ and a crystal momentum $k$, is precisely Bloch's theorem.

### A word on completeness

It is tempting to say "$\psi_{nk}$ are eigenstates of the Hermitian $H$, hence a complete orthonormal basis." However this is not true.

The correct statement should be: at fixed $k$, the Bloch Hamiltonian $H_k$ acts on the *compact* cell $[0,a]$, has a purely discrete spectrum, and its eigenfunctions $\{u_{nk}\}_n$ form a genuine complete orthonormal basis of $L^2(\text{cell})$.

On the other hand, the full Hamiltonian $H$'s spectrum is not discrete. Its spectrum is the union of the bands $\bigcup_n\{E_n(k):k\in\text{BZ}\}$, and since each $E_n(k)$ varies *continuously* with $k$, the spectrum is *continuous*, not discrete. Correspondingly the $\psi_{nk}$ are not normalizable:

$$
\int_{-\infty}^{\infty}\vert \psi_{nk}(x)\vert ^2\,dx=\int_{-\infty}^{\infty}\vert u_{nk}(x)\vert ^2\,dx=\infty
$$

because $\vert u_{nk}\vert ^2$ is periodic and nonzero. This is just like plane waves.

If one wants a genuine countable complete orthonormal basis of *normalizable* states, one must impose Born–von Karman (periodic) boundary conditions on a ring of length $L=Na$. Then $e^{ikL}=1$ forces $k=\frac{2\pi j}{Na}$, giving $N$ allowed values of $k$ in the Brillouin zone; each $\psi_{nk}$ is now normalizable, and

$$
\{\psi_{nk}\}_{\,n\in\mathbb{N},\;k\in\text{BZ}}, \qquad \langle\psi_{nk}\vert \psi_{n'k'}\rangle=\delta_{nn'}\delta_{kk'},
$$

is a true complete orthonormal basis of the Hilbert space. Taking $N\to\infty$ (so $\sum_k\to\frac{L}{2\pi}\int dk$) recovers the $\delta$-normalized continuum picture above.