
# Lecture 5 – Crystal structure and diffraction

_Based on chapters 12–14 of the book_

In this lecture we will:

- discuss how to classify crystal structures
- review some common crystal structures
- expand on the topics of reciprocal space and Brillouin zone
- consider diffraction experiments on crystals

### Crystal classification

- **_Lattice_**
    + periodic pattern of *lattice points*, which all have an identical view
    + lattice points are not necessarily the same as atom positions
    + there can be multiple atoms per lattice point
    + freedom of translation
    + multiple lattices with different point densities possible
- **_Lattice vectors_**
    + from lattice point to lattice point
    + $N$ vectors for $N$ dimensions
    + multiple combinations possible
    + not all combinations provide full coverage
- **_Unit cell_**
    + spanned by lattice vectors
    + has 4 corners in 2D, 8 corners in 3D
    + check if copying unit cell along lattice vectors gives full lattice
- **_Primitive unit cell_**
    + smallest possible $\rightarrow$ no identical points skipped
    + not always most practical choice
- **_Basis_**
    + only now we care about the contents (i.e. atoms)
    + gives element and position of atoms
    + properly count partial atoms $\rightarrow$ choose which belongs to unit cell
    + positions in terms of lattice vectors, *not* Cartesian coordinates!

### Example: graphite

![](figures/graphite_mod.svg)

1. Choose origin (can be atom, not necessary)
2. Find other lattice points that are identical
3. Choose lattice vectors, either primitive (red) or not primitive (blue)
    - lengths of lattice vectors and angle(s) between them fully define the crystal lattice
    - for graphite: $|{\bf a}_1|=|{\bf a}_2|$ = 0.246 nm = 2.46 Å, $\gamma$ = 60$^{\circ}$
4. Specify basis
    - using ${\bf a}_1$ and ${\bf a}_2$: C$(0,0)$, C$\left(\frac{2}{3},\frac{2}{3}\right)$
    - using ${\bf a}_1$ and ${\bf a}_{2}'$: C$(0,0)$, C$\left(0,\frac{1}{3}\right)$, C$\left(\frac{1}{2},\frac{1}{2}\right)$, C$\left(\frac{1}{2},\frac{5}{6}\right)$

An alternative type of unit cell is the _Wigner-Seitz cell_: the collection of all points that are closer to one specific lattice point than to any other lattice point. You form this cell by taking all the perpendicular bisectrices or lines connecting a lattice point to its neighboring lattice points.

### Stacking of atoms
What determines what crystal structure a material adopts? $\rightarrow$ To good approximation, atoms are solid incrompressible spheres that attract each other. How will these organize?

We start with the densest possible packing in 2D:
![](figures/packing.svg)
Will the second layer go on sites A, B or C?

ABCABC stacking $\rightarrow$ _cubic close packed_, also known as _face centered cubic_ (fcc):

![](figures/stacking.svg)

- One atom on the center of each side-plane: 'a dice that always throws 1'
- Conventional unit cell $\neq$ primitive unit cell
- Cyclic ABC $\rightarrow$ all atoms identical $\rightarrow$ 1 atom per primitive unit cell
- Conventional cell: $8\times\frac{1}{8}+6\times\frac{1}{2}=1+3=4$ atoms

Examples of fcc crystals: Al, Cu, Ni, Pb, Au and Ag.

### Filling factor
Filling factor = # of atoms per cell $\times$ volume of 1 atom / volume of cell

$=\frac{4\times\frac{4}{3}\pi R^3}{a^3}=\frac{1}{6}\sqrt{2}\pi\approx 0.74$, where we have used that $\sqrt{2}a=4R$.

Compare this to _body centered cubic_ (bcc), which consists of a cube with atoms on the corners and one atom in the center (Fig. 1.12): filling factor = 0.68. Examples of bcc crystals: Fe, Na, W, Nb.

Question: is 74% the largest possible filling factor? $\rightarrow$ Kepler conjecture (1571 – 1630). Positive proof by Hales _et al._ in 2015!

Crystal structures that are related to fcc:

1. ionic crystals (Fig. 1.13), e.g. NaCl
2. zincblende (Fig. 1.15), e.g. diamond

ABABAB stacking $\rightarrow$ _hexagonally close-packed_ (hcp), e.g. Co, Zn. In this case there is no cubic symmetry (Fig. 1.11).

### Miller planes
We start with a simple cubic lattice:

![](figures/cubic_mod.svg)

$|{\bf a}_1|=|{\bf a}_2|=|{\bf a}_3|\equiv a$ (_lattice constant_)

The plane designated by Miller indices $(u,v,w)$ intersects lattice vector ${\bf a}_1$ at $\frac{|{\bf a}_1|}{u}$, ${\bf a}_2$ at $\frac{|{\bf a}_2|}{v}$ and ${\bf a}_3$ at $\frac{|{\bf a}_3|}{w}$.

