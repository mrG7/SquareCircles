# Planck Time, “Photon On/Off”, and Measurement Context: Rigorous Operational Analysis (Draft)

**Status:** Working draft (v0.3)  
**Repo:** AI-V-OS (`docs/`)  
**Purpose:** Make “photon on/off” precise, show where apparent contradictions come from, and connect (carefully) to Planck-scale heuristic limits without overstating quantum-gravity claims.

---

## Abstract

Claims like “a photon is on or off” become ambiguous (and sometimes self-contradictory) when classical binary predicates are applied to quantum optical systems without specifying (i) the **mode** defining “the photon” and (ii) the **measurement** defining “on/off.” This draft develops a fully operational account using quantized field modes, number states, coherent states, and explicit detector POVMs (ideal and inefficient on/off detectors with dark counts). We then compute detection statistics for several scenarios—including vacuum vs one-photon states, vacuum–one superpositions, coherent states, Mach–Zehnder interference with and without which-path information, time-bin superpositions, and emitter–field entanglement—and show that “contradictions” typically arise from implicitly assuming non-contextual, measurement-independent truth values for incompatible observables. Finally, we derive Planck units and present a standard *heuristic* bound suggesting that attempting to operationalize time resolution \(\Delta t \ll t_P\) requires energies approaching the Planck scale, where gravitational backreaction cannot be neglected; we emphasize the limits of this argument and distinguish it from claims that time is discretized in steps of \(t_P\).

---

## 0. Notation and assumptions

- We use SI units unless otherwise stated.
- \(c\) is the speed of light, \(G\) Newton’s constant, \(\hbar\) reduced Planck’s constant.
- \(\mathcal{H}\) is a Hilbert space; density operators are \(\rho\ge 0\) with \(\mathrm{Tr}(\rho)=1\).
- A single bosonic mode has annihilation/creation operators \(a,a^\dagger\) with \([a,a^\dagger]=1\).
- Number operator: \(N=a^\dagger a\); Fock states satisfy \(N|n\rangle=n|n\rangle\).
- “Photon on/off” will mean a **specific measurement** (typically an on/off threshold detector) applied to a **specific mode** (a chosen wavepacket/spatial-temporal mode). Without that, the question is ill-posed.

---

## 1. Introduction: why “photon on/off” can look contradictory

Classical reasoning quietly assumes all of the following:

1. **Definiteness:** a property (e.g., “photon present”) has a definite value at all times.
2. **Non-contextuality:** that value does not depend on how one chooses to measure it.
3. **Measurement revelation:** measurement reveals a pre-existing value rather than creating an outcome via interaction.

Quantum theory rejects this package. A “photon on/off” statement becomes meaningful only after specifying:

- **(i) a mode decomposition** (what counts as “the photon”), and
- **(ii) an observable/POVM** (what counts as “on/off” operationally).

Once those are fixed, the theory makes unambiguous predictions; “contradictions” typically reflect mixing incompatible contexts (e.g., demanding which-path facts *and* interference fringes as if both were simultaneously definite).

### 1.1 “Square circles” from higher-dimensional projections (explicit construction)

“Square circle” is a useful *diagnostic phrase*: in a single 2D world, “the same planar figure is both a perfect square and a perfect circle (in the same sense, at the same time)” is a contradiction. But **projection** lets a single higher-dimensional object yield different lower-dimensional appearances.

#### Example: a right circular cylinder whose shadows are a circle and a square

Let the 3D solid cylinder be

\[
C := \{(x,y,z)\in\mathbb{R}^3:\; x^2+y^2\le R^2,\; 0\le z\le h\}.
\]

Define orthographic (drop-coordinate) projections:

\[
\pi_{xy}(x,y,z)=(x,y),\qquad \pi_{yz}(x,y,z)=(y,z).
\]

Then the image of \(C\) under \(\pi_{xy}\) is

\[
\pi_{xy}(C)=\{(x,y)\in\mathbb{R}^2:\exists z\ \text{s.t.}\ (x,y,z)\in C\}
=\{(x,y):x^2+y^2\le R^2\},
\]
which is a **filled circle** (disk) of radius \(R\).

Similarly,

\[
\pi_{yz}(C)=\{(y,z)\in\mathbb{R}^2:\exists x\ \text{s.t.}\ (x,y,z)\in C\}
=\{(y,z):y^2\le R^2,\ 0\le z\le h\}
=[-R,R]\times[0,h],
\]
which is a **filled rectangle** of width \(2R\) and height \(h\).

If we choose \(h=2R\), then \(\pi_{yz}(C)\) is a **filled square** of side length \(2R\). Thus:

- viewing along the cylinder axis gives a **circle**,
- viewing orthogonally gives a **square** (for \(h=2R\)).

There is no contradiction because the “circle” and “square” are properties of **different projections** \(\pi_{xy}(C)\) and \(\pi_{yz}(C)\), not two simultaneous properties of a single 2D object.

