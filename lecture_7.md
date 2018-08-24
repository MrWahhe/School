# Semiconductor physics

## Review of band structure properties

* Group velocity $v=\hbar^{-1}\partial E(k)/\partial k$
* Effective mass $m_{eff} = \hbar^2\left(d^2 E(k)/dk^2\right)^{-1}$
* Density of states $g(E) = \sum_{\textrm{FS}}dk \times (dn/dk) \times (dk/dE)$ the amount of states per infinitesimal interval of energy at each energy.

A simple check that everything is correct is the free electron model:

$$H = \hbar^2 k^2/2m$$

The velocity is $\hbar^{-1}\partial E(k)/\partial k = \hbar k / m \equiv p/m$.  
The effective mass is $m_{eff} = \hbar^2\left(d^2 E(k)/dk^2\right)^{-1} = m$.

So in the simplest case the definitions match the usual expressions.

#### Why are these properties important?

* Group velocity descibes how quickly electrons interacting with the lattice move.
* Effective mass tells us how hard it is to *accelerate* the particles and it enters $g(E)$ for a parabolic band
* Density of states is required to determine the Fermi level, heat capacity, etc.

## Filled vs empty bands

A completely filled band is very similar to a completely empty band.

In a filled band $n(E)=1$ because $|E - E_F| \gg kT$. In an empty band $n(E)=0$.

Heat capacity $C_v = \tfrac{d}{dT}\int_{-\infty}^\infty E\times g(E) \times dE\times n_F(E, T) = 0$.

A completely filled band carries no electric current:

$$
j = 2e \int_{-\pi/a}^{\pi/a} v(k) dk = 2e \int_{-\pi/a}^{\pi/a} (dE/dk)\times dk = 2e [E(-\pi/a) - E(\pi/a)] = 0
$$

## From electrons to holes

A completely filled band $\approx$ completely empty band. The idea of introducing **holes** is to transform an *almost* completely filled band $\Rightarrow$ almost empty one. Instead of describing a lot of electrons that are present, we focus on those that are absent.

Definition: a **hole** is a state of a completely filled band with one particle missing.

![](figures/holes.svg)

In this schematic we can either say that 8×2 electron states are occupied (the system has 8×2 electrons counting spin), or 10×2 hole states are occupied. A useful analogy to remember: glass half-full or glass half-empty.

## Properties of holes

The probability for an electron state to be occupied in equilibrium is $f(E)$:

$$f(E) = \frac{1}{e^{(E-E_F)/kT} + 1}$$

The probability for a hole state to be occupied:

$$1 - f(E) = 1 - \frac{1}{e^{(E-E_F)/kT} + 1} = \frac{1}{e^{(-E+E_F)/kT} + 1}$$

therefore for holes both energy $E_h= -E$ and $E_{F,h} = -E_F$.

The **momentum** $p_h$ of a hole should give the correct total momentum of a partially filled band if one sums momenta of all holes. Therefore $p_h = -\hbar k$, where $k$ is the wave vector of the electron.

Similarly, the total **charge** should be the same regardless of whether we count electrons or holes, so holes have a positive charge $+e$ (electrons have $-e$).

On the other hand, the velocity of a hole is **the same**:
$$\frac{dE_h}{dp_h} = \frac{-dE}{-d\hbar k} = \frac{dE}{dp}$$

Finally, we derive the hole effective mass from the equations of motion:

$$m_h \frac{d v}{d t} = +e (E + v\times B)$$

Comparing with

$$m_e \frac{d v}{d t} = -e (E + v\times B)$$

we get $m_h = -m_e$.

## Semiconductors: materials with two bands.

In semiconductors the Fermi level is between two bands. The unoccupied band is the **conduction band**, the occupied one is the **valence band**. In the conduction band the **charge carriers** (particles carrying electric current) are electrons, in the valence band they are holes.

We can control the position of the Fermi level (or create additional excitations) making semiconductors conduct when needed.

Only the bottom of the conduction band has electrons and the top of the valence band has holes because the temperature is always smaller than the width of the band.

Therefore we can approximate the dispersion relation of both bands as parabolic.

![](figures/semiconductor.svg)

Or in other words

$$E_e = E_G + \frac{\hbar^2k^2}{2m_e},$$
$$E_h = \frac{\hbar^2k^2}{2m_h}.$$

