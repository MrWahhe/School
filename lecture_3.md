
# Atoms and bonds

## Looking back

So far we have:

* Introduced the $k$-space (reciprocal space)
* Postulated electron and phonon dispersion relations

As a result we:

* Understood how phonons store heat (Debye model)
* Understood how electrons conduct (Drude model) and store heat/energy (Sommerfeld model)

We used our best guess as a starting point, and there are several mysteries:

* Why is there a cutoff frequency? Why are there no more phonon modes?
* Why do electrons not scatter off from every single atom in the Drude model? Atoms are charged and should provide a lot of scattering.
* Why are some materials not metals? (Think if you know a crystal that isn't a metal)

## A quick review of atoms

### Why chemistry is not physics

> Chemists are merely solving the Schrödinger equation, they are a domain in physics  
> —An arrogant physicist

**Everything** is described by the Schrödinger equation:

$$H\psi = E\psi,$$

with $H$ the sum of kinetic energy and Coulomb interaction, so for hydrogen we have:

$$H=-\hbar^2\frac{\partial^2}{2m\partial {\mathbf r^2}} - \frac{e^2}{4\pi\varepsilon_0|r|}$$

for helium it becomes more complex: $\psi({\mathbf r})\rightarrow \psi({\mathbf {r_1, r_2}})$, so

$$H=-\hbar^2\frac{\partial^2}{2m\partial {\mathbf r_1^2}} -\hbar^2\frac{\partial^2}{2m\partial {\mathbf r_2^2}}- \frac{2e^2}{4\pi\varepsilon_0|r_1|} - \frac{2e^2}{4\pi\varepsilon_0|r_2|} + \frac{e^2}{4\pi\varepsilon_0|r_1 - r_2|},$$

which means we need to find eigenvalues and eigenvectors of a 6-dimensional differential equation!

"Mundane" copper has 29 electrons, so to find the electronic spectrum of Copper we would need to solve an 87-dimensional Schrödinger equation, and there is no way in the world we can do so.

This exponential growth in complexity with the number of interacting quantum particles is why *many-body quantum physics* is very much an open area in solid state physics.

However we need to focus on what is possible to do, and apply heuristic rules based on the accumulated knowledge of how atoms work (hence we will need a bit of chemistry).

### Quantum numbers and shell filling

Single electron states have 4 quantum numbers: $|n, l, l_z, \sigma\rangle$

![](figures/single_atom.svg)

Quantum numbers:

* $n=1,2,\ldots$ is the azimuthal (principal) quantum number
* $l=0, 1, \ldots, n-1$ is the angular momentum (also known as $s, p, d, f$ orbitals)
* $l_z=-l, -l+1\ldots, l$ is the $z$-component of angular momentum
* $\sigma$ is the spin

It turns out that electrons in all atoms occupy these orbitals, only the energies are very different.

* Aufbau principle: *first fill a complete shell (all electrons with the same $n, l$) before going to the next one*
* Madelung's rule: *first occupy the shells with the lowest $l+n$, and of those with equal $l+n$ those with smaller $n$*

Therefore shell-filling order is 1s, 2s, 2p, 3s, 3p, 4s, 4d, ...

The electrons in the outermost shell are the only ones participating in chemical reactions and electric conduction.
The rest provides a negatively charged cloud that reduces the attraction to the atomic nucleus.

## Covalent bonds and linear combination of atomic orbitals

*Here we present the material in the order different from the book because the covalent bonds are most important for the exercises*

### Two atoms

Consider two atoms next to each other.

Since different orbitals of an atom are separated in energy, we consider one orbital per atom (even though this is often a bad starting point and it should only work for $s$-orbitals).

Let's imagine that the atoms are sufficiently far apart, so that the shape of the orbitals or the energy of the orbitals doesn't change much.

If $\phi_1$ is the wave function of an electron bound to the first atom, and $\phi_2$ is the wave function of the electron near the second atom, we will search for a solution in form: $\psi = c_{1} \phi_{1} + c_{2} \phi_{2}$, or in other words as a *Linear Superposition of Atomic Orbitals (LCAO)*.

For simplicity let's assume now that $\langle\phi_1|\phi_2\rangle=0$, so that $\psi$ is normalized whenever $|c_1|^2 + |c_2|^2 = 1$. (See exercises for relaxing this assumption)

Acting with the Hamiltonian on the LCAO wave function we get an eigenvalue problem:

$$ E \begin{pmatrix} c_1 \\ c_2 \end{pmatrix}
= \begin{pmatrix}
\langle \phi_1|H|\phi_1\rangle & \langle \phi_1|H|\phi_2\rangle \\ \langle \phi_2|H|\phi_1\rangle & \langle \phi_2|H|\phi_2\rangle
\end{pmatrix}\begin{pmatrix} c_1 \\ c_2\end{pmatrix}$$

$\langle \phi_1|H|\phi_1\rangle \equiv E_0$ is the **onsite energy**, $\langle \phi_1|H|\phi_2\rangle \equiv t$ is the **hopping integral** (or just **hopping**).

Since we are considering bound states, the $\phi_n$ are purely real ⇒ $t$ is real as well.

$$ H = \begin{pmatrix} E_0 & t \\ t & E_0 \end{pmatrix}$$

Eigenstates & eigenvalues:  
$\psi_+ = \tfrac{1}{\sqrt{2}}(\phi_1 + \phi_2)$ [even/symmetric superposition with $E_+ = E_0 + t$];  
$\psi_- = \tfrac{1}{\sqrt{2}}(\phi_1 - \phi_2)$ [odd/antisymmetric superposition with $E_- = E_0 - t$].

Two atoms are a molecule, and $\psi_+$ and $\psi_-$ are **molecular orbitals**.

An even superposition has a lower kinetic energy (derivative is smaller) ⇒ $t$ is negative.

![](figures/two_atoms.svg)

### Bonding vs antibonding

Hopping $t$ grows when the atoms are moved together because the overlap. Let's plot energy of molecular orbitals vs inter-atomic distance.

![](figures/bonding.svg)

When $\psi_+$ is occupied by an electron, it makes the atoms attract (or *bond*) because the total energy is lowered. It is therefore called a **bonding orbital**.

An occupied $\psi_-$ increases the molecule energy as the atoms move closer ⇒ it makes atoms repel, and it is an **antibonding orbital**.

Therefore if each atom has a single electron in the outermost shell, these atoms attract, if there are 0 or 2 electrons, the net electron force cancels (but electrostatic repulsion remains).

## Adding repulsion

If bringing two atoms closer would keep increasing energy, any covalent bond would collapse; eventually the two atoms must start repelling (at least when the nuclei get close, but really already much earlier).

![](figures/bonding_with_repulsion.svg)

### Van der Waals bond

*Not our focus, but we will discuss it for completeness*

Originates from attraction between dipole moments of two atoms:

If one atom has a dipole moment $p_1$, it creates electric field

$$ E = \frac{p_1}{4\pi \varepsilon_0 r^3} $$

at the position of another atom. The other atom then develops a dipole moment $p_2 = \chi E$ with $\chi$ the *polarizability* of the atom.

This results in an attractive potential $U(r) = -E p_2 \sim r^{-6}$.

This attraction is much weaker than covalent bonds but drops slower with increasing distance. (Q: how fast does the interaction of covalent bonds drop?)

Van der Waals bonds hold layers of covalently bonded carbon atoms together when forming graphite:

![Graphite atomic layers](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Graphite-layers-side-3D-balls.png/320px-Graphite-layers-side-3D-balls.png)  
(image source: Wikipedia)

## First steps towards phonons

The atomic interaction is minimized when the distance between the atoms is at the minimum of the potential: $U = U_0$ when $\delta r = a$.

![](figures/interatomic_interaction.svg)

Near the minimum, the potential is approximately parabolic:

$$
U = U_0 + \frac{\kappa}{2} (\delta r - a)^2 - \frac{\kappa_3}{3!} (\delta r - a)^3 + \ldots
$$

This is a harmonic oscillator potential with the higher order term $\kappa_3$ providing anharmonicity.

### Rigidity

If we stretch a material with length $L$ containing $N=L/a$ atoms by a lenght $\delta L$, the displacement of each atom is $\delta r - a = \delta L/N$.

The returning force is

$$
F = - \frac{d U}{d(\delta r)} (\delta r - a) = \kappa a \delta L / L,
$$

which leads us to the material *compressibility*

$$
\beta \equiv -\frac{1}{L} \frac{\partial L}{\partial F} = \frac{1}{\kappa a}.
$$

Then using compressibility we can derive the wave equation and obtain the speed of sound in the material relating it to the bond strength.

### Thermal expansion

The nonlinearity $\kappa_3$ means that the potential grows slower when the atoms are further apart than when they are closer to each other.

Therefore the larger the energy of the atoms, the more their average distance increases $\Rightarrow$ we have a model of thermal expansion.

## Looking ahead: multiple atoms

Our aim is to understand electrons and phonons in solids containing $N\to\infty$ atoms.

We now have a microscopic model of what happens when there are two atoms; let's try to see what happens when we take several.

### Phonons

Our plan:

* Consider only *harmonic potential* acting between atoms
* Write down equations of motion
* Compute normal modes

For simplicity we consider 1D motion, and let's start with 3 atoms:

![](figures/phonons2.svg)

Newton's equations of motion:

$$
\begin{aligned}
m \ddot{x}_1 &= - \kappa (x_1 - x_2) \\
m \ddot{x}_2 &= -\kappa (x_2 - x_1) -\kappa (x_2 - x_3) \\
m \ddot{x}_3 &= - \kappa (x_3 - x_2)
\end{aligned},
$$

Or in matrix form:

$$
m \ddot{x} = -\kappa
\begin{pmatrix}
1 & -1 & 0\\
-1 & 2 & -1\\
0 & -1 & 1
\end{pmatrix}x
$$

We search for *normal modes*: patterns of motion that are periodic and have a fixed frequency: $x(t) = x_0 e^{i\omega t}$.

Substituting into the equations of motion we get an eigenvalue problem:

$$
\omega^2 x_0 = \sqrt{\frac{\kappa}{m}}
\begin{pmatrix}
1 & -1 & 0\\
-1 & 2 & -1\\
0 & -1 & 1
\end{pmatrix}x_0.
$$

The solutions of this eigenvalue problem are the phonon modes that we occupy.

### Electrons

Same as a single covalent bond, only more atoms in a line. Considering 3 atoms:

$$
E \begin{pmatrix}
c_1 \\ c_2 \\ c_3
\end{pmatrix} = 
\begin{pmatrix}
E_0 & t & 0 \\
t & E_0 & t \\
0 & t & E_0
\end{pmatrix}
\begin{pmatrix}
c_1 \\ c_2 \\ c_3
\end{pmatrix}
$$

### Numerical test

Diagonalizing large matrices is unwieldy, but let's try and check it numerically to see if we notice a trend.

Eigenfrequencies of 3 atoms: `[0.0 1.0 1.732050]`

![](figures/3_phonons.svg)

Energies of 3 orbitals: `[-1.41421356 0.0  1.41421356]`

![](figures/3_electrons.svg)

### From 3 atoms to 300

Frequencies of many phonons:

![](figures/300_phonons.svg)

Energies of many electrons:

![](figures/300_electrons.svg)

## Summary

* Electrons in atoms occupy "shells" in the energetically favorable order
* When two atoms come close, electrons occupy molecular orbitals and bind atoms together.
* Motion of electrons makes atoms attract
* Oscillatory motion of atoms and hopping of electrons between atoms give rise to the macroscopic behavior of the materials (next week)