#### Moral

Projections are many-to-one maps: they discard information. Two different projections of the same higher-dimensional object can look mutually incompatible if one incorrectly assumes the projection is “the whole object.”

### 1.2 Why this maps tightly to quantum measurement (Born rule as projection geometry)

This “projection resolves apparent contradiction” story is not merely metaphorical in quantum theory: **ideal (projective) quantum measurement is literally built from projection operators.**

Let an observable have spectral decomposition

\[
A=\sum_a a\,P_a,
\]
where \(P_a\) are orthogonal projectors (\(P_aP_{a'}=\delta_{aa'}P_a\), \(\sum_a P_a = I\)).

For a pure state \(|\psi\rangle\), the Born rule can be written as a squared projection norm:

\[
p(a)=\langle\psi|P_a|\psi\rangle=\|P_a|\psi\rangle\|^2.
\]

The post-measurement state (Lüders rule) is the normalized projection:

\[
|\psi\rangle \;\longrightarrow\; \frac{P_a|\psi\rangle}{\sqrt{p(a)}}.
\]

So a measurement is, in a precise mathematical sense, a map from a “higher-dimensional” object (state vector or density operator) to a lower-dimensional classical outcome, and it generally discards phase/coherence information relative to other incompatible decompositions.

In the present paper:

- photon “on/off” is a projection/POVM that is diagonal in the number basis (§4),
- quadrature/homodyne statistics depend on coherences that on/off cannot access (§5.2.1),
- interferometric “wave-like” behavior depends on the overlap of path-correlated environment states (a scalar product) that controls visibility (§5.5.3).

Attempting to demand that a system simultaneously carry **measurement-independent** truth values for multiple incompatible “views” is analogous to demanding one 2D shadow be both a circle and a square in the same projection.

---

## 2. Planck units and Planck time

### 2.1 Dimensional analysis derivation

We seek a time scale constructed from \(\hbar\), \(G\), and \(c\). Write

\[
t_P \propto \hbar^a G^b c^d.
\]

Using base dimensions:

- \([\hbar] = \mathrm{M\,L^2\,T^{-1}}\)
- \([G] = \mathrm{L^3\,M^{-1}\,T^{-2}}\)
- \([c] = \mathrm{L\,T^{-1}}\)

We require \(\mathrm{T^1}\) overall. Compute:

- Mass exponent: \(a - b = 0 \Rightarrow a=b\).
- Length exponent: \(2a + 3b + d = 0 \Rightarrow 2a + 3a + d = 0 \Rightarrow d=-5a\).
- Time exponent: \(-a - 2b - d = 1 \Rightarrow -a - 2a - (-5a) = 1 \Rightarrow 2a = 1 \Rightarrow a=b=\tfrac12\).

Thus \(d=-\tfrac{5}{2}\) and

\[
t_P = \sqrt{\frac{\hbar G}{c^5}}.
\]

### 2.2 Numerical value and associated scales

Using (approximately):

- \(\hbar \approx 1.054571817\times 10^{-34}\,\mathrm{J\,s}\)
- \(G \approx 6.67430\times 10^{-11}\,\mathrm{m^3\,kg^{-1}\,s^{-2}}\)
- \(c = 2.99792458\times 10^8\,\mathrm{m\,s^{-1}}\)

we obtain:

\[
t_P \approx 5.39\times 10^{-44}\,\mathrm{s}.
\]

Related Planck units:

\[
\ell_P=\sqrt{\frac{\hbar G}{c^3}}\approx 1.62\times 10^{-35}\,\mathrm{m},\quad
m_P=\sqrt{\frac{\hbar c}{G}}\approx 2.18\times 10^{-8}\,\mathrm{kg},
\]
\[
E_P=m_Pc^2=\sqrt{\frac{\hbar c^5}{G}}\approx 1.96\times 10^9\,\mathrm{J}\approx 1.22\times 10^{19}\,\mathrm{GeV}.
\]

Note the identity \(E_P = \hbar/t_P\).

### 2.3 What Planck time does (and does not) imply

- **Does imply:** a natural scale where the dimensionless combination of couplings suggests quantum-gravity effects may be important.
- **Does not (by itself) imply:** that time is fundamentally discrete in steps of \(t_P\), or that physical systems must “update” at that cadence, or that any particular “on/off” predicate must flip on Planck timescales.

### 2.4 Heuristic “minimum time” from quantum localization + gravity (careful)

A standard heuristic combines:

1. To operationally probe time resolution \(\Delta t\), one needs frequency components with \(\Delta\omega \gtrsim 1/\Delta t\) (Fourier limitation).
2. Quanta at angular frequency \(\omega\) have energy \(\sim \hbar\omega\), so resolving \(\Delta t\) pushes energies toward \(E \sim \hbar/\Delta t\) (order-of-magnitude).
3. Concentrating energy \(E\) within a region of size \(R\sim c\Delta t\) yields an associated Schwarzschild radius
   \[
   r_s = \frac{2GE}{c^4}.
   \]