![](figures/miller.svg)

Miller index 0 means that the plane is parallel to that axis (intersection at "$\frac{|{\bf a}_3|}{0}=\infty$"). A bar above a Miller index means intersection at a negative coordinate.

If a crystal is symmetric under $90^\circ$ rotations, then $(100)$, $(010)$ and $(001)$ are physically indistinguishable. This is indicated with $\{100\}$. $[100]$ is a vector. In a cubic crystal, $[100]$ is perpendicular to $(100)$ $\rightarrow$ proof in problem set.

### Reciprocal lattice
For every real-space lattice

$$
{\bf R}=n_1{\bf a_1}+n_2{\bf a_2}+n_3{\bf a_3}
$$

where $n_1$, $n_2$ and $n_3$ are integers, there exists a reciprocal lattice

$$
{\bf G}=m_1{\bf b_1}+m_2{\bf b_2}+m_3{\bf b_3}
$$

where $m_1$, $m_2$ and $m_3$ are also integers.

_(Note that in previous years we used the notation $({\bf a},{\bf b},{\bf c}),({\bf a^*},{\bf b^*},{\bf c^*})$ instead of $({\bf a_1},{\bf a_2},{\bf a_3}),({\bf b_1},{\bf b_2},{\bf b_3})$.)_

The two lattices are related as follows:

$$
{\rm e}^{i{\bf G}\cdot{\bf R}}=1
$$

The above relation holds if

$$
{\bf a_i}\cdot{\bf b_i}=2\pi\delta_{ij}
$$

giving

$$
{\rm e}^{i{\bf G}\cdot{\bf R}}={\rm e}^{2\pi i(n_1 m_1 + n_2 m_2 + n_3 m_3)}
$$

which is clearly 1.

### Example of a two-dimensional reciprocal lattice

![](figures/reciprocal_mod.svg)

Compose reciprocal lattice vectors.
Directions:

${\bf a_1}\cdot{\bf b_2}=0\rightarrow{\bf a_1}\perp{\bf b_2}$

${\bf a_2}\cdot{\bf b_1}=0\rightarrow{\bf a_2}\perp{\bf b_1}$

Lengths: ${\bf a_1}\cdot{\bf b_1}={\bf a_2}\cdot{\bf b_2}=2\pi$

$|{\bf b_1}|=\frac{2\pi}{|{\bf a_1}|{\rm cos}30^\circ}=\frac{4\pi}{|{\bf a_1}|\sqrt{3}}$, $|{\bf b_2}|=\frac{2\pi}{|{\bf a_2}|{\rm cos}30^\circ}=\frac{4\pi}{|{\bf a_2}|\sqrt{3}}$

Normalization is arbitrary in reciprocal space.

The reciprocal lattice vectors can be composed directly from their real-space counterparts:

$$
{\bf b_1}=\frac{2\pi({\bf a_2}\times{\bf a_3})}{ {\bf a_1}\cdot({\bf a_2}\times{\bf a_3})}
$$

$$
{\bf b_2}=\frac{2\pi({\bf a_3}\times{\bf a_1})}{ {\bf a_1}\cdot({\bf a_2}\times{\bf a_3})}
$$

$$
{\bf b_3}=\frac{2\pi({\bf a_1}\times{\bf a_2})}{ {\bf a_1}\cdot({\bf a_2}\times{\bf a_3})}
$$

Note that the denominator is the volume of the real-space unit cell. These definitions are cyclic, because ${\bf a_1}\cdot({\bf a_2}\times{\bf a_3})={\bf a_2}\cdot({\bf a_3}\times{\bf a_1})={\bf a_3}\cdot({\bf a_1}\times{\bf a_2})$.

The reciprocal lattice can also be described as a Fourier transform. We imagine the real-space lattice as a density function consisting of delta peaks, first in 1D:

$$
\rho(r)=\sum_{n} \delta(r-na)
$$

We take the Fourier transform of this function to find:

$$
{\mathcal F}_{k}\left[\rho(r)\right]=\int {\rm d}r\ {\rm e}^{ikr} \rho(r)=\sum_{n} \int {\rm d}r\ {\rm e}^{ikr} \delta(r-na)=\sum_{n} {\rm e}^{ikna}
$$

This sum is non-zero only if $k=2\pi m/a$, so when $k$ is in a recoprocal lattice point. Therefore, it can be rewritten as:

$$
{\mathcal F}_{k}\left[\rho(r)\right]=\frac{2\pi}{|a|}\sum_{m} \delta\left(k-\frac{2\pi m}{a}\right)
$$

The above can be generalized to three dimensions:

$$
{\mathcal F}_{\bf k}\left[\rho({\bf r})\right]=\int {\rm d}{\bf r}\ {\rm e}^{i{\bf k}\cdot{\bf r}} \rho({\bf r})
$$

