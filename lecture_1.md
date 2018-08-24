
# Lecture 1 – Phonons and specific Heat
_Based on chapter 2 of the book_

In this lecture we will:

- discuss specific heat of a solid based on atomic vibrations (_phonons_)
- disregard periodic lattice $\Rightarrow$ consider homogeneous medium
    - _(chapter 9: discuss phonons in terms of atomic masses and springs)_
- discuss the Einstein model
- discuss the Debye model
- introduce reciprocal space, periodic boundary conditions and _density of states_

### Einstein model
Before solid state physics: heat capacity per atom $C=3k_{\rm B}$ (Dulong-Petit). Each atom is (classical) harmonic oscillator in three directions. Experiments showed that this law breaks down at low temperatures, where $C$ reduces to zero ($C\propto T^3$).

This can be explained by considering a _quantum_ harmonic oscillator:
![](figures/harmonic.svg)

$$\varepsilon_n=\left(n+\frac{1}{2}\right)\hbar\omega$$

Phonons are bosons $\Rightarrow$ they follow Bose-Einstein statistics.

$$
n(\omega,T)=\frac{1}{ {\rm e}^{\hbar\omega/k_{\rm B}T}-1}\Rightarrow\bar{\varepsilon}=\frac{1}{2}\hbar\omega+\frac{\hbar\omega}{ {\rm e}^{\hbar\omega/k_{\rm B}T}-1}
$$

![](figures/bose_einstein.svg)

The term $\frac{1}{2}\hbar\omega$ is the _zero point energy_, which follows from the uncertainty principle.

In order to calculate the heat capacity per atom $C$, we need to differentiate $\bar{\varepsilon}$ to $T$.

$$
\begin{multline}
C = \frac{\partial\bar{\varepsilon}}{\partial T}
= -\frac{\hbar\omega}{\left({\rm e}^{\hbar\omega/k_{\rm B}T}-1\right)^2}\frac{\partial}{\partial T}\left({\rm e}^{\hbar\omega/k_{\rm B}T}-1\right)\\
= \frac{\hbar^2\omega^2}{k_{\rm B}T^2}\frac{ {\rm e}^{\hbar\omega/k_{\rm B}T}}{\left({\rm e}^{\hbar\omega/k_{\rm B}T}-1\right)^2}
=k_{\rm B}\left(\frac{\hbar\omega}{k_{\rm B}T}\right)^2\frac{ {\rm e}^{\hbar\omega/k_{\rm B}T}}{\left({\rm e}^{\hbar\omega/k_{\rm B}T}-1\right)^2}
\end{multline}
$$

![](figures/zeropoint.svg)

The dashed line signifies the classical value, $k_{\rm B}$. Shaded area $=\frac{1}{2}\hbar\omega$, the zero point energy that cannot be removed through cooling.

This is for just one atom. In order to obtain the heat capacity of a full material, we would have to multiply $C$ (or $\bar{\varepsilon}$) by $3N$, _i.e._ the number of harmonic oscillators according to Einstein model.

### Debye model
The Einstein model explained the experimental data quite well, but still slightly underestimated the observed values of $C$. Apparently the "each atom is an oscillator"-idea is too simplistic.

![](figures/einstein.svg)

Peter Debye (1884 – 1966) suggested to instead consider _normal modes_: sound waves that propagate through a solid with velocity $v=\omega/k$, where $k=2\pi/\lambda$ is the _wave number_. Instead of just multiplying $\bar{\varepsilon}$ by $3N$, we now use:

$$E=\int\limits_0^\infty\left(\frac{1}{2}\hbar\omega+\frac{\hbar\omega}{ {\rm e}^{\hbar\omega/{k_{\rm B}T}}-1}\right)g(\omega){\rm d}\omega$$

$g(\omega)$ is the _density of states_: the number of normal modes found at each position along the $\omega$-axis. How do we calculate $g(\omega)$?


#### Reciprocal space, periodic boundary conditions
Each normal mode can be described by a _wave vector_ ${\bf k}$. A wave vector represents a point in _reciprocal space_ or _k-space_. We can find $g(\omega)$ by counting the number of normal modes in k-space and then converting those to $\omega$.

How far apart are the normal modes in k-space? This is determined by the boundaries of the solid. One way to treat the boundaries is by using _fixed boundary conditions_ (like a guitar string), resulting in modes $k=\pi/L$, $2\pi/L$, $3\pi/L$ etc., where $L$ is the length of the solid.