Requiring \(r_s \lesssim R\) (avoid immediate horizon formation in this crude model) gives:

\[
\frac{2GE}{c^4} \lesssim c\Delta t.
\]

Insert \(E\sim \hbar/\Delta t\):

\[
\frac{2G\hbar}{c^4\,\Delta t} \lesssim c\Delta t
\;\Rightarrow\;
\Delta t^2 \gtrsim \frac{2\hbar G}{c^5}
\;\Rightarrow\;
\Delta t \gtrsim \sqrt{2}\,t_P.
\]

**Interpretation:** this is a plausibility argument that **sub-Planckian operational time resolution** may require energies at which gravitational backreaction becomes non-negligible. It is **not** a derivation of time discreteness or a theorem of quantum theory alone.

---

## 3. Quantized optical modes: “what is a photon?”

In quantum optics, a “photon” is most cleanly defined as an excitation of a **mode** of the electromagnetic field. A “mode” is not unique: it depends on boundary conditions (cavity/waveguide), filtering, pulse shaping, detection mode-matching, etc.

### 3.1 Single-mode field algebra

For a single bosonic mode:

\[
[a,a^\dagger]=1,\quad N=a^\dagger a.
\]

The Fock basis \(\{|n\rangle\}_{n=0}^\infty\) satisfies:

\[
N|n\rangle=n|n\rangle,\quad
a|n\rangle=\sqrt{n}\,|n-1\rangle,\quad
a^\dagger|n\rangle=\sqrt{n+1}\,|n+1\rangle.
\]

### 3.2 Canonical states

- **Vacuum:** \(|0\rangle\).
- **Number (Fock) state:** \(|n\rangle\) with definite photon number \(n\).
- **Coherent state:** \(|\alpha\rangle\) defined by \(a|\alpha\rangle=\alpha|\alpha\rangle\). Expansion:
  \[
  |\alpha\rangle = e^{-|\alpha|^2/2}\sum_{n=0}^\infty \frac{\alpha^n}{\sqrt{n!}}|n\rangle.
  \]
  Photon number distribution:
  \[
  P(n)=|\langle n|\alpha\rangle|^2=e^{-|\alpha|^2}\frac{|\alpha|^{2n}}{n!},
  \]
  i.e. Poisson with mean \(\mu=|\alpha|^2\).
- **Thermal state:** diagonal in number basis with Bose–Einstein distribution. If mean photon number is \(\bar n\):
  \[
  \rho_\text{th}=\sum_{n=0}^\infty \frac{\bar n^n}{(1+\bar n)^{n+1}}|n\rangle\langle n|.
  \]

### 3.3 Wavepacket modes (time/frequency localized photons)

For a continuum of frequency modes with operators \(a(\omega)\) satisfying

\[
[a(\omega),a^\dagger(\omega')]=\delta(\omega-\omega'),
\]

define a normalized wavepacket mode \(f(\omega)\) with \(\int d\omega\,|f(\omega)|^2=1\) and

\[
a_f = \int d\omega\, f(\omega)\,a(\omega),\quad [a_f,a_f^\dagger]=1.
\]

Then \(|1_f\rangle = a_f^\dagger|0\rangle\) is “one photon in mode \(f\).”

Crucially, *different choices of \(f\)* define different “photon number” questions. This will matter in §5.8.

---

## 4. What does “on/off” mean? Explicit measurement models

### 4.1 Photon number projective measurement vs on/off detection

An ideal number-resolving measurement uses projectors \(\Pi_n = |n\rangle\langle n|\).

An **ideal on/off detector** (threshold detector) distinguishes only:

- “off” = vacuum (\(n=0\))
- “on” = any nonzero photon number (\(n\ge 1\))

The corresponding POVM elements are:

\[
\Pi_\text{off} = |0\rangle\langle 0|,\quad
\Pi_\text{on} = I - |0\rangle\langle 0|.
\]

For a state \(\rho\), predicted probabilities:

\[
p_\text{off}=\mathrm{Tr}(\rho\,\Pi_\text{off}),\quad
p_\text{on}=\mathrm{Tr}(\rho\,\Pi_\text{on})=1-p_\text{off}.
\]

### 4.2 Inefficiency and dark counts (standard quantum-optics model)

Let \(\eta\in[0,1]\) be detection efficiency. A common model treats each photon as independently detected with probability \(\eta\). Then the probability of **no click** given \(n\) photons is \((1-\eta)^n\).

This corresponds to the POVM:

\[
\Pi_\text{off}^{(\eta)}=\sum_{n=0}^\infty (1-\eta)^n\,|n\rangle\langle n|,
\quad
\Pi_\text{on}^{(\eta)}=I-\Pi_\text{off}^{(\eta)}.
\]

Add a dark-count probability \(p_d\) per detection window by mixing with a classical “false click”:

\[
p_\text{off} = (1-p_d)\,\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)}),
\quad
p_\text{on}=1-p_\text{off}.
\]