### Periodicity of the reciprocal lattice
Any wave in a crystal with wave vector ${\bf k}$ can also be described with wave vector ${\bf k'}={\bf k}+{\bf G}_0$, where ${\bf G}_0=h{\bf b_1}+k{\bf b_2}+l{\bf b_3}$.

A primitive unit cell of the reciprocal lattice contains a set of unique ${\bf k}$ vectors. Convention: _1st Brillouin zone_. All ${\bf k}$ vectors outside the 1st BZ have a copy inside the 1st BZ. So any wave process with arbitrary ${\bf k}$ can be described inside the 1st BZ.

![](figures/brillouin_mod.svg)

The 1st Brillouin zone = the Wigner Seitz cell of the reciprocal lattice.

### Diffraction
We will now discuss how incoming waves incident onto a crystal can be scattered by the lattice. These waves can be x-rays, neutrons or electrons.

We assume that the incoming wave has wave vector ${\bf k}$ and the scattered wave has wave vector ${\bf k'}$. Furthermore, we assume only elastic scattering, meaning that $|{\bf k'}|=|{\bf k}|$. In this case, a scattering atom at position ${\bf r}$ can be seen as a radiation sources emitting a wave ${\rm e}^{i\left(({\bf k'}-{\bf k})\cdot{\bf r}-\omega t\right)}$. A complete atomic lattice ${\bf R}$ will then emit a total wave amplitude:

$$
A\propto\sum_{\bf R}{\rm e}^{i\left(({\bf k'}-{\bf k})\cdot{\bf R}-\omega t\right)}
$$

We find that this sum will only yield a finite value if:

$$
{\bf k'}-{\bf k}={\bf G}
$$

in other words, if the difference between the outgoing and incoming wave vectors coïncides with a reciprocal lattice point. We can then expect constructive interference due to the lattice points. This requirement is known as the _Laue condition_. Note that the total intensity measured by the detector goes like $I\propto A^2$.

![](figures/laue_mod.svg)

In the above we have assumed that at each lattice point there is one single atom. But what if there are multiple atoms per unit cell? In that case each atom acquires a phase shift of its own and the total amplitude becomes:

$$
A\propto\sum_{\bf R}{\rm e}^{i\left({\bf G}\cdot{\bf R}-\omega t\right)}\sum_j f_j\ {\rm e}^{i{\bf G}\cdot{\bf r}_j}
$$

where $f_j$ is a phenomenological form factor that may be different for atoms of different elements. The second sum is called the _structure factor_:

$$
S({\bf G})=\sum_j f_j\ {\rm e}^{i{\bf G}\cdot{\bf r}_j}
$$

The structure factor can cause destructive interference due to the contents of the unit cell, even though the Laue condition is met. Examples:

- Simplest case: 1 atom at each lattice point, ${\bf r}_1=(0,0,0)\rightarrow S=f_1$. In this case each reciprocal lattice point gives one interference peak, none of which is cancelled.
- Example 2: conventional cell of the fcc lattice.

![](figures/fcc_mod.svg)

Basis contains 4 identical atoms:

$$
\begin{aligned}
{\bf r}_1&=(0,0,0)\\
{\bf r}_2&=\frac{1}{2}({\bf a}_1+{\bf a}_2)\\
{\bf r}_3&=\frac{1}{2}({\bf a}_2+{\bf a}_3)\\
{\bf r}_4&=\frac{1}{2}({\bf a}_3+{\bf a}_1)\\
f_1&=f_2=f_3=f_4\equiv f
\end{aligned}
$$

$$
\begin{aligned}
{\bf G}&=h{\bf b}_1+k{\bf b}_2+l{\bf b}_3\\
S&=f\left({\rm e}^{i{\bf G}\cdot{\bf r}_1}+{\rm e}^{i{\bf G}\cdot{\bf r}_2}+{\rm e}^{i{\bf G}\cdot{\bf r}_3}+{\rm e}^{i{\bf G}\cdot{\bf r}_4}\right)\\
&=f\left(1+{\rm e}^{i/2(h{\bf b}_1\cdot{\bf a}_1+k{\bf b}_2\cdot{\bf a}_2)}+{\rm e}^{i/2(k{\bf b}_2\cdot{\bf a}_2+l{\bf b}_3\cdot{\bf a}_3)}+{\rm e}^{i/2(h{\bf b}_1\cdot{\bf a}_1+l{\bf b}_3\cdot{\bf a}_3)}\right)\\
&=f\left(1+{\rm e}^{-i\pi(h+k)}+{\rm e}^{-i\pi(k+l)}+{\rm e}^{-i\pi(h+l)}\right)
\end{aligned}
$$

Parameters $h$, $k$, $l$ are integers $\rightarrow$ all terms are either $+1$ or $-1$ $\rightarrow$ puzzle. Solution:

$S=4f$ if $h$, $k$, $l$ are all even or all odd

$S=0$ in all other cases
