# Lecture 8 – Magnetism

_Based on chapters 19 and 20 of the book_

In this lecture we will:

- discuss common forms of magnetism
- introduce magnetic susceptibility
- discuss Hund's rules
- discuss magnetic order

### Magnetic field
To start off confusing, there are two different quantities that are often referred to as the _magnetic field_: the ${\bf B}$-field (in units of Tesla) and the ${\bf H}$-field (in A/m). In vacuum, they are proportional:

$$
{\bf B}=\mu_0 {\bf H}
$$

with $\mu_0$ the permeability of free space. Technically, inside a material they differ. Here, ${\bf B}$ is the total magnetic field that one can measure locally, while ${\bf H}$ is the same, but corrected for the magnetisation:

$$
{\bf B}=\mu_0({\bf H}+{\bf M}),\ {\rm or}\ \ {\bf H}=\frac{\bf B}{\mu_0}-{\bf M}
$$

where ${\bf M}$ is the _magnetisation_. In other words, ${\bf B}$ is the field due to free currents and 'bound currents' (i.e. local magnetised moments) while ${\bf H}$ is the field due only to free currents. But in practice, ${\bf M}$ is small compared to ${\bf H}$, so we always assume ${\bf B}=\mu_0 {\bf H}$.

### Magnetic susceptibility
The _susceptibility_ $\chi$ is the extent to which a material is prone to magnetisation:

$$
{\bf M}=\chi{\bf H}=\chi\frac{\bf B}{\mu_0}
$$

Depending on the sign, you can get different forms of magnetism:

$\chi>0\Rightarrow$ _paramagnetism_: the material tends to magnetise along the local field.

$\chi<0\Rightarrow$ _diamagnetism_: the material tends to magnetise opposite to the local field.

Further on, we will discuss two forms of spontaneous magnetisation: _ferromagnetism_ and _anti-ferromagnetism_. Unlike the ones mentioned above, these forms persist even in the absense of a magnetic field.

### Hund's rules
We discussed before that the magnetic configuration of electrons in an atomic orbital can be described with four quantum numbers: $n$, $l$, $l_z$ and $\sigma_z$. Question is: how do these spin and orbital momental align inside the atom? There are various mechanism governing this, but the results can be summarized in three _Hund's rules_:

- Rule 1: Maximise $S$.
- Rule 2: Maximise $L$ (provided that rule 1 is satisfied).
- Rule 3: For shells less than half filled: $J=|L-S|$. For shells more than half filled: $J=L+S$.

Examples:

- Fe = [Ar]4s$^2$3d$^6$

$S=2$, $L=2$, $J=4$ $\Rightarrow$ $^{2S+1}L_J =\ ^5{\rm D}_4$

- V = [Ar]4s$^2$3d$^3$

$S=\frac{3}{2}$, $L=3$, $J=\frac{3}{2}$ $\Rightarrow$ $^{2S+1}L_J =\ ^4{\rm F}_{3/2}$

![](figures/hund.svg)

### Paramagnetism: free spin $\frac{1}{2}$
If single electron spin ${\bf \sigma}$ is situated in a magnetic field ${\bf B}$, it can be described by the Zeeman Hamiltonian (note convention minus sign):

$$
{\mathcal H}=g\mu_{\rm B}{\bf B}\cdot{\bf \sigma}
$$

where $\mu_{\rm B}=\frac{e\hbar}{2m_{\rm e}}=10^{-23}$ J/T is the _Bohr magneton_ and $g$ is the _g-factor_, which for an electron is almost exactly 2. Its two eigenstates are $+\mu_{\rm B}B$ and $-\mu_{\rm B}B$.
Now using the Bolzmann weights we compute the expectation value of the magnetisation of $n$ spins:

$$
M = -n \frac{ \mu_{\rm B}{\rm e}^{-\beta\mu_{\rm B}B}-\mu_{\rm B}{\rm e}^{+\beta\mu_{\rm B}B} }{ {\rm e}^{-\beta\mu_{\rm B}B}+{\rm e}^{+\beta\mu_{\rm B}B}}
= n\mu_{\rm B}{\rm tanh}(\beta\mu_{\rm B}B)
$$