This is not the only model, but it is a widely used baseline.

### 4.3 Immediate consequence: phases can be invisible to on/off

Because \(\Pi_\text{off}^{(\eta)}\) is diagonal in the number basis, any relative phase between \(|0\rangle\) and \(|1\rangle\) in a superposition \(\alpha|0\rangle+\beta|1\rangle\) will not affect \(p_\text{on/off}\). To see that phase, you need a different measurement (e.g. homodyne).

---

## 5. Scenarios with explicit calculations

### 5.1 Vacuum vs one-photon Fock state

Let \(\rho=|0\rangle\langle0|\). With ideal on/off:

\[
p_\text{off}=1,\quad p_\text{on}=0.
\]

With inefficiency and dark counts:

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)}) = (1-\eta)^0 = 1
\Rightarrow
p_\text{on} = 1-(1-p_d)\cdot 1 = p_d.
\]

So even vacuum can “click” due to dark counts.

Now take \(\rho=|1\rangle\langle1|\). Then

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})=(1-\eta)^1 = 1-\eta
\Rightarrow
p_\text{on}=1-(1-p_d)(1-\eta)=p_d + (1-p_d)\eta.
\]

For \(p_d=0\), \(p_\text{on}=\eta\): a one-photon state does not guarantee a click unless \(\eta=1\).

### 5.2 The clearest “on/off superposition”: \(|\psi\rangle=\alpha|0\rangle+\beta|1\rangle\)

Let \(|\alpha|^2+|\beta|^2=1\) and \(\rho=|\psi\rangle\langle\psi|\).

Compute \(\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})\).

Because \(\Pi_\text{off}^{(\eta)}\) is diagonal in \(|n\rangle\),

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})
= |\alpha|^2(1-\eta)^0 + |\beta|^2(1-\eta)^1
= |\alpha|^2 + (1-\eta)|\beta|^2
= 1-\eta|\beta|^2.
\]

Thus (with \(p_d=0\)):

\[
p_\text{on}=\eta|\beta|^2.
\]

With ideal detection \(\eta=1\), \(p_\text{on}=|\beta|^2\). The state is literally a coherent superposition of “off” and “on” eigenstates of photon number, and “on/off” becomes a probabilistic measurement outcome.

#### 5.2.1 On/off cannot see coherence; homodyne (quadrature) can (explicit calculation)

The on/off POVM in §4 is diagonal in the number basis, so it depends only on the populations \(\rho_{nn}\). This means **a coherent superposition and an incoherent mixture can have identical on/off statistics**.

For example, define the incoherent mixture with the same number populations as \(|\psi\rangle\):

\[
\rho_\text{mix} := |\alpha|^2|0\rangle\langle 0| + |\beta|^2|1\rangle\langle 1|.
\]

Then for either \(\rho=|\psi\rangle\langle\psi|\) or \(\rho_\text{mix}\),

\[
p_\text{on} = 1-\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)}) = \eta|\beta|^2,
\]
so **on/off detection cannot distinguish “superposition” from “classical randomness”** in this case.

To see the difference, consider a homodyne (quadrature) measurement. Define the dimensionless quadrature operator

\[
X := \frac{a+a^\dagger}{\sqrt{2}},
\]
with eigenstates \(|x\rangle\) satisfying \(X|x\rangle=x|x\rangle\).

In the \(x\)-representation, the first two harmonic-oscillator wavefunctions are:

\[
\psi_0(x):=\langle x|0\rangle = \pi^{-1/4}e^{-x^2/2},\qquad
\psi_1(x):=\langle x|1\rangle = \pi^{-1/4}\sqrt{2}\,x\,e^{-x^2/2}.
\]

For the pure state \(|\psi\rangle=\alpha|0\rangle+\beta|1\rangle\), the quadrature amplitude is

\[
\langle x|\psi\rangle=\alpha\psi_0(x)+\beta\psi_1(x)
=\pi^{-1/4}e^{-x^2/2}\left(\alpha+\sqrt{2}\,x\,\beta\right),
\]
so the probability density is

\[
P_\psi(x)=|\langle x|\psi\rangle|^2
=\pi^{-1/2}e^{-x^2}\left(|\alpha|^2 + 2x^2|\beta|^2 + 2\sqrt{2}\,x\,\mathrm{Re}(\alpha^*\beta)\right).
\]

For the mixture \(\rho_\text{mix}\), the probability density is