Here $E_G$ is the band gap, and the top of the valence band is at $E=0$.

Observe that because we are describing particles in the valence band as holes, $m_h > 0$ and $E_h > 0$.

??? question "a photon gives a single electron enough energy to move from the valence band to the conduction band. How many particles does this process create?"
    Two: one electron and one hole.

## Semiconductor density of states and Fermi level

### Part 1: pristine semiconductor

![](figures/intrinsic_DOS.svg)

Electrons
$$ E = E_G + {p^2}/{2m_e}$$

$$ g(E) = (2m_e)^{3/2}\sqrt{E-E_G}/2\pi^2\hbar^3$$

Holes
$$ E_h = {p^2}/{2m_h}$$

$$ g(E_h) = (2m_h)^{3/2}\sqrt{E_h}/2\pi^2\hbar^3$$

**The key algorithm of describing the state of a semiconductor:**

1. Write down the density of states, assuming a certain position of the Fermi level
2. Calculate the total amount of electrons and holes, equate the difference to the total amount of electrons $-$ holes available.
3. Use physics intuition to simplify the equations (this is important!)
4. Find $E_F$ and concentrations of electrons and holes

Applying the algorithm:

$$n_h = \int_0^\infty f_h(E+E_F)g_h(E)dE = \int_0^\infty\frac{(2m_h)^{3/2}}{2\pi^2\hbar^3} \sqrt{E}\frac{1}{e^{(E+E_F)/kT}+1}dE$$

$$n_e = \int_{E_G}^\infty f_h(E-E_F)g_e(E)dE = \int_{E_G}^\infty\frac{(2m_e)^{3/2}}{2\pi^2\hbar^3} \sqrt{E-E_G}\frac{1}{e^{(E-E_F)/kT}+1}dE$$

We need to solve $n_e = n_h$

Simplification:
Fermi level is far from both bands $E_F \gg kT$ and $E_G - E_F \gg kT$

Therefore Fermi-Dirac distribution is approximately similar to Boltzmann distribution.

$$f(E\pm E_F) \approx e^{-(E\pm E_F)/kT}$$

Now we can calculate $n_e$ and $n_h$:

$$n_h \approx \frac{V(2m_h)^{3/2}}{2\pi^2\hbar^3}e^{-E_F/kT} \int_0^\infty\sqrt{E}e^{-E/kT}dE =
N_V e^{-E_F/kT},$$

with

$$N_V = 2\left(\frac{2\pi m_h kT}{h^2}\right)^{3/2}$$

the number of holes with energy $E<T$ (compare with the rule above).

??? question "how large is $N_V$ at room temperature? (hard question)"
    If $kT \sim 1\textrm{eV}$ (the typical energy size of a band), then electrons in the whole band may be excited and $N_V \sim 1$. On the other hand, $N_V \sim T^{3/2}$ Therefore $N_V \sim (kT/1 \textrm{eV})^{3/2}\sim 1\%$.

Similarly for electrons:

$$n_e = N_C e^{-(E_G - E_F)/kT},\quad N_C = 2\left(\frac{2\pi m_e kT}{h^2}\right)^{3/2}$$


Combining everything together:

$$n_h \approx N_V e^{-E_F/kT} = N_C e^{-(E_G-E_F)/kT} \approx n_e$$

Solving for $E_F$:

$$E_F = \frac{E_G}{2} - \frac{3}{4}kT\log(m_e/m_h)$$

An extra observation: regardless of where $E_F$ is located, $n_e n_h = N_C N_V e^{-E_G/kT} \equiv n_i^2$.

$n_i$ is the **intrinsic carrier concentration**, and for a pristine semiconductor $n_e = n_h = n_i$.

> The equation
> $$n_e n_h = n_i^2$$
> is the **law of mass action**. The name is borrowed from chemistry, and describes the equilibrium concentration of two reagents in a reaction $A+B \leftrightarrow AB$. Here electrons and hole constantly split and recombine.

## Adding an impurity to semiconductor

* Typical semiconductors are group IV (Si, Ge, GaAs).
* Unfilled shell of group V atom (donor) has 1 extra electron and its nucleus 1 extra proton
* Group III atom (acceptor) lacks 1 electron and 1 nucleus charge

