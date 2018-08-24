
# Lecture 2 – Free electron model
_Based on chapters 3 and 4 of the book_

In this lecture we will:

- consider electrons as charged point particles travelling through a solid
- discuss Drude theory
- discuss the Hall experiment
- discuss specific heat of a solid based due to electrons
- introduce mobility, Hall resistance and the Fermi energy

### Drude theory
Ohm's law states that $V=IR=I\rho\frac{l}{A}$. In this lecture we will investigate where this law comes from. We will use the theory developed by Paul Drude in 1900, which is based on three assumptions:

- Electrons have an average scattering time $\tau$.
- At each scattering event an electron returns to momentum ${\bf p}=0$.
- In-between scattering events electrons respond to the Lorentz force ${\bf F}_{\rm L}=-e\left({\bf E}+{\bf v}\times{\bf B}\right)$.

For now we will consider only an electric field (_i.e._ ${\bf B}=0$). What velocity do electrons acquire in-between collisions?

$$
{\bf v}=-\int_0^\tau\frac{e{\bf E}}{m_{\rm e}}{\rm d}t=-\frac{e\tau}{m_{\rm e}}{\bf E}=-\mu{\bf E}
$$

Here we have defined the quantity $\mu\equiv e\tau/m_{\rm e}$, which is the _mobility_. If we have a density $n$ of electrons in our solid, the current density ${\bf j}$ [A/m$^2$] then becomes:

$$
{\bf j}=-en{\bf v}=\frac{n e^2\tau}{m_{\rm e}}{\bf E}=\sigma{\bf E}\ ,\ \ \sigma=\frac{ne^2\tau}{m_{\rm e}}=ne\mu
$$

$\sigma$ is the conductivity, which is the inverse of resistivity: $\rho=\frac{1}{\sigma}$. If we now take $j=\frac{I}{A}$ and $E=\frac{V}{l}$, we retrieve Ohm's Law: $\frac{I}{A}=\frac{V}{\rho l}$.

Scattering is caused by collisions with:

- Phonons: $\tau_{\rm ph}(T)$ ($\tau_{\rm ph}\rightarrow\infty$ as $T\rightarrow 0$)
- Impurities/vacancies: $\tau_0$

Scattering rate $\frac{1}{\tau}$:

$$
\frac{1}{\tau}=\frac{1}{\tau_{\rm ph}(T)}+\frac{1}{\tau_0}\ \Rightarrow\ \rho=\frac{1}{\sigma}=\frac{m}{ne^2}\left( \frac{1}{\tau_{\rm ph}(T)}+\frac{1}{\tau_0} \right)\equiv \rho_{\rm ph}(T)+\rho_0
$$

![](figures/matthiessen.svg)

_Matthiessen's Rule_ (1864). Solid (dashed) curve: $\rho(T)$ for a pure (impure) crystal.

How fast do electrons travel through a copper wire? Let's take $E$ = 1 volt/m, $\tau$ ~ 25 fs (Cu, $T=$ 300 K).

$\rightarrow v=\mu E=\frac{e\tau}{m_{\rm e}}E=\frac{10^{-19}\times 2.5\times 10^{-14}}{10^{-30}}=2.5\times10^{-3}=2.5$ mm/s ! (= 50 $\mu$m @ 50 Hz AC)

### Hall effect
Consider a conductive wire in a magnetic field ${\bf B} \rightarrow$ electrons are deflected in a direction perpendicular to ${\bf B}$ and ${\bf j}$. 

![](figures/hall_effect.svg)

${\bf E}_{\rm H}$ = _Hall voltage_, caused by the Lorentz force.

In equilibrium, assuming that the average velocity becomes zero after every collision: $\frac{mv_x}{\tau}=-eE$

The $y$-component of the Lorentz force $-e{\bf v}_x\times{\bf B}$ is being compensated by the Hall voltage ${\bf E}_{\rm H}={\bf v}_x\times{\bf B}=\frac{1}{ne}{\bf j}\times{\bf B}$. The total electric field then becomes

$$
{\bf E}=\left(\frac{1}{ne}{\bf j}\times{\bf B}+\frac{m}{ne^2\tau}{\bf j}\right)
$$

We now introduce the _resistivity matrix_ $\tilde{\rho}$ as ${\bf E}=\tilde{\rho}{\bf j}$, where the diagonal elements are simply $\rho_{xx}=\rho_{yy}=\rho_{zz}=\frac{m}{ne^2\tau}$. The off-diagonal element $\rho_{xy}$ gives us:

$$
\rho_{xy}=\frac{B}{ne}\equiv -R_{\rm H}B
$$

where $R_{\rm H}=-\frac{1}{ne}$ is the _Hall resistance_. So by measuring the Hall resistance, we can obtain $n$, the density of free electrons in a material.

While most materials have $R_{\rm H}>0$, interestingly some materials are found to have $R_{\rm H}<0$. This would imply that the charge carriers either have a positive charge, or a negative mass. We will see later (chapter 17) how to interpret this.

### Sommerfeld theory (free electron model)
Atoms in a metal provide conduction electrons from their outer shells (often s-shells). These can be described as waves in the crystal, analogous to phonons. Hamiltonian of a free electron:

$$
\mathcal{H}=\frac{ {\bf p}^2}{2m}=-\frac{\hbar^2}{2m}\left( \frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2} \right)\ \Rightarrow\ \varepsilon=\frac{\hbar^2}{2m}\left( k_x^2+k_y^2+k_z^2 \right)
$$

Take periodic boundary conditions: $\psi(x,y,z)=\psi(x+l,y+L,z+L)$:

$$
k_x=\frac{2\pi p}{L},\ k_y=\frac{2\pi q}{L},\ k_z=\frac{2\pi r}{L}\ \Rightarrow\ \varepsilon=\frac{2\pi^2\hbar^2}{mL^2}\left( p^2+q^2+r^2 \right)
$$

![](figures/free_electron.svg)

Comparable to phonons, but: electrons are _fermions_.

- Only 2 (due to spin) allowed per $k$-value
- Fill up from the lowest energy until you run out of electrons
   
$\rightarrow$ Calculate when you are out of electrons $\rightarrow$ _Fermi energy_.

![](figures/fermi_circle_periodic.svg)

In order to compute the density of states, we need to perform an integration of k-space. Assuming three dimensions and spherical symmetry (the dispersion in the free electron model is isotropic) we find for the total number of states:

$$
N=2\left(\frac{L}{2\pi}\right)^3\int{\rm d}{\bf k}=2 \left(\frac{L}{2\pi}\right)^34\pi\int k^2{\rm d}k=\frac{V}{\pi^2}\int k^2{\rm d}k ,
$$

where the factor 2 represents spin degeneracy. Using $k=\frac{\sqrt{2m\varepsilon}}{\hbar}$ and ${\rm d}k=\frac{1}{\hbar}\sqrt{\frac{m}{2\varepsilon}}{\rm d}\varepsilon$ we can rewrite this as:

$$
N=\frac{V}{\pi^2}\int\frac{2m\varepsilon}{\hbar^3}\sqrt{\frac{m}{2\varepsilon}}{\rm d}\varepsilon=\frac{Vm^{3/2}}{\pi^2\hbar^3}\int\sqrt{2\varepsilon}\ {\rm d}\varepsilon
$$

So we find for the density of states:

$$
g(\varepsilon)=\frac{ {\rm d}N}{ {\rm d}\varepsilon}=\frac{Vm^{3/2}\sqrt{2\varepsilon}}{\pi^2\hbar^3}\propto\sqrt{\varepsilon}
$$

![](figures/sqrt.svg)

Similarly,

- For 1D: $g(\varepsilon) = \frac{2 V}{\pi} \frac{ {\rm d}k}{ {\rm d}\varepsilon} \propto 1/\sqrt{\varepsilon}$
- For 2D: $g(\varepsilon) = \frac{k V}{\pi} \frac{ {\rm d}k}{ {\rm d}\varepsilon} \propto \text{constant}$

Total number of electrons:

$$
N=\int_0^{\varepsilon_{\rm F}}g(\varepsilon){\rm d}\varepsilon,
$$

with $\varepsilon_{\rm F}$ the _Fermi energy_ = highest filled energy at $T=0$.

$$
\varepsilon_{\rm F}=\frac{\hbar^2}{2m}\left( 3\pi^2\frac{N}{V} \right)^{2/3}\equiv \frac{\hbar^2 k_{\rm F}^2}{2m},\ 
k_{\rm F}=\left( 3\pi^2\frac{N}{V} \right)^{1/3}
$$

The quantity $k_{\rm F}=\frac{2\pi}{\lambda_{\rm F}}$ is called the _Fermi wavevector_, where $\lambda_{\rm F}$ is the _Fermi wavelength_, which is typically in the order of the atomic spacing.