\[
P_\text{mix}(x)=\mathrm{Tr}(\rho_\text{mix}|x\rangle\langle x|)
=|\alpha|^2|\psi_0(x)|^2 + |\beta|^2|\psi_1(x)|^2
=\pi^{-1/2}e^{-x^2}\left(|\alpha|^2 + 2x^2|\beta|^2\right),
\]
which lacks the linear “interference” term proportional to \(\mathrm{Re}(\alpha^*\beta)\).

Thus the **relative phase** between \(\alpha\) and \(\beta\) (and, more generally, coherence between \(|0\rangle\) and \(|1\rangle\)) is operationally accessible in quadrature statistics even though it is invisible to on/off detection. In practice, one measures a phase-rotated quadrature \(X_\varphi=(a e^{-i\varphi}+a^\dagger e^{i\varphi})/\sqrt2\) by varying the local-oscillator phase \(\varphi\).

### 5.3 Coherent state \(|\alpha\rangle\): Poisson counting \(\Rightarrow\) closed-form click probability

For \(\rho=|\alpha\rangle\langle\alpha|\) with mean photon number \(\mu=|\alpha|^2\),

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})
=\sum_{n=0}^\infty (1-\eta)^n\,P(n)
=\sum_{n=0}^\infty (1-\eta)^n\,e^{-\mu}\frac{\mu^n}{n!}.
\]

Recognize the exponential series:

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})
= e^{-\mu}\sum_{n=0}^\infty \frac{\left((1-\eta)\mu\right)^n}{n!}
= e^{-\mu}\,e^{(1-\eta)\mu}
= e^{-\eta\mu}.
\]

So (with dark counts \(p_d\)):

\[
p_\text{on}=1-(1-p_d)e^{-\eta\mu}.
\]

This is a quantitative bridge between a classical-looking field amplitude (coherent state) and discrete on/off click statistics.

### 5.4 Thermal state \(\rho_\text{th}\): click probability and heavy tails

For \(\rho=\rho_\text{th}\) with mean \(\bar n\),

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})
=\sum_{n=0}^\infty (1-\eta)^n\,\frac{\bar n^n}{(1+\bar n)^{n+1}}
=\frac{1}{1+\bar n}\sum_{n=0}^\infty \left(\frac{(1-\eta)\bar n}{1+\bar n}\right)^n.
\]

This is a geometric series with ratio \(r=\frac{(1-\eta)\bar n}{1+\bar n}\) (note \(|r|<1\)). Therefore:

\[
\mathrm{Tr}(\rho\,\Pi_\text{off}^{(\eta)})
=\frac{1}{1+\bar n}\cdot \frac{1}{1-r}
=\frac{1}{1+\bar n}\cdot \frac{1}{1-\frac{(1-\eta)\bar n}{1+\bar n}}
=\frac{1}{1+\eta\bar n}.
\]

Thus (with \(p_d=0\)):

\[
p_\text{on}=1-\frac{1}{1+\eta\bar n}=\frac{\eta\bar n}{1+\eta\bar n}.
\]

### 5.5 Mach–Zehnder interferometer: single-photon interference vs which-path information

We model two spatial modes (arms) \(A\) and \(B\) with creation operators \(a^\dagger, b^\dagger\).

#### 5.5.1 50/50 beamsplitter transformation (one convention)

Let the first beamsplitter implement:

\[
U_\text{BS}^\dagger a\,U_\text{BS}=\frac{a+i b}{\sqrt{2}},\quad
U_\text{BS}^\dagger b\,U_\text{BS}=\frac{i a+b}{\sqrt{2}}.
\]

Input state: one photon in mode \(a\), vacuum in \(b\):

\[
|\psi_\text{in}\rangle = |1\rangle_a|0\rangle_b = a^\dagger|0\rangle.
\]

After the first beamsplitter:

\[
|\psi_1\rangle = U_\text{BS}|\psi_\text{in}\rangle
= U_\text{BS} a^\dagger U_\text{BS}^\dagger\,U_\text{BS}|0\rangle
= \left(\frac{a^\dagger - i b^\dagger}{\sqrt{2}}\right)|0\rangle
= \frac{|1,0\rangle - i|0,1\rangle}{\sqrt{2}}.
\]

Now apply a phase shift \(\phi\) in arm \(B\): \(b^\dagger\mapsto e^{i\phi} b^\dagger\). Then

\[
|\psi_\phi\rangle=\frac{|1,0\rangle - i e^{i\phi}|0,1\rangle}{\sqrt{2}}.
\]

After the second identical beamsplitter, compute output amplitudes. Let output modes be \(c,d\) defined by the same unitary acting on \(a,b\):

\[
c=\frac{a+i b}{\sqrt{2}},\quad d=\frac{i a+b}{\sqrt{2}}
\Rightarrow
a=\frac{c-i d}{\sqrt{2}},\quad b=\frac{-i c+d}{\sqrt{2}}.
\]

Rewrite the single-photon state in terms of \(c^\dagger,d^\dagger\). Using