Extra electron (or extra hole) is attracted to the extra charge of the nucleus.

In H the energy levels are:
$$ E_n = - \frac{me^4}{8\pi^2\hbar^3\varepsilon^2_0n^2} = -R_E /n^2= -\frac{13.6\text{eV}}{n^2}$$

Bohr radius (size of the ground state wave function): $4 \pi \varepsilon_0 \hbar^2/m_{\mathrm{e}} e^2$

In a semiconductor $m\to m_{\text{eff}}$, $\epsilon_0 \to \epsilon\epsilon_0$.

An impurity creates a very weakly bound state:
$$E = -\frac{m_e}{m\varepsilon^2} R_E = -0.01 \text{eV (in Ge)}$$
$r = 4$ nm (vs $r = 0.5$ Å in H).

Binding energy smaller than room temperature (0.026 eV).

So a donor adds an extra state at $E_D$ (close to the bottom of the conduction band) and an extra electron.

Likewise an acceptor adds an extra state at $E_A$ (close to the top of the valence band) and an extra hole.

### Density of states with donors and acceptors

![](figures/doping.svg)

All donor/acceptor states at the same energy:
$$g_A(E) = N_A \delta(E-E_A),\quad g_D(E) = N_D \delta(E- (E_G - E_D))$$

How large can $N_D/N_A$ be? The distance between donors should be such that the states don't overlap, so the distance must be much larger than 4 nm. Therefore **maximal** concentration of donors before donor band merges with conduction band is $N_D \lesssim (1Å/4\textrm{nm})^3 \sim 10^{-5}\ll N_C$.


## Number of carriers

Charge conservation:
$$n_e - n_h + n_D - n_A = N_D - N_A$$

We already know $n_e$ and $n_h$.

$$n_D = N_D \frac{1}{e^{-(E_D-E_F)/kT} + 1}, n_A = N_A \frac{1}{e^{-(E_A+E_F)/kT} + 1}$$

Simplification:

Most donors are ionized and most acceptors are occupied.

Then

$$n_e - n_h = N_D - N_A, n_e = n_i^2/n_h$$

When $|N_D-N_A| \gg n_i$ the semiconductor is **extrinsic**, so that if $N_D > N_A$ ($n$-doped semiconductor), $n_e \approx N_D -N_A$ and $n_h = n_i^2/(N_D-N_A)$. If $N_D < N_A$ ($p$-doped semiconductor), $n_h \approx N_A -N_D$ and $n_e = n_i^2/(N_A-N_D)$.

We can now easily find the Fermi level:

$$E_F = E_G - kT\log[N_C/(N_D-N_A)], \textrm{ for } N_D > N_A$$
and
$$E_F = kT\log[N_V/(N_A-N_D)], \textrm{ for } N_A > N_D$$

??? question "When is a semiconductor intrinsic, and when it is extrinsic?"
    By definition the semiconductor is intrinsic when $|N_D-N_A| \ll n_i$, so $kT \gtrsim E_G/\log[N_C N_V/(N_D-N_A)^2]$.

## Temperature dependence of the carrier density and Fermi level

It is instructive to consider how $E_F$, $n_e$ and $n_h$ depend on carrier concentrations.

![](figures/E_F_and_carrier_density.svg)

Several noteworthy features:

* At high temperature $n_e = n_h$ and $E_F$ has an upturn (if holes are heavier than electrons)
* Once the temperature is sufficiently low, we expect the electrons to "freeze away" from the conduction band to the donor band, so that the donor band starts playing a role of the new valence band at $kT \ll E_G - E_D$.
* At zero temperature $E_F$ should match the donor band since it has partially occupied states. If there are no acceptors, $E_F$ would be halfway between $E_D$ and $E_G$, and if there was no doping at all it would be at $E_G/2$.

!!! check "Exercise"
    check that you can reproduce all the relevant limits in a calculation.

## Measuring band gaps

### Conduction

The change of $n_i$ is extremely rapid due to the factor $e^{-E_G/kT}$. Therefore the simplest way of determining the band gap is the temperature dependence of conductance

The total current

$$j = -n_e e v_e + n_h e v_h $$

$$ -m_e v_e /\tau_e = -eE;\quad -m_h v_h /\tau_h = eE $$