For small $B$ this function is linear, allowing us to extract the susceptibility

$$
\chi=\mu_0\frac{{\rm d}M}{{\rm d}B}\approx\frac{n\mu_0 \mu_{\rm B}^2}{k_{\rm B}T}=\frac{C}{k_{\rm B}T}
$$

with $C$ a constant. This is known as the _Curie law_, and it shows that at high temperature a paramagnetic material becomes less susceptible to magnetisation.

![](figures/curie.svg)

### Paramagnetism: free spin $J$
For an atom with magnetic moments $L$ and $S$ the Hamiltonian will become:

$$
{\mathcal H}=\mu_{\rm B}{\bf B}\cdot\left({\bf L}+g{\bf S}\right)
$$

This can be written in terms of the total magnetic moment ${\bf J}$ using the _Landé factor_ $\tilde{g}\ $:

$$
{\mathcal H}=\tilde{g}\ \mu_{\rm B}{\bf B}\cdot{\bf J}
$$

with

$$
\tilde{g}\ =\frac{1}{2}(g+1)+\frac{1}{2}(g-1)\left[\frac{S(S+1)-L(L+1)}{J(J+1)}\right]=\frac{3}{2}-\frac{L(L+1)-S(S+1)}{2J(J+1)}
$$

The result is a ladder of equally spaced levels. The bigger the contribution of $S$ inside $J$, the bigger te level spacing. Now, the magnetisation for $n$ atoms becomes:

$$
M=-n\frac{\sum_{m_{J}=-J}^{J}\tilde{g}\ \mu_{\rm B}m_{J}{\rm e}^{-\beta\mu_{\rm B}m_J B}}{\sum_{m_{J}=-J}^{J}{\rm e}^{-\beta\mu_{\rm B}m_J B}}
$$

The resulting susceptibility is:

$$
\chi=\frac{n\mu_0(\tilde{g}\ \mu_{\rm B})^2}{3}\frac{J(J+1)}{k_{\rm B}T}
$$

### Atoms in solids
Until now we have considered magnetic atoms in free space. When embedded inside a solid, many things change. Below, we will discuss two effects:

- Interaction of magnetic atoms with other magnetic atoms $\Rightarrow$ _Heisenberg model_
- Interaction of spins with non-magnetic atoms $\Rightarrow$ _Crystal field_

### Heisenberg model
Consider a one-dimensional chain of spins $\frac{1}{2}$ that are nearest-neighbor coupled with equal coupling strength $J$:

$$
{\mathcal H}=-\frac{1}{2}J\sum_{\langle i,j \rangle} {\bf S}_i\cdot{\bf S}_j+\sum_i g\mu_{\rm B}{\bf B}\cdot{\bf S}_i=\sum_i \left( -J{\bf S}_i\cdot{\bf S}_{i+1}+ g\mu_{\rm B}{\bf B}\cdot{\bf S}_i \right)
$$

#### Ferromagnetism
Let's assume ${\bf B}=0$ for now. When $J>0$, the spins tend to align and form a _ferromagnet_. In this case, $\left|\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\right\rangle$ and $\left|\downarrow\downarrow\downarrow\downarrow\downarrow\downarrow\right\rangle$ are both valid eigenstates. The order parameter is the total magnetisation $M=\sum_i S_z^i$.

#### Antiferromagnetism
When $J<0$, the term favors anti-alignment, leading to _antiferromagnetism_. Antiferromagnets typically have zero magnetization, so we need a different order parameter. We can define the _staggered magnetization_ $\tilde{M} = \sum_i (-1)^i S_z^i$, which will become finite if there is alternating order.

Surprisingly, the so-called _Néel states_ $\left|\uparrow\downarrow\uparrow\downarrow\uparrow\downarrow\right\rangle$ and $\left|\downarrow\uparrow\downarrow\uparrow\downarrow\uparrow\right\rangle$ are _not_ eigenstates of the Heisenberg Hamiltonian. This can be seen as follows:

$$
{\mathcal H}=-J\sum_i{\bf S}_i\cdot{\bf S}_{i+1}=-J\sum_i \left( S_x^i S_x^{i+1}+S_y^i S_y^{i+1}+S_z^i S_z^{i+1} \right)
$$

Using $S_x=\frac{S_{+}+S_{-}}{2}$ and $S_y=\frac{S_{+}-S_{-}}{2i}$, we can rewrite this as:

$$
{\mathcal H}=-J\sum_i\left(\frac{S_+S_+ + S_+S_- + S_-S_+ + S_-S_-}{4}-\frac{S_+S_+ - S_+S_- - S_-S_+ + S_-S_-}{4}+S_zS_z\right)\\
=-J\sum_i\left(\frac{S_+S_-}{2}+\frac{S_-S_+}{2}+S_zS_z\right)
$$

#### Frustration
Finding the correct behavior of the $J<0$ Heisenberg chain is a challenge, both theoretically and experimentally. As particularly fascinating situation arises if there is _frustration_, where no configuration of the spins can satisfy all bonds (Fig. 20.2). For just three spins the ground state can still be worked out (see Problem 20.2), but nobody knows what happens in large frustrated spin systems.

#### Forms of coupling
Why do spins sometimes prefer to align and sometimes prefer to anti-align? The most obvious explanation is dipolar interaction. But if we estimate the dipolar interaction between two moments $\mu_{\rm B}$ at a distance of 3 Å, we find:

$$
\Delta E\sim \mu_B B_{\rm dipolar} \sim \frac{\mu_0\mu_{\rm B}^2}{4\pi r^3} \sim 2\ \mu{\rm eV}
$$

This corresponds to a thermal energy of only ~20 mK! Therefore, other mechanism must be responsible for magnetic ordering:

- _Exchange interaction_ – The total wavefunction of two electrons needs to be antisymmetric upon exchange:

$$
\psi({\bf r}_1,{\bf r}_2,{\bf s}_1,{\bf s}_2)=-\psi({\bf r}_2,{\bf r}_1,{\bf s}_2,{\bf s}_1)
$$

Coulomb interaction favors symmetric spatial wavefunction, resulting in a preferred antisymmetric spin wavefunction $\Rightarrow J>0$.

- _Superexchange interaction_ – When magnetic atoms are connected via one non-magnetic mutual neighbor, simultaneous exchange of electrons with the neighbor can favor anti-alignment $\Rightarrow J<0$.

![](figures/superexchange.svg)

- _Ruderman-Kittel-Kasuya-Yosida (RKKY) interaction_ - Coupling of magnetic atoms via the itinerant electrons inside a metal can lead to an oscillating behavior of $J$ as a function of separation.

![](figures/RKKY.svg)

### Crystal field

For a free atom, the orbitals are spherically symmetric (_spherical harmonics_). Inside a crystal, it can happen that, due to the Coulomb interaction with neighboring non-magnetic atoms, the degeneracy between orbitals is broken.
As a result, electrons can no longer complete a full circular orbit around an atom, causing the orbital angular momentum to be _quenched_: ${\bf L}\Rightarrow 0$.

![](figures/crystalfield.svg)

The remaining spin ${\bf S}$ can favor certain directions for magnetisation (due to spin-orbit coupling). This can be expressed in the Heisenberg Hamiltonian as:

$$
{\mathcal H}=\sum_i \left( -J{\bf S}_i\cdot{\bf S}_{i+1}+ g\mu_{\rm B}{\bf B}\cdot{\bf S}_i -\kappa(S_i^z)^2 \right)
$$

If $S>\frac{1}{2}$, e.g. $S=2$, in this case the $S_z = \pm 2$ states will be favored. This is called _crystal field anisotropy_. If the anisotropy becomes very large, it makes sense to reduce the system to just the $S_z = \pm S$ subspace. This is called the _Ising model_:

$$
{\mathcal H}=\sum_i \left( -J \sigma_i \sigma_{i+1}+ g\mu_{\rm B}B\sigma_i\right)
$$

where $\sigma_i=\pm S$.