\[
a^\dagger=\frac{c^\dagger+i d^\dagger}{\sqrt{2}},\quad
b^\dagger=\frac{i c^\dagger+d^\dagger}{\sqrt{2}},
\]

we have

\[
|\psi_\phi\rangle
=\frac{1}{\sqrt{2}}\left(a^\dagger - i e^{i\phi} b^\dagger\right)|0\rangle
=\frac{1}{\sqrt{2}}\left(
\frac{c^\dagger+i d^\dagger}{\sqrt{2}}
- i e^{i\phi}\frac{i c^\dagger+d^\dagger}{\sqrt{2}}
\right)|0\rangle.
\]

Simplify the bracket:

\[
\frac{1}{\sqrt{2}}\left(
\frac{c^\dagger+i d^\dagger}{\sqrt{2}}
+\frac{e^{i\phi} c^\dagger - i e^{i\phi} d^\dagger}{\sqrt{2}}
\right)
=\frac{1}{2}\left(
(1+e^{i\phi})c^\dagger + i(1-e^{i\phi})d^\dagger
\right).
\]

Thus:

\[
|\psi_\text{out}\rangle
=\frac{1+e^{i\phi}}{2}|1\rangle_c|0\rangle_d
+\frac{i(1-e^{i\phi})}{2}|0\rangle_c|1\rangle_d.
\]

Therefore detection probabilities at the two outputs:

\[
P(c)=\left|\frac{1+e^{i\phi}}{2}\right|^2
=\frac{1+\cos\phi}{2}=\cos^2\left(\frac{\phi}{2}\right),
\]
\[
P(d)=\left|\frac{1-e^{i\phi}}{2}\right|^2
=\frac{1-\cos\phi}{2}=\sin^2\left(\frac{\phi}{2}\right).
\]

This is single-photon interference: outcomes depend on relative phase even though “only one photon” traverses the interferometer.

#### 5.5.2 Which-path information as dephasing: interference disappears

Suppose the path becomes entangled with an environment/pointer state \(|E_A\rangle,|E_B\rangle\) such that after the first beamsplitter:

\[
|\Psi\rangle = \frac{|1,0\rangle|E_A\rangle - i|0,1\rangle|E_B\rangle}{\sqrt{2}}.
\]

If \(\langle E_A|E_B\rangle=0\) (perfect which-path record), then tracing out the environment yields the mixed state:

\[
\rho_{AB}=\mathrm{Tr}_E(|\Psi\rangle\langle\Psi|)
=\frac12\left(|1,0\rangle\langle 1,0| + |0,1\rangle\langle 0,1|\right),
\]
with no coherence (no off-diagonal terms).

Propagating this mixture through the phase shifter and second beamsplitter yields equal output probabilities:

\[
P(c)=P(d)=\frac12,
\]
independent of \(\phi\). The “contradiction” (which-path *and* interference) is resolved: interference requires coherence, which which-path records destroy.

#### 5.5.3 Partial which-path information: overlap controls visibility and yields a quantitative tradeoff

The physically generic case is *partial* which-path information: the environment states correlated with the two arms are neither identical nor orthogonal. Let

\[
\gamma := \langle E_B|E_A\rangle,\qquad 0\le |\gamma|\le 1.
\]

Carry the phase shift \(\phi\) in arm \(B\) and write the joint state (up to an overall convention-dependent phase) as:

\[
|\Psi_\phi\rangle=\frac{|1,0\rangle|E_A\rangle - i e^{i\phi}|0,1\rangle|E_B\rangle}{\sqrt{2}}.
\]

Tracing out the environment yields a reduced path state:

\[
\rho_{AB}=\mathrm{Tr}_E(|\Psi_\phi\rangle\langle\Psi_\phi|)
=\frac12\Big(
|1,0\rangle\langle 1,0| + |0,1\rangle\langle 0,1|
+ i\gamma e^{-i\phi}|1,0\rangle\langle 0,1|
- i\gamma^* e^{i\phi}|0,1\rangle\langle 1,0|
\Big).
\]

Now compute the probability to exit at output port \(c\) of the second beamsplitter. Using \(c=(a+i b)/\sqrt2\), the number operator is

\[
n_c=c^\dagger c=\frac{a^\dagger a + b^\dagger b + i a^\dagger b - i b^\dagger a}{2}.
\]

Restricted to the single-photon subspace spanned by \(\{|1,0\rangle,|0,1\rangle\}\), we have
\(\langle 1,0|a^\dagger b|0,1\rangle=1\) and \(\langle 0,1|b^\dagger a|1,0\rangle=1\), so:

\[
P(c)=\mathrm{Tr}(\rho_{AB} n_c)
=\frac12\left(\rho_{AA}+\rho_{BB}\right)+\frac12\left(i\rho_{BA}-i\rho_{AB}\right)
=\frac12 + \mathrm{Im}(\rho_{AB}).
\]

