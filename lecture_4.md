# Electrons and phonons in 1D

Last lecture:

* Movement of a few atoms (Newton's equations)
* Energies of molecular orbitals (LCAO)

This lecture:

* Infinitely many atoms
* Main idea: use *periodicity* in space, similar to periodicity in time

## Equations of motion 

### Phonons

![](figures/phonons2.svg)

If atom $n$ has displacement $u_n$, then

$$
m \ddot{u}_n = -\kappa (u_n - u_{n-1}) -\kappa (u_n - u_{n+1}),
$$

and if we have a system of size $L = Na$ with periodic boundary conditions, we additionally have $u_L = u_0$.

### Electrons

![](figures/lattice_potential.svg)

A similar problem: we consider an LCAO wave function $\psi = \sum_n c_n \phi_n$. We need to solve the Schrödinger equation

$$
E c_n = E_0 c_n + t c_{n+1} + t c_{n-1}
$$

The periodic boundary conditions mean $c_N = c_0$.

### Key idea

Our task is to find all normal modes and to take $L → ∞$.

All atoms are similar $⇒$ the solution should be similar for all atoms $⇒$  
For phonons:
$$u_n = e^{i \omega t - i k x} u_0,$$
and for electrons:
$$c_n = e^{i E t/\hbar - i k x} c_0.$$
(Here we wrote the time-dependent solution of the Schrödinger equation to emphasize the similarity between two systems.)

Periodicity requires $e^{i k L} = 1$ $⇒$ $k = 2\pi p/L$, with $p\in \mathbb{Z}$.

In that case $c_n/c_0 = \exp(2 \pi n p a/L) = \exp(2 \pi n p/N)$, and changing $p→p+N$ corresponds to exactly the same solution, and we have $N$ different solutions in total.

We can see that the solutions with different $k$ (or different $p$) are identical by plotting them:

![](figures/phonons4.svg)

Let's count how many different solutions we expect to find. We have a system with $N$ degrees of freedom (either $u_n$ or $c_n$), and therefore we need $N$ normal modes (or eigenstates).

Because we proposed $N$ different plane wave solutions, if we find an energy or frequency for each solution, we have fully solved the problem!

## Solution

### Phonons

First substitute the Ansatz into the equations of motion:
$$ -m \omega^2 c_0 e^{i\omega t - ikx} = \kappa c_0  e^{i\omega t}(-2 e^{-ikx} + e^{-ikx+ika}+ e^{-ikx-ika}),$$
the exponents and $c_0$ drop out (just like we expected) and we get:
$$ -m \omega^2 = \kappa (-2 + e^{ika}+ e^{-ika})=\kappa [-2 + 2\cos(ka)],$$
or after a further simplification:
$$\omega = \sqrt{\frac{2\kappa}{m}}\sqrt{1-\cos(ka)} = 2\sqrt{\frac{\kappa}{m}}|\sin(ka/2)|$$
[here we used that $1-\cos(x)=2\sin^2(x/2)$.]

So we arrive to the dispersion relation

![](figures/phonons3.svg)

Here $k_p = 2\pi p / L$ for $0 ≤ p < N$ are *all the normal modes* of the crystal, and therefore we can rederive a better Debye model!

Before we had $\sum_p → \frac{L}{2\pi}\int_{-\omega_D/v_s}^{\omega_D/v_s}dk$, because we introduced the cutoff to fix the problem with the number of modes.

Now $\sum_p → \frac{L}{2\pi}\int_{-\pi/a}^{\pi/a}dk$, the integral is over a finite number of modes because there is only a finite number of modes.

**Sound velocity:** at small $k$ $\sin(ka/2)\approx ka/2$, and therefore $\omega \approx \sqrt{\kappa/m} k a$, so we have derived the existence of sound waves.

### Electrons

Substitute the Ansatz into the equations of motion:

$$
E c_0 e^{-ikx} = E_0 c_0 e^{-ikx} +t e^{-ikx-ika} + te^{-ikx+ika},
$$
and after canceling the exponents we immediately get
$$
E = E_0 + 2t\cos(ka),
$$
so we come to the dispersion relation:

![png](figures/tight_binding_1d.svg)


Usually electron dispersion has multiple options for $E(k)$, each called a *band*. The complete dispersion relation is also called a *band structure*.

The band bottom is at $k=0$ (when $t<0$). There the energy

$$
E = E_0 + 2t\cos{ka} \approx E_0 + 2t - t (ka)^2.
$$
Comparing this with $E=(\hbar k)^2/2m$, we see that the dispersion relation is as if the electrons had an effective mass $m^*=\hbar^2/2ta^2$.

A single band has $2N$ states ($N$ $k$-values and 2 spins). If each atom contributes 2 electrons, all these states must be occupied. Applying electric field, therefore cannot create electric current $⇒$ we have explained insulators!

## Group velocity, effective mass, density of states

*(here I only discuss electrons; for phonons everything is the same except for replacing $E = \hbar \omega$)*

Question: what happens if we apply an external electric field to the crystal:

![](figures/electric_field.svg)

A reminder from Hamiltonian mechanics:

$$H = \frac{p^2}{2m} + U(r)$$

$$\begin{aligned}
\frac{dr}{dt} &= \frac{\partial H(p, r)}{\partial p} \equiv v \\
\frac{dp}{dt} &= -\frac{\partial H(p, r)}{\partial r} \equiv F
\end{aligned}$$

The first equation is *velocity*, the second equation is *force*.

Connection to quantum mechanics: $p = \hbar k$.

If electrons form bands, then in each band
$$ H = E(k) + \tilde{U}(r),$$

where $\tilde{U}(r) = -e\mathbf{E}$ only includes slow variations of the electrostatic potential (the rapidly changing atomic potential is responsible for $E(k)$):


For electrons in an arbitrary band structure: $\hbar^{-1}\partial H/\partial k$ is the **group velocity** (same as for phonons).

Another important concept is the **effective mass** defined using an analogy:

$$\frac{dv}{dt} = m_{eff}^{-1} F$$.

Substituting, we get

$$m_{eff} = \hbar^2\left(\frac{d^2 E(k)}{dk^2}\right)^{-1}$$

![](figures/meff_1d_tb.svg)


### density of states

DOS is the number of states per unit energy. In 1D we have
$$g(E) = \sum |dk/dE| = \sum |v|^{-1},$$

The sum goes over all bands existing at a given energy, positive and negative momenta, and spins.

Using

$$ E = E_0 + 2t \cos(ka), $$

we get

$$
k = \pm\arccos[(E - E_0) / 2t],
$$
and
$$
|d k / d E| = [4t^2 - (E - E_0)^2]^{-1/2}.
$$

You can get to this result immediately if you remember the derivative of arccosine. Otherwise you need to go the long way: compute $dE/dk$ as a function of $k$, express $k$ through $E$ as we did above, and take the inverse.

Also a sanity check: when the energy is close to the bottom of the band, $E = E_0 + 2t + \delta E$ we get $g(E) \sim E^{-1/2}$, as we would expect in 1D.

## More complex systems

### More hoppings in LCAO

Consider electrons in a 1D atomic chain again

![](figures/lattice_potential.svg)

Let's relax the assumption that there is no hopping between atoms that are further than nearest neighbors:

$$ \langle \phi_n | H | \phi_{n+2}\rangle \equiv t' ≠ 0.$$

We now have more terms in the Schrödinger equation:

$$ E c_n = E_0 c_n + t c_{n-1} + t c_{n+1} + t' c_{n-2} + t' c_{n+2},$$

but the same Ansatz as before should work: $ c_n = c_0 \exp(ikna) $.

Indeed, after substituting we get:

$$ E = E_0 + 2t\cos(ka) + 2t'\cos(2ka).$$

*(check that!)*

Therefore including more hopping terms works out of the box using the same Ansatz.

### More degrees of freedom per unit cell:

![](figures/phonons5.svg)

Before we used that all atoms are similar, but this doesn't work anymore. We need to generalize our anzatz. We label all degrees of freedom in each **unit cell** (a repeated element of the system).

For two atoms in a unit cell we have displacements $u_{1,n}$ and $u_{2,n}$. Here the first index is the atom number within the unit cell, second is the unit cell number. The atom with mass $M$ is the atom 1, and the atom with mass $m$ is the atom 2.

Having the degrees of freedom let's write down the equations of motion:

$$
\begin{aligned}
M\ddot{u}_{1,n}=\kappa(u_{2,n}-2u_{1,n}+u_{2,n-1})\\
m\ddot{u}_{2,n}=\kappa(u_{1, n} - 2u_{2,n}+u_{1,n+1}),
\end{aligned}
$$

The new Ansatz is conceptually the same as before: all unit cells should be the same up to a phase factor:

$$
\begin{pmatrix}
u_{1,n}\\
u_{2,n}
\end{pmatrix} =
e^{i\omega t - ik na}
\begin{pmatrix}
u_{1}\\
u_{2}
\end{pmatrix}.
$$

Substituting this ansatz into the equations of motion we end up with an eigenvalue problem:
$$\omega^2
\begin{pmatrix}
M & 0 \\ 0 & m
\end{pmatrix}
\begin{pmatrix}
u_{1} \\ u_{2}
\end{pmatrix} = \kappa
\begin{pmatrix}
2 & -1 - e^{ika} \\ -1-e^{-ika} & 2
\end{pmatrix}
\begin{pmatrix}
u_{1}\\ u_{2}
\end{pmatrix},$$
with eigenfrequencies
$$\omega^2=\frac{\kappa(M+m)}{Mm}\pm \kappa\left\{\left(\frac{M+m}{Mm}\right)^2-\frac{4}{Mm}{\rm sin}^2\left(\frac{1}{2}ka\right)\right\}^{\frac{1}{2}}$$

Looking at the eigenvectors we see that for every $k$ there are now two values of $\omega$: one corresponding to in-phase motion (–) and anti-phase (+).

![](figures/phonons6.svg)

'A' is called the _acoustic branch_, 'B' is called the _optical branch_.

Important concept: _density of states_ (DOS): $g(\omega)=\rho_{\rm S}\frac{ {\rm d}k}{ {\rm d}\omega}$

The quantity $\frac{ {\rm d}k}{ {\rm d}\omega}$ can be calculated from the dispersion.

When plotted, the DOS may look something like this:

![](figures/phonons8.svg)

Note that normally $g(\omega)$ is plotted along the vertical axis and $\omega$ along the horizontal axis – the plot above is just to demonstrate the relation between the dispersion and the DOS. The singularities in $g(\omega)$ at the bottom and top of each branch are called _van Hove singularities_. 

### Consistency check with 1 atom per cell

But what if we take $M\rightarrow m$? We should reproduce the previous result with only one band!

The reason why we get two bands is because we have $a\rightarrow 2a$ compared to 1 atom per unit cell!

For $M\rightarrow m$, the dispersion diagram should come back to the diagram obtained for the first example (i.e. with identical masses).

To reconsile the two pictures let's plot two unit cells in the reciprocal space. (Definition: each of these unit cells is called a **Brillouin zone**, a concept that will come up later.)

![](figures/phonons7.svg)

Doubling the lattice constant "folds" the band structure on itself, doubling all the bands.

### Total number of states

Which values of $k$ are allowed for a finite 1D crystal of length $L$?

Assume closed boundary conditions $\rightarrow$ standing waves $\rightarrow k=\frac{\pi}{L},\frac{2\pi}{L},\frac{3\pi}{L},\frac{4\pi}{L}...$

$\rightarrow \rho_{\rm S}(k)=$ (no. of $k$-values / unit of $k$) $=\frac{L}{\pi}$, where only the positive part of $k$-space is filled with allowed $k$-values.

For open boundary conditions $\rightarrow$ running waves $\rightarrow k=$ $...\frac{-4\pi}{L},\frac{-2\pi}{L},0,\frac{2\pi}{L},\frac{4\pi}{L}...$

$\rightarrow \rho_{\rm R}(k)=\frac{L}{2\pi}$, which is lower than for the case of closed boundary conditions, however, in this case the entire $k$-space is filled. 

## Summary

* By using plane waves in real space as an Ansatz we found all normal modes and eigenvectors
* Dispersion relation of a system with period $a$ in real space is periodic with period $2\pi/a$ in $k$-space
* Computing dispersions explains all the problems we listed before (need for cutoff, lack of scattering with every single atom, existence of insulators).
* Electrons and phonons have a complicated nonlinear relation between momentum and velocity (**group velocity**), effective mass, and density of states
* In a system with more than one degree of freedom per unit cell we need to consider independent amplitudes for each degree of freedom, and get multiple bands.
