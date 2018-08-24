# Tight binding and nearly free electrons

Let's summarize what we learned about electrons so far:

* Free electrons form a Fermi sea ([lecture 2](lecture_1.md))
* Isolated atoms have discrete orbitals ([lecture 3](lecture_3.md))
* When orbitals hybridize we get *LCAO* or *tight-binding* band structures ([lecture 4](lecture_4.md))

In this lecture we:

* Formulate a general way of computing the electron band structure, the **Bloch theorem**.
* Derive the electron band structure when the interaction with the lattice is weak using the **Nearly free electron model**. This model:
    - Helps to understand the relation between tight-binding and free electron models
    - Describes the properties of metals.

All the different limits can be put onto a single scale as a function of the strength of the lattice potential $V(x)$:

![](figures/models.svg)

## Bloch theorem

> All Hamiltonian eigenstates in a crystal have the form
> $$ \psi_n(\mathbf{r}) = u_n(\mathbf{r})e^{i\mathbf{kr}} $$
> with $u_n(\mathbf{r})$ having the same periodicity as the lattice potential $V(\mathbf{r})$, and index $n$ labeling electron bands with energies $E_n(\mathbf{k})$.

In other words: any electron wave function in a crystal is a product of a periodic part that describes electron motion within a unit cell and a plane wave.

### Extra remarks

The wave function $u_n(\mathbf{r})e^{i\mathbf{kr}}$ is called a **Bloch wave**.

The $u_n(\mathbf{r})$ part is some unknown function. To calculate it we need to solve the Schrödinger equation. It is hard in general, but there are two limits when $U$ is "weak" and $U$ is "large" that provide us with most intuition.

If we change $\mathbf{k}$ by a reciprocal lattice vector $\mathbf{k} \rightarrow \mathbf{k} + h\mathbf{b}_1 + k\mathbf{b}_2 + l\mathbf{b}_3$, and we change $u_n(\mathbf{r}) \rightarrow u_n(\mathbf{r})\exp\left[-h\mathbf{b}_1 - k\mathbf{b}_2 - l\mathbf{b}_3\right]$ (also periodic!), we obtain the same wave function. Therefore energies of all bands $E_n(\mathbf{k})$ are periodic in reciprocal space with the periodicity of the reciprocal lattice.

Bloch theorem is extremely similar to the ansatz we used in [1D](lecture_4.md), and to the description of the [X-ray scattering](lecture_5.md).

## Nearly free electron model

In free electron model $E = \hbar^2 k^2/2m$.

* There is only one band
* The band structure is not periodic in $k$-space
* In other words the Brillouin zone is infinite in momentum space

Within the **nearly free electron model** we want to start from the dispersion relation of the free electrons and consider the effect of introducing a weak lattice potential. The logic is very similar to getting optical and acoustic phonon branches by changing atom masses (and therefore reducing the size of the Brillouin zone).

In our situation:

![](figures/nearly_free_electron_bands.svg)

The band gaps open where two copies of the free electron dispersion cross.

### Avoided level crossing

*Remark: this is an important concept in quantum mechanics, based on the perturbation theory. You will only learn it later in QMIII, so we will need to postulate some important facts.*

Let's focus on the first crossing. The momentum near it is $k = \pi/a + \delta k$ and we have two copies of the original band structure coming together. One with $\psi_+ \propto e^{i\pi x/a}$, another with $\psi_- \propto e^{-i\pi x/a}$. Near the crossing the wave function is the linear superposition of $\psi_+$ and $\psi_-$: $\psi = \alpha \psi_+ + \beta \psi_-$. We actually used almost the same form of the wave function in LCAO, except instead of $\psi_\pm$ we used the orbitals $\phi_1$ and $\phi_2$ there.

Without the lattice potential we can approximate the Hamiltonian of these two states as follows:
$$H\begin{pmatrix}\alpha \\ \beta \end{pmatrix} = 
\begin{pmatrix} E_0 + v \hbar \delta k & 0 \\ 0 & E_0 - v \hbar \delta k\end{pmatrix}
\begin{pmatrix}\alpha \\ \beta \end{pmatrix}.
$$