Combining the two we see that despite electron and hole velocities have opposite signs, they carry electric current in the same direction.

$$ \sigma \equiv \frac{j}{E} = \left(\frac{n_e e^2 \tau_e}{m_e}+\frac{n_h e^2 \tau_h}{m_h}\right) = n_e e \mu_e + n_h e \mu_h.$$

Since $n_e = n_h = n_i \propto e^{-E_G/kT}$, $E_G \approx d \log \sigma / d [kT]^{-1}$.

Additional information can be obtained using Hall effect. However Hall effect is much more complex in semiconductors since only the current in the direction perpendicular to the applied electric field must vanish. This, however only means that the electron current is opposite of the hole current in that direction, not that the electrons and holes move parallel to the applied current.

### Light adsorption

See [previous lecture](lecture_6.md#light-adsorption)

## Combining semiconductors: $pn$-junction

Main idea: what happens if we bring two differently doped semiconductors together (one of $p$-type, one of $n$-type)?

![](figures/pn-junction.svg)

### Band diagram

Previously we dealt with homogeneous materials, now coordinate (let's call it $x$) starts playing a role. We can represent the properties of inhomogeneous materials using the **band diagram**. The main idea is to plot dependence of various energies ($E_F$, bottom of conduction band, top of the valence band) as a function of position.

So here is our problem for today:

![](figures/band_diagram_question.svg)

> An important remark is in order: before we counted all energies with respect to the top of the valence band. Now $E_F$ is the same everywhere if the sample is in equilibrium, and the bands are shifted due to an extra electrostatic potential.

More specifically: How fast does the electrostatic potential change in the intermediate region? What is the charge density at the junction if we make the chemically-defined boundary between materials very precise?

We may instead use a key bit of insight: **the density of electrons and holes drops exponentially fast as soon as potential deviates by $kT \ll \delta \varphi$ from its bulk value**.

Using this information we can expect a formation of the **depletion region** with almost no electrons or holes (but donors and acceptors won't move anywhere from that region).

So this is our expectation of the dependence of $\rho(x)$:

![](figures/pn_charge_density.svg)

The typical values of $w_n+w_p$ are $\sim 1 \mu \textrm{m}$ at $N_A,\,N_D \sim 10^{16} \textrm{cm}^{-3}$, and $\sim 0.1 \mu \textrm{m}$ at $N_A,\,N_D \sim 10^{18} \textrm{cm}^{-3}$, so it may be much larger than the distance between the dopant atoms.


### $pn$-junction diode

What happens if we apply voltage to a junction?

Because the conductivity of the $p$-region and $n$-region is much larger than that of the depletion region, most of the voltage difference will appear in the depletion region:

![](figures/pn_junction_bias.svg)

The number of majority carriers moving across the junction is proportional to their concentration.
Increasing the voltage bias "pushes" carriers up in energy, it depends exponentially on the voltage.

We therefore get the Shockley diode equation:

$$I = I_0 \left(\exp(eV/kT) -1\right)$$

### Solar cell

Light adsopbed in the $pn$-junction creates electron-hole pairs.
The eletric field then moves electrons to the $n$-doped region, holes to the $p$-doped one, and therefore generates a voltage.

![](figures/solar_cell.svg)

### Semiconducting laser

A heavily doped $pn$-junction so that the Fermi level is in the conduction/valence band produces an extremely high rate electron-hole recombination with an extremely high rate, and makes the $pn$-junction function like a laser.

### MOSFET and quantum well

See the book for details.

## Summary

Density of states in a doped semiconductor:

![](figures/doping.svg)

Charge balance determins the number of electrons and holes as well as the position of the Fermi level.

If dopant concentrations are low, then $n_e = n_h = n_i \equiv \sqrt{N_C N_V}e^{-E_G/2kT}$.

If dopant concentrations are high, then in $n$-doped semiconductor $n_e = N_D - N_A$ and $n_h = n_i^2/n_e$ (or vice versa).

Temperature switches between intrinsic and extrinsic regimes, and controls the carrier density

Conductance combines the contributions of electrons and holes, and allows to determine $E_G$.

A $pn$-junction has a **depletion layer** in its middle with the potential in a $pn$-junction having the following shape (where the transition region is made out of two parabolas):

![](figures/band_diagram_solution.svg)