For copper, the Fermi energy is ~7 eV $\rightarrow$ thermal energy of the electrons ~70 000 K ! The _Fermi velocity_ $v_{\rm F}=\frac{\hbar k_{\rm F}}{m}\approx$ 1750 km/s $\rightarrow$ electrons run with a significant fraction of the speed of light, only because lower energy states are already filled by other electrons.

The total number of electrons can be expressed as $N=\frac{2}{3}\varepsilon_{\rm F}g(\varepsilon_{\rm F})$.

![](figures/fermi_level.svg)

The bold line represents all filled states at $T=0$. This is called the _Fermi sea_. Conduction takes place only at the _Fermi surface_: everything below $\varepsilon_{\rm F}-\frac{eV}{2}$ is compensated.

Now: **Finite temperature** $\rightarrow$ probability distribution to occupy certain states.

Fermi-Dirac distribution:

$$
f(\varepsilon,T)=\frac{1}{ {\rm e}^{(\varepsilon-\mu)/k_{\rm B}T}+1}
$$

![](figures/fermi_dirac.svg)

Chemical potential $\mu=\varepsilon_{\rm F}$ if $T=0$. Typically $\varepsilon_{\rm F}/k_{\rm B}$~70 000 K (~7 eV), whereas room temperature is only 300 K (~30 meV) $\rightarrow$ thermal smearing occurs only very close to Fermi surface.

At finite temperature, the total number of electrons $N$ should be:

$$
N=\int_0^\infty f(\varepsilon,T)g(\varepsilon){\rm d}\varepsilon=\int_0^\infty n(\varepsilon,T){\rm d}\varepsilon
$$

We can use this to calculate the electronic contribution to the heat capacity.

![](figures/FD_DOS.svg)

Electrons in the top triangle are being excited to the bottom triangle due to temperature increase. Number of excited electrons $\approx\frac{1}{2}g(\varepsilon_{\rm F})k_{\rm B}T=n_{\rm exc}$. Total extra energy $E(T)-E(0)=n_{\rm exc}k_{\rm B}T=\frac{1}{2}g(\varepsilon_{\rm F})k_{\rm B}^2T^2$.

$$
C_{V,e}=\frac{ {\rm d}E}{ {\rm d}T}=g(\varepsilon_{\rm F})k_{\rm B}^2T=\ ...\ =\frac{3}{2}Nk_{\rm B}\frac{T}{T_{\rm F}}\propto T
$$

$T_{\rm F}=\frac{\varepsilon_{\rm F}}{k_{\rm B}}$ is the _Fermi temperature_.

How does $C_{V,e}$ relate to the phonon contribution $C_{V,p}$?

- At room temperature, $C_{V,p}=3Nk_{\rm B}\gg C_{V,e}$
- Near $T=0$, $C_{V,p}\propto T^3$ and $C_{V,e}\propto T$ $\rightarrow$ competition.

New concept: _Fermi surface_ = all points in k-space with $\varepsilon=\varepsilon_{\rm F}$. For free electrons, the Fermi surface is a sphere.

$$
N=2\frac{\frac{4}{3}\pi k_{\rm F}^3}{\left( \frac{2\pi}{L} \right)^3}=\frac{k_{\rm F}^3V}{3\pi^2}\ \Rightarrow\ k_{\rm F}=\left( 3\pi^2\frac{N}{V} \right)^{1/3}
$$

![](figures/transport.svg)

The orange circle represents the Fermi surface at finite current $\rightarrow$ this circle will shift only slightly before the electrons reach terminal velocity $\rightarrow$ all transport takes place near the Fermi surface.

## Useful trick: scaling of $C_V$

Behavior of $C_V$ can be very quickly memorized or understood using the following mnemonic rule

> Particles with energy $E \leq kT$ are thermally excited, and each carries extra energy $kT$.

#### Example 1: electrons

$g(E_F)$ roughly constant ⇒ total energy in the thermal state is $T \times [T\times g(E_F)]$ ⇒ $C_V \propto T$.

#### Example 2: graphene with $E_F=0$ (midterm 2018)

$g(E) \propto E$ ⇒ total energy is $T \times T^2$ ⇒ $C_V \propto T^2$.

#### Example 3: phonons in 3D at low temperatures.

$g(E) \propto E^2$ ⇒ total energy is $T \times T^3$ ⇒ $C_V \propto T^3$.