Here we used $\delta p = \hbar \delta k$, and we expanded the quadratic function into a linear plus a small correction.  

??? question "calculate $E_0$ and the velocity $v$"
    The edge of the Brilloin zone has $k = \pi/a$. Substituting this in the free electron dispersion $E = \hbar^2 k^2/2m$ we get $E_0 = \hbar^2 \pi^2/2 m a^2$, and $v=\hbar p/m=\hbar \pi/ma$.

Without $V(x)$ the two wave functions $\psi_+$ and $\psi_-$ are independent since they have a different momentum. When $V(x)$ is present, it may couple these two states.

So in presence of $V(x)$ the Hamiltonian becomes

$$
H\begin{pmatrix}\alpha \\ \beta \end{pmatrix} = 
\begin{pmatrix} E_0 + v \hbar \delta k & W \\ W^* & E_0 - v \hbar \delta k\end{pmatrix}
\begin{pmatrix}\alpha \\ \beta \end{pmatrix},
$$

Here the coupling strength $W = \langle \psi_+ | V(x) | \psi_- \rangle$ is the matrix element of the potential between two states. *(This where we need to apply the perturbation theory, and this is very similar to the LCAO Hamiltonian)*.

??? question "how does our solution satisfy the Bloch theorem? What is $u(x)$ in this case?"
    The wave function has a form $\psi(x) = \alpha \exp[ikx] + \beta \exp[i(k - 2\pi/a)x]$
    (here $k = \pi/a + \delta k$). Choosing $u(x) = \alpha + \beta \exp(2\pi i x/a)$ we see
    that $\psi(x) = u(x) \exp(ikx)$.

#### Dispersion relation near the avoided level crossing

We need to diagonalize a 2x2 matrix Hamiltonian. The answer is
$$ E(\delta k) = E_0 \pm \sqrt{v^2\hbar^2\delta k^2 + |W|^2}$$

Check out section 15.1.1 of the book for the details of this calculation.

#### Physical meaning of $W$

Now we expand the definition of $W$:

$$W = \langle \psi_+ | V(x) | \psi_- \rangle = \int_0^{a} dx \left[e^{i\pi x/a}\right]^* V(x) \left[e^{-i\pi x/a}\right] = \int_0^a e^{2\pi i x /a} V(x) = V_1$$

Here $V_1$ is the first Fourier component of $V(x)$ (using a complex Fourier transform).

$$ V(x) = \sum_{n=-\infty}^{\infty} V_n e^{2\pi i n x/a}$$

#### Crossings between the higher bands

Everything we did applies to the crossings at higher energies, only there we would get higher Fourier components of $V(x)$: $V_2$ for the crossing between the second and third band, $V_3$ for the crossing between third and 4th, etc.

### Repeated vs reduced vs extended Brillouin zone

All different ways to **plot** the same dispersion relation (no difference in physical information).

Repeated BZ (all possible Bloch bands):

![](figures/nearly_free_electron_bands.svg)

* Contains redundant information
* May be easier to count/follow the bands

Reduced BZ (all bands within 1st BZ):

![](figures/reduced_nearly_free_electron_bands.svg)

* No redundant information
* Hard to relate to original dispersion

Extended BZ (n-th band within n-th BZ):

![](figures/extended_nearly_free_electron_bands.svg)

* No redundant information
* Easy to relate to free electron model
* Contains discontinuities

## Band structure

How are material properties related to the band structure?

For a material to be a conductor, there should be available electron states at the Fermi level. Otherwise all the states are occupied, and all the currents cancel out.

A band structure of a 1D material may look similar to this:

![](figures/band_structure_sketch.svg)

We see several **energy bands** that may be separated by a **band gap** or overlapping.

When the Fermi level lies in the band gap, the material is called a semiconductor (or dielectric or insulator). When the Fermi level is between different bands, it is a conductor (metal).

### A simple requirement for insulators

In an insulator every single band is either completely filled or completely empty.

How many electrons may an insulator have per unit cell? To answer this we need to integrate the density of states. Integrating $g(E)$ is hard, but integrating $\rho(k)$ is easy.