Here \(\rho_{AB}=\langle 1,0|\rho_{AB}|0,1\rangle = (i\gamma e^{-i\phi})/2\), so

\[
P(c)=\frac12 + \frac{|\gamma|}{2}\cos\!\left(\phi-\arg\gamma\right)
=\frac12\left[1+|\gamma|\cos\!\left(\phi-\arg\gamma\right)\right].
\]

Thus the fringe **visibility** is

\[
V=\frac{P_\text{max}-P_\text{min}}{P_\text{max}+P_\text{min}}=|\gamma|.
\]

Meanwhile, the best possible which-path guess from the environment record is a binary quantum-state discrimination problem between \(|E_A\rangle\) and \(|E_B\rangle\) with equal priors. Helstrom’s bound gives optimal success probability

\[
P_\text{succ}^\star=\frac12\left(1+\sqrt{1-|\langle E_A|E_B\rangle|^2}\right)
=\frac12\left(1+\sqrt{1-|\gamma|^2}\right).
\]

Define distinguishability \(D:=2P_\text{succ}^\star-1\). Then

\[
D=\sqrt{1-|\gamma|^2}.
\]

Combining with \(V=|\gamma|\) yields the quantitative complementarity relation for this pure-state model:

\[
V^2 + D^2 = 1.
\]

More general models (mixed environments, unequal arm weights, additional noise) give \(V^2 + D^2 \le 1\), but the central message remains: partial which-path information continuously reduces interference in a precisely computable way—there is no logical contradiction once the full quantum state and measurement context are specified.

### 5.6 Time-bin superposition: “early or late” is not classical ignorance

Let \(|E\rangle\) and \(|L\rangle\) be orthonormal time-bin modes (early/late). Consider a single-photon time-bin qubit:

\[
|\psi\rangle=\frac{|E\rangle+e^{i\theta}|L\rangle}{\sqrt{2}}.
\]

An “arrival-time bin measurement” in the \(\{|E\rangle,|L\rangle\}\) basis yields early/late each with probability \(1/2\), independent of \(\theta\).

But an interferometric measurement that recombines the bins (effectively measuring in the \(\{|+\rangle,|-\rangle\}\) basis with \(|\pm\rangle=(|E\rangle\pm|L\rangle)/\sqrt2\)) yields:

\[
P(+)=\left|\langle +|\psi\rangle\right|^2
=\left|\frac{1+e^{i\theta}}{2}\right|^2
=\cos^2\left(\frac{\theta}{2}\right),
\]
\[
P(-)=\sin^2\left(\frac{\theta}{2}\right).
\]

Thus the phase \(\theta\) is operationally real (observable) in the recombined measurement, even though it is invisible to the “which-bin” measurement. Again: context matters.

### 5.7 Emitter–field entanglement: “photon on/off” can be conditional

Consider an atom with excited \(|e\rangle\) and ground \(|g\rangle\) states coupled to a single field mode. A simplified entangled state is:

\[
|\Psi\rangle = \frac{|e\rangle|0\rangle + |g\rangle|1\rangle}{\sqrt{2}}.
\]

The reduced field state is obtained by tracing out the atom:

\[
\rho_\text{field}=\mathrm{Tr}_\text{atom}(|\Psi\rangle\langle\Psi|)
=\frac12\left(|0\rangle\langle 0| + |1\rangle\langle 1|\right),
\]
a classical mixture (no \(|0\rangle\langle 1|\) coherence).

An on/off detector with efficiency \(\eta\) and \(p_d=0\) predicts:

\[
p_\text{on} = \mathrm{Tr}(\rho_\text{field}\,\Pi_\text{on}^{(\eta)})
=\frac12\left(0 + \eta\right)=\frac{\eta}{2}.
\]

However, if one measures the atom first and conditions on the outcome:

- outcome \(|e\rangle\) prepares the field in \(|0\rangle\) (“off”)
- outcome \(|g\rangle\) prepares the field in \(|1\rangle\) (“on” with probability \(\eta\))

So “photon on/off” can be a **conditional** statement relative to correlated degrees of freedom, not an absolute binary fact of the field alone.

### 5.8 Mode-basis dependence: a definite photon in one mode can be a superposition in another

Let \(a_u,a_v\) be annihilation operators for two orthonormal modes \(u,v\).
Define rotated modes:

\[
a_\pm=\frac{a_u\pm a_v}{\sqrt2}.
\]

Then \(a_u^\dagger = (a_+^\dagger + a_-^\dagger)/\sqrt2\). Acting on vacuum:

\[
|1_u,0_v\rangle = a_u^\dagger|0\rangle
=\frac{1}{\sqrt2}\left(a_+^\dagger+a_-^\dagger\right)|0\rangle
=\frac{|1_+,0_-\rangle + |0_+,1_-\rangle}{\sqrt2}.
\]