In this course, however, we will exclusively use _periodic boundary conditions_, where one edge of the solid should connect seamlessly to the opposite edge. This results in:

$$k=\ ..., \frac{-4\pi}{L}, \frac{-2\pi}{L}, 0, \frac{2\pi}{L}, \frac{4\pi}{L}, ...$$

The three-dimensional wave vector ${\bf k}$ can be any threefold permutation of these values. All possible values of ${\bf k}$ then form a grid in k-space:

![](figures/DOS_periodic.svg)

There is one allowed ${\bf k}$ per $\left(\frac{2\pi}{L}\right)^3$. The number of ${\bf k}$-values inside a sphere with radius $k$:

$$N=\frac{\frac{4}{3}\pi k^3}{\left(\frac{2\pi}{L}\right)^3}=\frac{Vk^3}{6\pi^2}$$

This means for the density of states $g(k)$ as a function of $k$:

$$g(k)=\frac{ {\rm d}N}{ {\rm d}k}=\frac{Vk^2}{2\pi^2}$$

The density of states $g(\omega)$ in frequency space then becomes:

$$g(\omega)=g(k)\frac{ {\rm d}k}{ {\rm d}\omega}=\frac{Vk^2}{2\pi^2}\frac{ {\rm d}k}{ {\rm d}\omega}$$


In general, ${\rm d}k/{\rm d}\omega$ can be difficult to calculate; we will see more of this later. But going back to the Debye model for now, where we assume simple sound waves with $v=\omega/k$, this reduces to $g(\omega)=V\omega^2/2\pi^2v^3$. The total energy then becomes:

$$ E=E_{\rm Z}+\frac{3V}{2\pi^2 v_{\rm s}^3}\int\limits_0^\infty\left(\frac{\hbar\omega}{ {\rm e}^{\hbar\omega/k_{\rm B}T}-1}\right)\omega^2{\rm d}\omega$$

Here, the factor 3 comes from the fact that every wave has three polarizations (two transversal, one longitudinal). The term $E_{\rm Z}$ goes to infinity through integration. This is no problem, as it doesn't count towards the heat capacity.

Substitute $x\equiv\frac{\hbar\omega}{k_{\rm B}T}$:

$$\Rightarrow E=E_{\rm Z}+\frac{3V}{2\pi^2 v_{\rm s}^3}\frac{\left(k_{\rm B}T\right)^4}{\hbar^3}\int\limits_0^\infty\frac{x^3}{ {\rm e}^x-1}{\rm d}x$$

The integral on the right is a constant, $\left(\frac{\pi^4}{15}\right)$ $\Rightarrow$ $C=\frac{ {\rm d}E}{ {\rm d}T}\propto T^3$.

#### Debye's interpolation for medium T
The above approximation works very well at low temperature. But at high temperature, $C$ should of course settle at $3k_{\rm B}$ (the Dulong-Petit value). The reason why the model breaks down, is that it assumes that there is an infinite number of harmonic oscillators up to infinite frequency.

Debye proposed an approximation: all phonons are acoustic (i.e. constant sound velocity) until a certain cut-off frequency, beyond which there are no phonons.

$$
g(\omega) = \left\{
    \begin{array}{ll}
        \frac{3V\omega^2}{2\pi^2v_{\rm s}^3} & \omega<\omega_{\rm D} \\
        0 & \omega>\omega_{\rm D}
    \end{array}
\right.
$$

What determines the _Debye frequency_ $\omega_{\rm D}$?

$$
\int_0^{\omega_{\rm D}}g(\omega){\rm d}\omega=\frac{V\omega_{\rm D}^3}{2\pi^2v_{\rm s}^3}=3N,
$$

where $N$ is the number of atom, so $3N$ the number of degrees of freedom.

Substitute in $E$, differentiate to $T$:

$$
\Rightarrow C=9Nk_{\rm B}\left(\frac{T}{\Theta_{\rm D}}\right)^3\int_0^{\Theta_{\rm D}/T}\frac{x^4{\rm e}^x}{({\rm e}^x-1)^2}{\rm d}x,
$$

where $x=\frac{\hbar\omega}{k_{\rm B}T}$ and $\Theta_{\rm D}\equiv\frac{\hbar\omega_{\rm D}}{k_{\rm B}}$, the _Debye temperature_.

![](figures/debye.svg)