For a single band

$$ N = 2 \int_{BZ}dk_x dk_y dk_z [L\times W\times H] (2\pi)^{-3} = 2 LWH $$

So a single band has 2 electrons per unit cell (because of spin).

We come to the important rule:

> Any material with an odd number of electrons per unit cell is a metal.

If the material has an even number of electrons per unit cell it may be a semiconductor, but only if the bands are not overlapping (see the figure above). For example: Si, Ge, Sn all have 4 valence electrons. Si (silicon, band gap 1.14 eV) and Ge (germanium, band gap 0.67 eV) are semiconductors, Sn (tin) is a metal. **Interesting feature: the heaviest material is a metal, why?**

## Fermi surface using a nearly free electron model

Sequence of steps (same procedure as in 1D, but harder because of the need to imagine a 2D dispersion relation):

1. Compute $k_f$ using the free electron model (remember this is our starting point).
2. Plot the free electron model Fermi surface and the Brillouin zones.
3. Apply the perturbation where the Fermi surface crosses the Brillouin zone (due to avoided level crossings).

The resulting band structure looks like this (in the extended Brillouin zone scheme):

<iframe width="100%", height="600" src="../figures/nfem_2d.html" frameBorder="0" align="center" style="border:0;">Your browser still doesn't support iframes??</iframe>

Observe that the top of the first band is above the bottom of the lowest band. Therefore if $V$ is sufficiently weak, the material can be conducting even with 2 electrons per unit cell!

A larger $V$ makes the Fermi surface more distorted and eventually makes the material insulating.
Let's compare the almost parabolic dispersion of the nearly free electron model with a tight-binding model in 2D.

We now have a dispersion relation $E = E_0 + 2t(\cos k_x a + \cos k_y a)$, which looks like this:

<iframe width="100%", height="600" src="../figures/tb_2d.html" frameBorder="0" align="center" style="border:0;">Your browser still doesn't support iframes??</iframe>

### Light adsorption

Photons of external light can be reflected, transmitted, or adsorbed by the material. Adsorption, in turn requires energy transfer from the photon to electrons. In a filled band there are no available states where energy could be transferred (that's why insulators may be transparent).

When transition between two bands becomes possible due to photons having high energy, the adsorption increases in a step-like fashion, see the sketch below for germanium.

![](figures/adsorption.svg)

Here $E'_G\approx 0.9eV$ and $E_G\approx 0.8 eV$. The two steps visible steps are due to the special band structure of Ge:

![](figures/direct_indirect.svg)

The band structure has two band gaps: *direct*, the band gap at $k=0$, $E'_G$ and *indirect* gap $E_G$ at any $k$. In Ge $E_G > E'_G$, and therefore it is an *indirect band gap semiconductor*. Silicon also has an indirect band gap. Direct band gap materials are for example GaAs and InAs.

Photons carry very little momentum and a very high energy since $E = c \hbar k$ and $c$ is large. Therefore to excite electrons at $E_G$, despite a lower photon energy is sufficient, there is not enough momentum. Then an extra phonon is required. Phonons may have a very large momentum at room temperature, and a very low energy since atomic mass is much higher than electron mass.

A joint adsorbtion of a photon and a phonon collision may excite an electron across an indirect band gap, however this process is much less efficient, and therefore are much worse for optics applications (light emitting diodes, light sensors, etc).

## Summary

* In periodic potential all electron states are **Bloch waves**
* Electron dispersion is organized into **energy bands** that may overlap, or may be separated by **band gaps**
* If the lattice potential is weak, the dispersion can be obtained by copying $p^2/2m$ into different Brillouin zones, and opening gaps at every level crossing. Each gap is equal to the Fourier component of the lattice potential.
* If the number of electrons per unit cell is odd, the material must be conducting.
* Each band hosts $2N$ eletrons, therefore a material with odd number of electrons is a metal; that with an even number of electrons may be an insulator.
* Light adsorption is a tool to measure the band gap, and it distinguishes **direct** from **indirect** band gaps.