So a state that is “one photon present” in mode \(u\) is **not** “one photon present” in a unique, basis-independent way; it becomes a superposition relative to another valid mode decomposition. Any binary “on/off” claim must therefore specify the mode that the detector is actually sensitive to.

---

## 6. Where the “contradictions” come from (and how superposition resolves them)

The recurring pattern in §5 is:

- One measurement context asks a yes/no question about a particular basis (e.g., “which path?”, “which time bin?”, “is \(n=0\)?”).
- Another context asks about interference/coherence in a complementary basis.

Attempting to assign simultaneous, context-independent truth values to both sets of questions leads to “contradictions.” Quantum theory avoids contradiction by:

- representing the system by a state (vector or density operator) that can contain coherent superpositions,
- predicting outcomes via context-specific Born-rule probabilities \(\mathrm{Tr}(\rho\,\Pi_i)\),
- allowing measurement interactions (and entanglement with environments) to change which coherences are physically accessible.

In short: superposition is not “classical uncertainty about which option is real”; it is a structural statement about how amplitudes compose and how different measurement choices access different observables.

---

## 7. Time resolution, bandwidth, and the Planck scale (operational framing)

### 7.1 “Time window” vs “photon present”: what a detector really does

A real detector defines:

- a detection **mode** (spatial/spectral/temporal filtering + mode overlap),
- a detection **window** of duration \(T\),
- a POVM (often effectively thresholding).

Thus “photon on in a Planck-time slice” is not just about \(t_P\); it requires a physically realizable detector whose response function has support on that timescale *and* couples to the relevant ultra-broadband modes.

### 7.2 Fourier-limited pulses: explicit bandwidth–duration relation

For a transform-limited pulse with temporal envelope \(g(t)\) and spectrum \(\tilde g(\omega)\), the rms widths satisfy

\[
\Delta t\,\Delta\omega \ge \frac12,
\]
with equality for Gaussians.

If \(\Delta t = t_P\), then \(\Delta\omega \gtrsim 1/(2t_P)\sim 10^{43}\,\mathrm{s^{-1}}\). Frequency components at that scale correspond to energies per quantum of order \(\hbar\Delta\omega \sim \hbar/t_P = E_P\).

### 7.3 Why this does not imply “photons flip on/off each \(t_P\)”

The reasoning above says:

- to probe such short times operationally, one is pushed to ultra-high-frequency components and Planckian energies,
- gravitational backreaction becomes relevant, so naive quantum-optics models likely fail.

It does **not** say:

- that physical fields evolve in discrete ticks,
- that a photon has an intrinsic binary “on/off” variable that updates at \(t_P\),
- or that standard quantum superposition ceases to apply (we do not currently have a complete experimentally confirmed theory at that regime).

---

## 8. Conclusion (current draft)

1. “Photon on/off” is not a single question; it is shorthand for a **mode-defined** and **measurement-defined** predicate.
2. With explicit detector POVMs, “on/off” outcomes are straightforward to compute and show no inconsistency.
3. Apparent contradictions most often come from importing classical assumptions of measurement-independent, simultaneously definite properties for incompatible observables.
4. Planck time is a natural quantum-gravity scale; heuristic arguments suggest operational probes below \(t_P\) require Planckian energies, but this does not by itself imply time discreteness or binary “flip” dynamics.

---

## Appendix A: On/off POVM derivation for inefficiency

If each photon is independently detected with probability \(\eta\), then with \(n\) photons the probability of *no* detection is \((1-\eta)^n\). For a number-diagonal state \(\rho=\sum_n p_n |n\rangle\langle n|\),

\[
p_\text{off}=\sum_{n=0}^\infty p_n(1-\eta)^n
=\mathrm{Tr}\!\left(\rho\sum_{n=0}^\infty (1-\eta)^n |n\rangle\langle n|\right).
\]

Thus the operator in parentheses is the POVM element \(\Pi_\text{off}^{(\eta)}\).

---

## Appendix B: Two-mode basis rotation identity

For orthonormal modes \(u,v\), define \(a_\pm=(a_u\pm a_v)/\sqrt2\). Then

\[
a_u^\dagger = \frac{a_+^\dagger+a_-^\dagger}{\sqrt2}
\Rightarrow
a_u^\dagger|0\rangle = \frac{|1_+,0_-\rangle + |0_+,1_-\rangle}{\sqrt2}.
\]

This is the core algebraic reason why “photon present” is mode-dependent.

---

## References (starting list)

- C. Gerry and P. Knight, *Introductory Quantum Optics*.
- D. F. Walls and G. J. Milburn, *Quantum Optics*.
- L. Mandel and E. Wolf, *Optical Coherence and Quantum Optics*.
- M. A. Nielsen and I. L. Chuang, *Quantum Computation and Quantum Information* (measurement/POVM formalism).
- A. Peres, *Quantum Theory: Concepts and Methods* (contextuality/complementarity discussion).


