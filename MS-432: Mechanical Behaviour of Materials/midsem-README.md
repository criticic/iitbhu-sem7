# MS-432: Mechanical Behaviour of Materials — Mid-Sem Notes

> **Scope:** Engineering vs. True Stress–Strain and the Additivity Proof; the Tensile Stress–Strain Curve (Yield, UTS, Necking, Resilience, Toughness); Theoretical vs. Real Shear Strength (Frenkel's Sinusoidal Model); Dislocation Fundamentals, Types and Motions; Resolved Shear Stress & Schmid's Law; Crystallography of Slip in FCC & BCC; Slip vs. Twinning; Coarse-to-Fine Grain Fragmentation during Rolling; the Bauschinger Effect; Frank-Read Sources & Lomer-Cottrell Locks; and Strengthening Mechanisms in Metals (Grain Boundary, Yield Point & Strain Aging, Solid Solution, and Precipitation Hardening).

---

## Table of Contents

1. [Part 1: Fundamentals of Stress–Strain, Elasticity, and Plasticity](#part-1)
2. [Part 2: Dislocation Fundamentals and Crystallography of Slip](#part-2)
3. [Part 3: Dislocation Interactions, Hardening, and Strain Cycles](#part-3)
4. [Part 4: Strengthening Mechanisms in Metals](#part-4)
5. [Exam Strategy & Preparation Tips](#exam-strategy--preparation-tips)

---

**Master Unit Roadmap for Mid-Semester Preparation**

1. **Unit 1 —** Fundamentals of Stress–Strain, Elasticity, and Plasticity
   * Engineering vs. True Stress and Strain (mathematical derivations, volume constancy, proof of additivity/accuracy).
   * The Tensile Stress–Strain Curve (elastic limit, proportional limit, yield point, 0.2% offset method, UTS, uniform vs. non-uniform elongation, necking, resilience, toughness).
   * Theoretical vs. Real Shear Strength of Crystals (Frenkel's sinusoidal model derivation, $\tau_m \approx G/2\pi$, comparison with experimental yield strength, role of defects).
2. **Unit 2 —** Dislocation Fundamentals and Crystallography of Slip
   * Dislocation types (Edge, Screw, Mixed) and their geometric relationships ($\vec{b} \perp \hat{t}$, $\vec{b} \parallel \hat{t}$).
   * Dislocation motion: Glide (conservative), Climb (non-conservative, vacancy-assisted), Cross-slip.
   * Resolved Shear Stress (RSS) & Schmid's Law: Full derivation of $\tau_{\text{RSS}} = \sigma \cos\phi \cos\lambda$, definition of Schmid Factor, physical significance of Critical Resolved Shear Stress ($\tau_{\text{CRSS}}$).
   * Slip systems in FCC and BCC: Specific plane-direction calculations, explanation of straight slip lines (FCC) vs. wavy slip lines (BCC).
   * Slip vs. Twinning mechanisms: Full comparative analysis, mirror symmetry, atomic displacement, and surface polishing behavior.
3. **Unit 3 —** Dislocation Interactions, Hardening, and Strain Cycles
   * Microstructural evolution under deformation: Coarse-to-fine grain fragmentation during rolling, formation of shear bands and subgrains.
   * The Bauschinger Effect: Definition, schematic stress–strain loops, dislocation pile-up mechanism, back-stress theory, forward vs. reverse yield stress, cyclic softening vs. hardening.
   * Dislocation Multiplication:
     * The Frank-Read Source (step-by-step mechanism, bow-out, pinch-off loop formation).
     * Sessile Dislocations & Lomer-Cottrell Locks (dislocation reactions in FCC, Frank's energy criterion $b^2$, planes of sessility, Cottrell-Lomer barrier formation).
4. **Unit 4 —** Strengthening Mechanisms in Metals
   * Grain Boundary Strengthening (Hall-Petch relation, pile-up model, reverse Hall-Petch at nanocrystalline scale).
   * Yield Point Phenomenon (mild steel, interstitial solute pinning, Cottrell atmosphere, upper/lower yield points, Lüders bands).
   * Strain Aging & Dynamic Strain Aging (DSA): Mechanisms, static vs. dynamic aging, Portevin–Le Chatelier serrations, effect of temperature and strain rate.
   * Solid Solution Strengthening (interstitial vs. substitutional, Hume-Rothery rules, lattice strain fields).
   * Precipitation / Particle Strengthening: Coherent vs. incoherent precipitates, Cutting/Shearing vs. Orowan Bypassing/Looping, critical particle size $d_c$, aging sequence in Al-Mg-Si alloys ($\text{SSSS} \to \text{GP zones} \to \beta'' \to \beta' \to \beta$) and hardness/yield strength evolution.

---

<a name="part-1"></a>
## Part 1: Fundamentals of Stress–Strain, Elasticity, and Plasticity

**Exam Questions Covered:** 2025 Q.9, Q.2 & Q.10; 2022 Q.2

---

### 1. Engineering Stress–Strain vs. True Stress–Strain

#### A. Definitions

1. **Engineering Stress ($\sigma_e$ or $s$):** The applied tensile or compressive load ($F$) divided by the **original** cross-sectional area ($A_0$):
   $$\sigma_e = \frac{F}{A_0}$$
2. **Engineering Strain ($\epsilon$ or $e$):** The change in length ($\Delta L$) divided by the **original** gauge length ($L_0$):
   $$\epsilon = \frac{L - L_0}{L_0} = \frac{\Delta L}{L_0}$$
3. **True Stress ($\sigma_T$):** The instantaneous applied load ($F$) divided by the **instantaneous** cross-sectional area ($A$):
   $$\sigma_T = \frac{F}{A}$$
4. **True Strain ($\epsilon_T$):** The integral of incremental changes in length ($dL$) over the current instantaneous length ($L$):
   $$\epsilon_T = \int_{L_0}^{L} \frac{dL}{L} = \ln\left(\frac{L}{L_0}\right)$$

#### B. Mathematical Derivations

* **Relation between True Stress ($\sigma_T$) and Engineering Stress ($\sigma_e$):**
  Assuming **constant volume** during plastic deformation:
  $$V = A_0 L_0 = A L \implies \frac{A_0}{A} = \frac{L}{L_0}$$

  From the definition of engineering strain:
  $$\frac{L}{L_0} = \frac{L_0 + \Delta L}{L_0} = 1 + \frac{\Delta L}{L_0} = 1 + \epsilon$$

  Therefore:
  $$\sigma_T = \frac{F}{A} = \frac{F}{A_0} \times \frac{A_0}{A} = \sigma_e \left(\frac{L}{L_0}\right)$$
  $$\mathbf{\sigma_T = \sigma_e (1 + \epsilon)}$$
  *(Note: Valid up to the onset of necking/UTS. Beyond necking, deformation is localized and cross-sectional area must be measured directly).*

* **Relation between True Strain ($\epsilon_T$) and Engineering Strain ($\epsilon$):**
  $$\epsilon_T = \ln\left(\frac{L}{L_0}\right) = \ln\left(\frac{L_0 + \Delta L}{L_0}\right) = \ln\left(1 + \frac{\Delta L}{L_0}\right)$$
  $$\mathbf{\epsilon_T = \ln(1 + \epsilon)}$$

---

> **EXAM QUESTION — 2025 Mid-Sem — Q.9**
>
> **Q:** Which one is giving more realistic value of strain: True strain or Engineering strain? Prove it theoretically. *(2 Marks)*
>
> **Answer:**
>
> **True strain** gives a more realistic and physically consistent measure of strain than engineering strain.
>
> **Theoretical Proof (Principle of Additivity / Reversibility):**
> Consider a bar of initial length $L$ that is stretched to double its length ($2L$), and subsequently compressed back to its original length ($L$):
>
> * **Using Engineering Strain ($\epsilon$):**
>   1. *Step 1 (Tensile elongation from* $L \to 2L$*):*
>      $$\epsilon_1 = \frac{2L - L}{L} = \frac{L}{L} = +1.0 \quad (+100\%)$$
>   2. *Step 2 (Compressive deformation from* $2L \to L$*):*
>      $$\epsilon_2 = \frac{L - 2L}{2L} = \frac{-L}{2L} = -0.5 \quad (-50\%)$$
>   3. *Total Net Engineering Strain:*
>      $$\Sigma \epsilon = \epsilon_1 + \epsilon_2 = +1.0 - 0.5 = \mathbf{+0.5 \neq 0}$$
>      *Contradiction:* The body has returned precisely to its initial geometry, yet engineering strain registers an artifact residual strain of $+50\%$. Engineering strain fails the condition of path additivity.
>
> * **Using True Strain ($\epsilon_T$):**
>   1. *Step 1 (Elongation from* $L \to 2L$*):*
>      $$\epsilon_{T,1} = \ln\left(\frac{2L}{L}\right) = \ln(2) \approx \mathbf{+0.693}$$
>   2. *Step 2 (Compression from* $2L \to L$*):*
>      $$\epsilon_{T,2} = \ln\left(\frac{L}{2L}\right) = \ln\left(\frac{1}{2}\right) = -\ln(2) \approx \mathbf{-0.693}$$
>   3. *Total Net True Strain:*
>      $$\Sigma \epsilon_T = \epsilon_{T,1} + \epsilon_{T,2} = \ln(2) + (-\ln(2)) = \mathbf{0}$$
>
> **Conclusion:** True strain accurately reflects zero net deformation upon returning to the original dimensions because it evaluates incremental strain with respect to the instantaneous reference state ($d\epsilon_T = dL/L$). Hence, true strain is mathematically additive and physically realistic.

---

### 2. The Complete Tensile Stress–Strain Curve for Ductile Materials

```
   Stress (σ)
       ^
       |                UTS (C)
       |                 /\
       |    Yield (B)   /    \  Fracture (D)
       |       *-------/      *
       |      /       Uniform  \ Non-uniform / Necking
       |     / A (Elastic Limit)
       |    /  
       |   /   Slope = Young's Modulus (E)
       |  /
       | /
       +--------------------------------------------> Strain (ε)
       0   0.2% Offset (if no sharp yield point)
```

1. **Linear Elastic Region ($0 \to A$):**
   * Follows Hooke's Law: $\sigma = E \epsilon$, where $E$ is Young's Modulus.
   * Deformation is fully reversible; upon load removal, atoms return to equilibrium spacing without defect generation.
2. **Proportional & Elastic Limit ($A$):**
   * The boundary beyond which stress is no longer strictly proportional to strain, and irreversible dislocation motion initiates.
3. **Yield Strength ($\sigma_y$ or $\sigma_o$):**
   * The stress level at which noticeable permanent plastic deformation begins.
   * **0.2% Offset Yield Strength ($R_{p0.2}$):** For materials without a sharply defined yield drop (e.g., FCC metals like Al, Cu, austenitic steel), a line parallel to the elastic slope ($E$) is drawn starting at $\epsilon = 0.002$ ($0.2\%$ strain). The intersection with the stress–strain curve defines $\sigma_y$.
4. **Strain Hardening / Work Hardening Region ($B \to C$):**
   * Characterized by **uniform plastic elongation**.
   * As plastic deformation proceeds, dislocation multiplication leads to severe dislocation–dislocation tangles and pile-ups at barriers, increasing the material's resistance to further deformation.
5. **Ultimate Tensile Strength (UTS, Point $C$):**
   * The maximum engineering stress sustained by the specimen.
   * Represents the **Considère criterion** for plastic instability:
     $$\frac{d\sigma_T}{d\epsilon_T} = \sigma_T$$
   * At this point, the rate of strain hardening can no longer compensate for the rate of area reduction.
6. **Necking Region & Fracture ($C \to D$):**
   * **Non-uniform (localized) deformation** concentrates in a narrow cross-section.
   * The load-bearing capacity decreases in engineering terms due to rapid local area reduction until ductile failure/fracture occurs (microvoid coalescence $\to$ cup-and-cone morphology).
7. **Energy Absorbed:**
   * **Resilience ($U_r$):** Modulus of resilience is the area under the elastic portion of the stress–strain curve up to the yield point:
     $$U_r \approx \frac{\sigma_y^2}{2E}$$
   * **Toughness:** Total area under the entire stress–strain curve up to the point of fracture, indicating energy absorbed per unit volume before catastrophic rupture.

---

### 3. Theoretical vs. Real Shear Strength of Crystalline Materials

#### A. Frenkel's Sinusoidal Model Derivation

Consider two parallel atomic planes separated by interplanar spacing $a$, with interatomic distance along the slip direction equal to $b$.

```
          <--- b --->
Plane 2:   O   O   O   O   O   O  ---> Displacement x, Shear stress τ
           |   |   |   |   |   |  
          --- a ---
           |   |   |   |   |   |
Plane 1:   O   O   O   O   O   O
```

When an external shear stress $\tau$ is applied, Plane 2 slides over Plane 1 by a relative displacement $x$:

1. **Symmetry Conditions:**
   * At $x = 0$, atoms are in equilibrium $\implies \tau = 0$.
   * At $x = b$, atoms have moved to the next lattice site $\implies \tau = 0$.
   * At $x = b/2$, atoms are in an unstable symmetric position midway between sites $\implies \tau = 0$.
2. **Periodic Shear Stress Assumption:**
   Frenkel assumed the restoring shear stress is periodic with period $b$:
   $$\tau = \tau_m \sin\left(\frac{2\pi x}{b}\right)$$
   where $\tau_m$ is the **theoretical shear strength** (amplitude of the wave).
3. **Small-Displacement Limit (Hooke's Law):**
   For very small atomic displacements ($x \ll b$):
   $$\sin\left(\frac{2\pi x}{b}\right) \approx \frac{2\pi x}{b} \implies \tau \approx \tau_m \left(\frac{2\pi x}{b}\right) \quad \text{--- (Eq. 1)}$$
   From continuum elasticity, shear stress is related to shear strain $\gamma = x/a$ via the shear modulus $G$:
   $$\tau = G \gamma = G \left(\frac{x}{a}\right) \quad \text{--- (Eq. 2)}$$
4. **Equating (Eq. 1) and (Eq. 2):**
   $$\tau_m \left(\frac{2\pi x}{b}\right) = G \left(\frac{x}{a}\right) \implies \tau_m = \frac{G}{2\pi}\left(\frac{b}{a}\right)$$
   For a simple cubic or close-packed arrangement where $b \approx a$:
   $$\mathbf{\tau_m \approx \frac{G}{2\pi} \approx \frac{G}{6} \text{ to } \frac{G}{10}}$$

---

> **EXAM QUESTION — 2025 Mid-Sem — Q.2 & Q.10 / 2022 Mid-Sem — Q.2**
>
> **Q:** Prove theoretically that theoretical shear strength of metal crystal is at least 100 times greater than the observed shear strength / yield stress. *(3 Marks)*
>
> **Q:** Why theoretical shear stress is much higher than the yield stress? *(2 Marks)*
>
> **Answer:**
>
> 1. **Numerical Discrepancy:**
>    * For typical engineering metals, the shear modulus $G$ ranges from **$20 \text{ GPa to } 150 \text{ GPa}$**.
>    * According to Frenkel's theoretical formula:
>      $$\tau_m = \frac{G}{2\pi} \approx \frac{20 \text{ to } 150 \text{ GPa}}{6.28} \approx \mathbf{3 \text{ to } 25 \text{ GPa}} \quad (3000 \text{ to } 25000 \text{ MPa})$$
>    * However, experimentally measured critical shear stresses ($\tau_{\text{exp}}$ or $\sigma_y$) in real single crystals are typically **$0.5 \text{ to } 10 \text{ MPa}$**.
>    * Taking the ratio:
>      $$\frac{\tau_m}{\tau_{\text{exp}}} = \frac{3000 \text{ MPa}}{10 \text{ MPa}} \approx \mathbf{300 \text{ to } 1000} \gg 100$$
>      Thus, the theoretical strength is **at least 100 to 1000 times higher** than experimental yield values.
>
> 2. **Physical Origin of the Discrepancy:**
>    * **Theoretical Assumption:** Frenkel's model assumes a **perfect crystal lattice** where all atomic bonds across the slip plane are stretched and broken **simultaneously** (rigid bodily shear).
>    * **Real Materials:** Real crystals contain line defects known as **dislocations**. Plastic deformation does **not** proceed by simultaneous bond rupture; instead, dislocations glide across the slip plane by breaking and reforming **one row of atomic bonds at a time**.
>    * Because moving an existing dislocation requires an exponentially lower stress (the *Peierls–Nabarro stress*), real metals yield at stresses orders of magnitude below their theoretical ideal bond strength.

---

<a name="part-2"></a>
## Part 2: Dislocation Fundamentals and Crystallography of Slip

**Exam Questions Covered:** 2024 Q.8, Q.6, Q.2, Q.1 & Q.3, Q.5; 2025 Q.1, Q.6, Q.11, Q.5 & Q.8; 2022 Q.4, Q.7 & Q.8, Q.6, Q.5

---

### 1. Dislocation Geometry, Types, and Motions

A **dislocation** is a one-dimensional (line) defect in a crystal lattice that separates slipped and unslipped regions of a slip plane. It represents the boundary where local atomic registry is disrupted.

#### A. Burgers Vector ($\vec{b}$) and Dislocation Line Vector ($\hat{t}$)

* **Dislocation Line Vector ($\hat{t}$):** A unit vector indicating the instantaneous direction and tangent to the dislocation line.
* **Burgers Vector ($\vec{b}$):** An invariant vector representing the magnitude and direction of the lattice distortion (closure failure of a Burgers circuit around the defect).

#### B. Types of Dislocations

```
      Edge Dislocation                    Screw Dislocation
      
           | Extra half-plane                  /// Slip boundary
           v                                  /// 
     O   O | O   O   O                   +---------+-------+
     O   O | O   O   O                   |         |  /|   |  Dislocation
     O   O | O   O   O                   |  Slip   | / |   |  line t 
     O   O * O   O   O                   |  region |/  |   |  ======>
     O     O     O                       +---------+---+---+
      <----+---->                         =====> Burgers vector b
         b (b ⊥ t)                                  (b || t)
```

1. **Edge Dislocation:**
   * **Geometry:** Formed by inserting an extra half-plane of atoms into the crystal lattice.
   * **Vector Relationship:** The Burgers vector is perpendicular to the dislocation line vector:
     $$\mathbf{\vec{b} \perp \hat{t}} \quad (\theta = 90^\circ)$$
   * **Slip Plane:** Because $\vec{b}$ and $\hat{t}$ are orthogonal, they uniquely define a single plane ($\vec{n} = \hat{t} \times \vec{b}$). Thus, an edge dislocation has a **unique, restricted slip plane**.
2. **Screw Dislocation:**
   * **Geometry:** Formed by cutting a crystal partway and shifting one side relative to the other parallel to the cut line, creating a helical/spiral ramp of atomic planes.
   * **Vector Relationship:** The Burgers vector is parallel to the dislocation line vector:
     $$\mathbf{\vec{b} \parallel \hat{t}} \quad (\theta = 0^\circ \text{ or } 180^\circ)$$
   * **Slip Plane:** Since $\vec{b} \parallel \hat{t}$, their cross product is zero; they do **not** define a unique plane. Any plane passing through $\hat{t}$ containing $\vec{b}$ can act as a potential slip plane.
3. **Mixed Dislocation:**
   * **Geometry:** Most real dislocations are curved loops containing both edge and screw characters.
   * **Vector Relationship:** $\vec{b}$ lies at an arbitrary angle $\theta$ relative to $\hat{t}$ ($0^\circ < \theta < 90^\circ$).
   * Can be mathematically resolved into an edge component ($b_e = b \sin\theta$) and a screw component ($b_s = b \cos\theta$).

#### C. Dislocation Motion

1. **Glide (Conservative Motion):**
   * Dislocation moves within its defined slip plane without mass transport (no diffusion).
   * **Stress-Controlled:** Driven purely by mechanical resolved shear stress.
   * *Edge Dislocation:* Glides **parallel** to $\vec{b}$ (in the direction of applied shear stress).
   * *Screw Dislocation:* Glides **perpendicular** to $\vec{b}$ (transverse to the applied shear stress).
2. **Climb (Non-Conservative Motion):**
   * Operates **only in edge dislocations**. The dislocation moves out of its slip plane (perpendicular to $\vec{b}$ and the slip plane).
   * **Diffusion-Controlled:** Requires the emission or absorption of vacancies or interstitials:
     * *Positive Climb:* Removal of an atom from the extra half-plane via absorption of a vacancy (half-plane shrinks upward).
     * *Negative Climb:* Addition of an atom to the extra half-plane by absorbing an interstitial or emitting a vacancy (half-plane extends downward).
   * Dominates at **elevated temperatures** ($T > 0.4 T_m$) where vacancy mobility is thermally activated.
3. **Cross-Slip:**
   * Operates **only in screw dislocations**.
   * Because $\vec{b} \parallel \hat{t}$, a screw dislocation is not constrained to a single plane. When blocked by an obstacle in its primary slip plane, it can transfer its glide motion to an intersecting, non-parallel slip plane that shares the same Burgers vector $\vec{b}$.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.8 / 2025 Mid-Sem — Q.1 / 2022 Mid-Sem — Q.4**
>
> **Q:** What are dislocations? Write down the different types of dislocations and explain them along with their motion and their relation of Burgers vector to dislocation line. *(1+2+1 / 4 Marks)*
>
> **Answer:**
>
> **1. Dislocation — Definition:** A dislocation is a one-dimensional (line) defect that separates slipped and unslipped regions of a slip plane. Plastic deformation proceeds by the **sequential** breaking and re-forming of atomic bonds along the dislocation line, not by simultaneous rupture of an entire plane. It is characterized by the **Burgers vector** $\vec{b}$ (magnitude and direction of the lattice distortion) and the **line vector** $\hat{t}$ (unit tangent to the dislocation line).
>
> **2. Types of Dislocations:**
>
> * **Edge Dislocation:** Formed by inserting an extra half-plane of atoms into the lattice; $\vec{b} \perp \hat{t}$ ($\theta = 90^\circ$). Because $\vec{b}$ and $\hat{t}$ define a unique plane ($\vec{n} = \hat{t} \times \vec{b}$), an edge dislocation is confined to a **single, restricted slip plane**.
> * **Screw Dislocation:** Formed by a shear displacement parallel to the cut line, giving a helical atomic ramp; $\vec{b} \parallel \hat{t}$ ($\theta = 0^\circ$ or $180^\circ$). Since $\vec{b} \parallel \hat{t}$, no unique slip plane is defined; any plane containing $\hat{t}$ and $\vec{b}$ can serve as a slip plane.
> * **Mixed Dislocation:** Most real dislocations are curved loops with both characters; $\vec{b}$ makes an arbitrary angle $\theta$ ($0^\circ < \theta < 90^\circ$) with $\hat{t}$. It resolves into an edge component ($b_e = b \sin\theta$) and a screw component ($b_s = b \cos\theta$).
>
> **3. Dislocation Motion:**
>
> * **Glide (Conservative):** Motion within the slip plane with no mass transport; driven by mechanical resolved shear stress. An edge dislocation glides **parallel** to $\vec{b}$, while a screw dislocation glides **perpendicular** to $\vec{b}$.
> * **Climb (Non-Conservative):** Out-of-plane motion of **edge** dislocations only, by emitting or absorbing vacancies/interstitials. It is diffusion-controlled and dominant at elevated temperatures ($T > 0.4\ T_m$).
> * **Cross-Slip:** Operation of **screw** dislocations only; since $\vec{b} \parallel \hat{t}$, a blocked screw dislocation can transfer its glide onto an intersecting plane that shares the same $\vec{b}$.

---

### 2. Resolved Shear Stress (RSS) and Schmid's Law

Dislocations glide only under the action of **shear stress acting on the slip plane along the slip direction**. Even under pure uniaxial tensile loading, shear components develop on obliquely oriented crystallographic planes.

```
                  F (Tensile Axis)
                  ^
                  |
             +----+----+
             |    |    |
             |   / \   |
             |  /   \  | N (Slip Plane Normal)
             | / Φ_N \ |
             |/       \|
             +---------+  <--- As (Area of Slip Plane)
             |\       /|
             | \ Φ_D / |
             |  \   /  | D (Slip Direction)
             |   \ /   |
             |    |    |
             +----+----+
                  |
                  v
                  F
```

#### A. Derivation of Resolved Shear Stress ($\tau_{\text{RSS}}$)

1. Let a cylindrical single crystal specimen have cross-sectional area $A$ normal to the tensile loading axis.
2. An axial tensile force $F$ is applied, producing nominal tensile stress $\sigma = F/A$.
3. Let:
   * $\vec{N}$ = normal to the slip plane, forming angle $\phi$ (or $\phi_N$) with the tensile axis.
   * $\vec{D}$ = slip direction lying on the slip plane, forming angle $\lambda$ (or $\phi_D$) with the tensile axis.
4. **Area of the Inclined Slip Plane ($A_s$):**
   The geometric projection of area $A$ onto the inclined plane is:
   $$A = A_s \cos\phi \implies A_s = \frac{A}{\cos\phi}$$
5. **Force Component along the Slip Direction ($F_D$):**
   The component of the axial load $F$ resolved along the direction $\vec{D}$ is:
   $$F_D = F \cos\lambda$$
6. **Resolved Shear Stress ($\tau_{\text{RSS}}$):**
   $$\tau_{\text{RSS}} = \frac{F_D}{A_s} = \frac{F \cos\lambda}{\frac{A}{\cos\phi}} = \left(\frac{F}{A}\right) \cos\phi \cos\lambda$$
   $$\mathbf{\tau_{\text{RSS}} = \sigma \cos\phi \cos\lambda}$$

#### B. Schmid Factor ($m$)

The dimensionless geometric quantity:
$$\mathbf{m = \cos\phi \cos\lambda}$$

* Because the slip direction $\vec{D}$ lies on the slip plane, the plane normal $\vec{N}$ and direction $\vec{D}$ are perpendicular: $\vec{N} \cdot \vec{D} = 0$, which means $\phi + \lambda \ge 90^\circ$.
* **Zero Shear Cases ($m = 0 \implies \tau_{\text{RSS}} = 0$):**
  1. Tensile axis normal to slip plane ($\phi = 0^\circ \implies \lambda = 90^\circ$).
  2. Tensile axis parallel to slip plane ($\phi = 90^\circ$).
  3. Tensile axis perpendicular to slip direction ($\lambda = 90^\circ$).
* **Maximum Schmid Factor:**
  The maximum possible value occurs when the plane and direction are oriented symmetrically at $\mathbf{\phi = \lambda = 45^\circ}$:
  $$m_{\text{max}} = \cos(45^\circ) \cos(45^\circ) = \frac{1}{\sqrt{2}} \times \frac{1}{\sqrt{2}} = \mathbf{0.5}$$

#### C. Schmid's Law

Schmid's Law states: Plastic slip initiates on the slip system for which the resolved shear stress reaches a critical characteristic value, known as the **Critical Resolved Shear Stress ($\tau_{\text{CRSS}}$)**, regardless of the orientation of the crystal or applied stress axis.

$$\mathbf{\tau_{\text{CRSS}} = \sigma_y \cos\phi \cos\lambda = \sigma_y \cdot m}$$
$$\implies \mathbf{\sigma_y = \frac{\tau_{\text{CRSS}}}{\cos\phi \cos\lambda} = \frac{\tau_{\text{CRSS}}}{m}}$$

* **Anisotropy of Yield Strength ($\sigma_y$):**
  * While **$\tau_{\text{CRSS}}$ is an intrinsic, invariant material constant** (dependent only on crystal structure, composition, and temperature), the measured uniaxial yield stress **$\sigma_y$ varies strongly with crystal orientation**.
  * If $m$ is close to $0.5$ (soft orientation), $\sigma_y$ is minimum.
  * If $m \to 0$ (hard orientation), $\sigma_y \to \infty$ on that specific slip system, forcing slip on secondary systems or causing brittle cleavage.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.6 / 2025 Mid-Sem — Q.6 / 2022 Mid-Sem — Q.7 & Q.8**
>
> **Q:** Derive the derivation for the critical resolved shear stress. Differentiate between Schmid law and Schmid factor. *(3+2 Marks)*
>
> **Q:** Why critical resolved shear stress is independent of the orientation of stress axis with respect to slip system? *(2 Marks)*
>
> **Answer:**
>
> **Part 1: Derivation of the Critical Resolved Shear Stress**
> Consider a cylindrical single crystal of cross-sectional area $A$ loaded axially by a force $F$, giving nominal stress $\sigma = F/A$. Let the slip plane normal $\vec{N}$ make an angle $\phi$ with the tensile axis, and let the slip direction $\vec{D}$ lying in the slip plane make an angle $\lambda$ with the tensile axis.
>
> 1. **Area of the inclined slip plane** (projection of the axial area onto the plane):
>    $$A_s = \frac{A}{\cos\phi}$$
> 2. **Force resolved along the slip direction:**
>    $$F_D = F \cos\lambda$$
> 3. **Resolved shear stress on the slip system:**
>    $$\tau_{\text{RSS}} = \frac{F_D}{A_s} = \frac{F \cos\lambda}{A/\cos\phi} = \sigma \cos\phi \cos\lambda$$
> 4. **Critical condition (Schmid's Law):** Slip initiates on the most favorably oriented slip system when $\tau_{\text{RSS}}$ reaches the intrinsic constant $\tau_{\text{CRSS}}$:
>    $$\tau_{\text{CRSS}} = \sigma_y \cos\phi \cos\lambda = \sigma_y \cdot m \implies \sigma_y = \frac{\tau_{\text{CRSS}}}{m}$$
>    where the maximum Schmid factor is $m_{\text{max}} = 0.5$ at $\phi = \lambda = 45^\circ$.
>
> **Part 2: Schmid's Law vs. Schmid Factor**
>
> | Parameter | Schmid's Law | Schmid Factor ($m$) |
> | :--- | :--- | :--- |
> | **Definition** | Criterion stating yielding begins when $\tau_{\text{RSS}} = \tau_{\text{CRSS}}$ on the most favorably oriented slip system. | Purely geometric orientation factor relating axial stress to shear stress ($m = \cos\phi \cos\lambda$). |
> | **Formula** | $\tau_{\text{CRSS}} = \sigma_y \cos\phi \cos\lambda$ | $m = \cos\phi \cos\lambda$ |
> | **Units** | Stress units ($\text{MPa}$ or $\text{N/m}^2$). | Dimensionless scalar ($0 \le m \le 0.5$). |
> | **Nature** | Fundamental physical law of crystal plasticity. | Geometrical mapping function dependent on loading axis. |
> | **Independence** | **$\tau_{\text{CRSS}}$ is independent of loading orientation** because it represents the fundamental lattice resistance (Peierls barrier) required to move dislocations on the slip plane. | **Directly dependent on orientation** of the tensile/compressive axis relative to the crystallographic axes. |

---

### 3. Crystallography of Slip Systems in FCC and BCC

A **slip system** is defined as a combination of a slip plane and a slip direction:
$$\text{Slip System} = \\{hkl\\}\langle uvw\rangle$$

Slip occurs preferentially along **closest-packed planes** (highest planar atomic density, largest interplanar spacing $d_{hkl}$) and along **closest-packed directions** (highest linear atomic density, shortest Burgers vector $|\vec{b}|$).

#### A. Face-Centered Cubic (FCC)

* **Slip Plane:** $\\{111\\}$ octahedral planes ($4$ unique planes).
* **Slip Direction:** $\langle 110\rangle$ face-diagonal directions ($3$ per plane).
* **Total Primary Slip Systems:**
  $$4 \text{ planes} \times 3 \text{ directions/plane} = \mathbf{12 \text{ slip systems}}$$
* **Burgers Vector:** $\vec{b} = \frac{a}{2}\langle 110\rangle$.

---

> **EXAM QUESTION — 2025 Mid-Sem — Q.11**
>
> **Q:** Determine the slip system for slip on a $(1\bar{1}1)$ plane in FCC Crystal. *(2 Marks)*
>
> **Solution:**
> In FCC crystals, slip directions belong to the $\langle 110\rangle$ family and must lie completely within the slip plane $(1\bar{1}1)$.
> For a direction $[uvw]$ to lie in plane $(hkl)$, their dot product must equal zero (**Weiss Zone Law**):
> $$h \cdot u + k \cdot v + l \cdot w = 0$$
> For plane $(hkl) = (1, -1, 1)$:
> $$1(u) - 1(v) + 1(w) = 0 \implies u - v + w = 0$$
>
> Testing all possible directions in the $\langle 110\rangle$ family:
> 1. Direction $[110]$: $1 - 1 + 0 = 0$ $\implies$ **Valid slip direction: $[110]$** (or $[\bar{1}\bar{1}0]$)
> 2. Direction $[011]$: $0 - 1 + 1 = 0$ $\implies$ **Valid slip direction: $[011]$** (or $[0\bar{1}\bar{1}]$)
> 3. Direction $[10\bar{1}]$: $1 - 0 + (-1) = 0$ $\implies$ **Valid slip direction: $[10\bar{1}]$** (or $[\bar{1}01]$)
> *(Note: Other combinations like* $[101] \implies 1 - 0 + 1 = 2 \neq 0$ *do not lie on this plane).*
>
> **Final Answer:**
> The three independent slip directions on the $(1\bar{1}1)$ plane are:
> $$\mathbf{[110], \ [011], \ [10\bar{1}]}$$
> giving the three slip systems:
> $$\mathbf{(1\bar{1}1)[110], \quad (1\bar{1}1)[011], \quad (1\bar{1}1)[10\bar{1}]}$$

---

#### B. Body-Centered Cubic (BCC)

* Does not possess a truly close-packed plane like $\\{111\\}_{\text{FCC}}$.
* **Slip Direction:** $\langle 111\rangle$ body-diagonal directions (strictly close-packed, $|\vec{b}| = \frac{a\sqrt{3}}{2}$).
* **Active Slip Planes:** Slip can occur on multiple planes containing the $\langle 111\rangle$ direction:
  * $\\{110\\}$ planes: $6 \text{ planes} \times 2 \text{ directions} = 12 \text{ systems}$
  * $\\{112\\}$ planes: $12 \text{ planes} \times 2 \text{ directions} = 24 \text{ systems}$
  * $\\{123\\}$ planes: $24 \text{ planes} \times 1 \text{ direction} = 24 \text{ systems}$
* **Total Potential Systems:** Up to **$48 \text{ slip systems}$**.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.2 / 2022 Mid-Sem — Q.6**
>
> **Q:** Why wavy slips were appeared after deformation in alpha iron (BCC) and straight slip lines in FCC metals? *(2 / 1+1 Marks)*
>
> **Answer:**
>
> 1. **In FCC Metals (Straight Slip Lines):**
>    * Slip is strictly confined to the four close-packed $\\{111\\}$ planes, where planar density is highest ($74\%$ atomic packing).
>    * Cross-slip from one $\\{111\\}$ plane to another requires constricting extended partial dislocations (which are split by a stacking fault ribbon), requiring high activation energy.
>    * Consequently, dislocations glide extensively on the same planar $\\{111\\}$ surface, creating **sharp, planar, straight slip traces**.
>
> 2. **In BCC Metals like $\alpha$-Iron (Wavy Slip Lines):**
>    * BCC metals have a common close-packed slip direction ($\langle 111\rangle$) shared by many intersecting planes ($\\{110\\}$, $\\{112\\}$, $\\{123\\}$).
>    * Screw dislocations in BCC have a non-planar, asymmetric core structure with a low cross-slip barrier.
>    * As screw dislocations glide, they readily and frequently **cross-slip** among multiple intersecting planes that share the common $\langle 111\rangle$ zone axis (a phenomenon known as **pencil glide**).
>    * Macroscopically, this continuous switching between planes appears as **undulated, wavy slip lines**.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.5**
>
> **Q:** Why most of the FCC materials exhibit low strength and higher ductility at higher temperature? *(2 Marks)*
>
> **Answer:**
>
> 1. **Activation of Secondary Slip Systems:** At room temperature, FCC deformation is dominated by the primary $12 \times \\{111\\}\langle 110\rangle$ slip systems. At elevated temperatures, additional thermal energy provides the driving force to activate higher-energy **secondary slip systems** (e.g., $\\{110\\}\langle 110\rangle$ and $\\{100\\}\langle 110\rangle$), providing more independent degrees of plastic deformation.
> 2. **Enhanced Dislocation Mobility & Cross-Slip:** Thermal activation assists extended partial dislocations to constrict and overcome obstacles via cross-slip and climb. This relieves dislocation pile-ups and reduces work hardening.
> 3. **Result:** Lower thermal barrier for flow reduces yield strength ($\sigma_y \downarrow$), while increased slip freedom and delay of localized necking increase elongation to failure ($\text{ductility} \uparrow$).

---

### 4. Slip vs. Twinning Mechanisms

Plastic deformation in crystals proceeds primarily through **Slip** or **Twinning**.

```
         SLIP MECHANISM                             TWINNING MECHANISM
   (Dislocation glide in blocks)                (Coordinated shear across plane)
   
        O   O   O   O   O                          O   O   /   O   O
      ------------------- (Slip Plane)                /  O   O   O
            O   O   O   O   O                        / O   O   O
      -------------------                   --------/---------------- (Twin Plane)
                O   O   O   O   O                  O   O   \   O   O
                                                      \  O   O   O
   - Orientation identical across plane                \   O   O
   - Movement: integer multiples of b       - Orientation: mirror image reflection
                                            - Movement: fraction of atomic spacing
```

#### A. Comprehensive Comparison Table

| Parameter | Slip | Twinning (Mechanical Twin) |
| :--- | :--- | :--- |
| **Mechanism** | Progressive glide of individual dislocations breaking one row of bonds at a time. | Coordinated, collective shear of atomic layers parallel to the twinning plane. |
| **Crystallographic Orientation** | Lattice orientation **remains identical** in slipped and unslipped regions. | Lattice in the twinned zone undergoes reorientation to form a **mirror image** of the matrix across the twin plane. |
| **Atomic Displacement** | Occurs in **discrete integer multiples** of the lattice vector ($1b, 2b, \dots$). | Atomic displacement is **proportional to the distance** from the twin plane (fractional atomic spacing). |
| **Planes Involved** | Localized on widely spaced, isolated discrete slip planes. | Involves **every consecutive atomic plane** within the twinned volume. |
| **Surface Morphology** | Produces step-like surface relief (**slip lines**). | Produces broad macroscopic bands/wedges (**twin bands**). |
| **Occurrence Conditions** | Dominates at high/room temperatures, low strain rates, in materials with high stacking fault energy (SFE) and numerous slip systems (FCC, BCC). | Dominates at **low temperatures**, **high strain rates (shock/impact)**, and in materials with **few slip systems** (e.g., HCP metals like Mg, Zn, Ti). |

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.1 & Q.3 / 2025 Mid-Sem — Q.5 & Q.8 / 2022 Mid-Sem — Q.5**
>
> **Q:** Differentiate between the slip and twin mechanism. *(3 / 2 Marks)*
>
> **Q:** Why slip lines are removed after polishing, but twin planes/deformation bands do not disappear even after polishing? *(1+1 / 2 Marks)*
>
> **Answer (Slip vs. Twinning):**
>
> * **Crystallographic orientation:** Lattice orientation remains identical across the slip plane in slip; the twinned region is reoriented into a **mirror image** of the matrix across the twin plane.
> * **Atomic displacement:** Occurs in discrete integer multiples of the Burgers vector in slip ($1b, 2b, \dots$); it is a fraction of the atomic spacing, proportional to the distance from the twin plane, in twinning.
> * **Planes involved:** Slip is localized on widely spaced, isolated planes; twinning shears **every consecutive atomic plane** within the twinned volume.
> * **Mechanism:** Progressive glide of individual dislocations in slip; coordinated, collective shear of atomic layers in twinning.
> * **Surface relief:** Step-like **slip lines** in slip; broad macroscopic **twin bands/wedges** in twinning.
> * **Occurrence conditions:** Slip dominates at high/room temperature and low strain rate in high-SFE materials with many slip systems (FCC, BCC); twinning dominates at low temperature and high strain rate in low-SFE materials with few slip systems (HCP).
>
> **Answer (Polishing Behavior):**
>
> * **Why Slip Lines Disappear:**
>   * Slip lines are merely **surface steps** (microscopic surface topography) created when dislocation lines exit at the free surface.
>   * The underlying crystal lattice orientation underneath the step remains completely identical to the bulk crystal.
>   * When the sample is metallographically ground and polished, this thin surface topography is abraded away. Because there is no internal crystallographic discontinuity or orientation difference, the slip lines **disappear completely**.
> * **Why Twin Planes / Deformation Bands Persist:**
>   * Twinning and deformation bands are **bulk microstructural features** that extend deeply through the 3D volume of the grain.
>   * The region inside the twin has a **different crystallographic orientation** (mirror image) separated from the matrix by a coherent twin boundary.
>   * When polished and chemically etched, the grain boundary/twin boundary has higher interfacial energy and etches preferentially; furthermore, light reflects differently from the reoriented lattice. Therefore, the twin traces **remain visible even after repeated polishing**.

---

<a name="part-3"></a>
## Part 3: Dislocation Interactions, Hardening, and Strain Cycles

**Exam Questions Covered:** 2025 Q.3, Q.4, Q.7; 2024 Q.4, Q.7; 2022 Q.10, Q.9; 2021 Q.3, Q.4

---

### 1. Microstructural Evolution: Coarse-to-Fine Grain Fragmentation During Rolling

During plastic deformation processes such as cold rolling or severe plastic deformation (SPD), large equiaxed grains break down into ultrafine grain structures through dislocation reorganization.

```
  Stage 1: Coarse Grains       Stage 2: Dislocation Glide      Stage 3: Shear Bands & Cells
     +-----+-----+                 +-----+-----+                  +--//-+--//-+
     |     |     |                 | / / | \ \ |                  | //  |  // | Dense Dislocation
     |     |     |  =========>     |/ / /|  \ \|  =========>      |// / | // /| Walls (DDWs) &
     +-----+-----+                 +-----+-----+                  +--//-+--//-+ Subgrains
     (High-angle boundaries)     (Slip planes activate)       (Dislocation-free subcell interiors)
                                                                           |
                                                                           | Stage 4: Rearrangement
                                                                           v
                                                                  +--+--+--+--+
                                                                  |  |  |  |  | Ultrafine Grains
                                                                  +--+--+--+--+ (New High-Angle Boundaries)
```

#### A. Step-by-Step Fragmentation Mechanism

1. **Initial State (Stage 1):** Polycrystalline material possesses coarse grains separated by high-angle grain boundaries (misorientation angle $\theta > 15^\circ$), which are thermodynamically stable.
2. **Homogeneous Slip & Dislocation Generation (Stage 2):** Under applied rolling stresses, multiple slip systems activate within each grain to accommodate macroscopic shape change (satisfying Taylor's criterion of 5 independent slip systems). Dislocations multiply rapidly.
3. **Dislocation Cell Formation & Shear Banding (Stage 3):**
   * Dislocations of opposite signs attract and form localized low-energy configurations called **dislocation cell walls** or **Dense Dislocation Walls (DDWs)**, enclosing relatively dislocation-free cell interiors.
   * Under heavy rolling reductions, macroscopic **shear bands** form, traversing through multiple grains.
   * These dense cell walls progressively trap more dislocations, increasing misorientation across the cell boundaries ($2^\circ < \theta < 15^\circ$). These are termed **Low-Angle Grain Boundaries (LAGBs)** or **subgrains**.
4. **Grain Refinement (Stage 4):**
   * With continued deformation (or moderate dynamic recovery/slight heat), subgrains rotate to accommodate severe plastic strains.
   * The low-angle boundaries continuously absorb lattice dislocations until their misorientation angle exceeds $\mathbf{15^\circ}$, transforming the subgrains into true, independent **high-angle grain boundaries (HAGBs)**.
   * The original coarse grains are thus fragmented into fine, sub-micron grains, significantly increasing yield strength according to the Hall–Petch relationship while reducing local dislocation pile-up lengths.

---

> **EXAM QUESTION — 2025 Mid-Sem — Q.3**
>
> **Q:** What is the mechanism behind the fragmentation of coarse grain to fine grains during rolling? *(2 Marks)*
>
> **Answer Summary:**
> The fragmentation of coarse grains into fine grains occurs through:
> 1. **Dislocation accumulation:** High-density dislocation generation and tangling along active slip planes.
> 2. **Cell subdivision:** Trapping of dislocations into low-energy dislocation structures (cell walls and dense dislocation bands) creating subgrains bounded by **low-angle grain boundaries** ($2^\circ < \theta < 15^\circ$).
> 3. **Subgrain rotation and dynamic recovery:** Continued rolling strain causes misorientation across these cell boundaries to increase progressively. When misorientation exceeds $\theta > 15^\circ$, the subgrain boundaries convert into **new high-angle grain boundaries**, producing permanent grain refinement (fragmentation).

---

### 2. The Bauschinger Effect

#### A. Definition

The **Bauschinger Effect** refers to the phenomenon where a material plastically deformed in one direction (e.g., tension) exhibits a **significantly lower yield stress when subsequently reloaded in the reverse direction (e.g., compression)** compared to continued forward deformation.

```
       Stress (σ)
           ^                 Forward Loading: Yields at σ_y1
           |         /---\   Continues to σ_max
           |        /     \
           |       /       \
  ---------+------/---------\-------------------------> Plastic Strain (ε)
           |     /           \
           |    /             \  Reverse Loading: 
           |   /               \ Yields early at |σ_y2| < |σ_y1|
           v
```

#### B. Microscopic Mechanisms

The Bauschinger effect originates from two primary dislocation mechanisms:

```
  FORWARD LOADING (Dislocations Pile Up)       REVERSE LOADING (Aided by Back Stress)
  
       Applied Shear Stress τ                       Reverse Shear Stress (-τ)
             ========>                                     <========
  [Source] ------------------| Barrier      [Source] <==================| Barrier
           T   T   T   T   T |                       <--   <--   <--
             Back Stress τ_b                               Back Stress τ_b
             <--------                                     <--------
  (τ_eff = τ - τ_b; pile-up opposes forward)    (τ_eff = |-τ| + τ_b; back stress aids reverse flow)
```

1. **Long-Range Internal Back-Stresses ($\tau_b$):**
   * During forward plastic flow, gliding dislocations encounter impenetrable barriers (such as grain boundaries, second-phase precipitates, or sessile dislocation locks).
   * Dislocations pile up against these obstacles. The mutual elastic repulsion among like-signed dislocations in the pile-up exerts a **long-range internal back-stress ($\tau_b$)** that acts in the direction opposite to forward loading.
   * To continue forward flow, the applied stress must overcome both the lattice friction and this repulsive back-stress:
     $$\tau_{\text{effective, forward}} = \tau_{\text{applied}} - \tau_b$$
   * When the load is reversed, this internal back-stress **assists dislocation motion** in the backward direction:
     $$\tau_{\text{effective, reverse}} = \tau_{\text{applied, reverse}} + \tau_b$$
   * As a result, reverse dislocation motion initiates at a substantially lower applied external stress ($\sigma_{y,\text{reverse}} < \sigma_{y,\text{forward}}$).
2. **Dislocation Annihilation and Directional Obstacle Resistance:**
   * Dislocations moving forward leave behind unpinned loops and debris.
   * When the stress direction is inverted, newly emitted dislocations of opposite sign can glide freely through the obstacle-depleted channels left behind or **annihilate existing dislocations of opposite sign**:
     $$(\perp) + (\top) \longrightarrow \text{annihilation (perfect lattice)}$$
   * This annihilation reduces total dislocation density and debris, producing transient softening in the reverse path.

#### C. Cyclic Softening vs. Cyclic Hardening

* Under symmetric cyclic loading ($\pm \sigma$), the peak stress required to enforce a given strain amplitude varies with cycle number $N$:
  1. **Cyclic Hardening:** Annealed or initially soft metals (low starting dislocation density) generate new dislocations that tangle and form cell walls, increasing flow stress with cycle count.
  2. **Cyclic Softening:** Initially heavily cold-worked or precipitation-hardened alloys undergo dislocation rearrangement into lower-energy cell walls, subcell coarsening, or precipitate shearing (loss of order), lowering flow stress over successive cycles.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.4 / 2025 Mid-Sem — Q.4 / 2022 Mid-Sem — Q.10 / 2021 Mid-Sem — Q.3**
>
> **Q:** Explain the Bauschinger Effect in detail. Why is the yield stress in the forwarding direction always greater than the yield stress in the backward direction? *(5 Marks)*
>
> **Answer Outline:**
>
> * **Definition:** Define the Bauschinger effect: plastic prestrain in one direction decreases yield stress in the opposing reverse direction. Draw the forward-reverse hysteresis loop.
> * **Derivation of Yielding Asymmetry:**
>   * In the forward direction, dislocations pile up at barriers, producing a back-stress $\tau_b$. Flow requires:
>     $$\tau_F = \tau_0 + \tau_b$$
>   * In the reverse direction, the sign of applied stress flips, while the elastic back-stress $\tau_b$ drives dislocations away from the pile-up back toward their sources. Reverse yielding begins when:
>     $$\tau_R = \tau_0 - \tau_b$$
>   * Clearly:
>     $$\mathbf{\tau_F - \tau_R = 2\tau_b > 0 \implies \tau_F > \tau_R}$$
> * **Role of Annihilation:** Dislocations of opposing Burgers vectors meet and annihilate during reverse stroke, reducing flow resistance further.

---

### 3. Dislocation Multiplication Mechanisms

Plastic deformation multiplies dislocation density from $\sim 10^6 - 10^8 \text{ cm}^{-2}$ (annealed state) to $\sim 10^{11} - 10^{12} \text{ cm}^{-2}$ (heavily cold worked). Two primary mechanisms operate in single crystals:

1. **The Frank-Read Source** (active multiplication)
2. **Lomer-Cottrell Locks** (sessile dislocation formation & forest hardening)

#### A. Mechanism 1: The Frank-Read Source

A segment of a dislocation line of length $L$ lies in a slip plane and is pinned at both ends by points $A$ and $B$ (e.g., node points of a dislocation network, impurity clusters, or sessile junctions).

```
   Stage (a)           Stage (b)           Stage (c)           Stage (d)           Stage (e)
   
       A                   A                   A                   A                    A
       |                   (                   (                   (                    |
       |                    \                 / \                 /   \                 |
       |                     )               (   )               (     )         O Loop |
       |                    /                 \ /                 \   /                 |
       |                   (                   (                   (                    |
       B                   B                   B                   B                    B
   Initial Line        Bow-out under      Critical state       Loop wraps        Pinch-off &
   pinned at A,B         stress τ         R = L/2 (semicircle)  around nodes      Regeneration
```

* **Step-by-step Operation:**
  1. **Initial State (a):** Dislocation segment $AB$ lies straight in its slip plane under zero stress.
  2. **Bow-Out (b):** Upon applying shear stress $\tau$, Peach-Koehler force $F = \tau b$ pushes the segment outward into a circular arc of radius $R$:
     $$\tau = \frac{Gb}{2R}$$
  3. **Critical State (c):** As $\tau$ increases, radius $R$ decreases until it reaches a minimum value equal to half the pinning distance:
     $$R_{\text{crit}} = \frac{L}{2}$$
     The **critical stress ($\tau_{\text{crit}}$)** required to activate the Frank-Read source is:
     $$\mathbf{\tau_{\text{crit}} = \frac{Gb}{L}}$$
  4. **Unstable Expansion (d):** Once the segment expands past the semicircular configuration, it becomes unstable and expands rapidly at lower stresses, curling around the pinning points $A$ and $B$.
  5. **Annihilation and Pinch-Off (e):**
     * The trailing segments behind the pins wrap around until they encounter each other.
     * Because the two colliding segments have identical line directions but opposite senses of Burgers vector, they **mutually annihilate** on contact:
       $$(\hat{t}, \vec{b}) + (-\hat{t}, \vec{b}) \longrightarrow 0$$
     * This creates a **closed, expanding dislocation loop** enclosing $A$ and $B$, while simultaneously **regenerating the original pinned segment $AB$**.
  6. **Repetition:** The regenerated line repeats the cycle continuously under sustained shear stress, generating thousands of concentric dislocation loops.

#### B. Mechanism 2: Sessile Dislocations & Lomer-Cottrell Barriers

When dislocations moving on two intersecting slip planes meet at the line of plane intersection, they react. If the product dislocation has a Burgers vector that does not lie on any easy glide plane, it becomes permanently immobile (**sessile**).

```
          (111) plane                    (11-1) plane
          \                                /
           \   b_1 = a/2[0 1 -1]          /   b_2 = a/2[1 0 1]
            \                            /
             \                          /
              \                        /
               \                      /
                \                    /
                 v                  v
                   *------------------  Line of intersection [1 -1 0]
                   |
                   | Product Dislocation:
                   | b_3 = a/2[1 1 0]
                   v
                   Lies on (001) plane! (Non-slip plane in FCC -> SESSILE LOCK)
```

#### C. Energy Criterion (Frank's Rule)

The elastic strain energy per unit length of a dislocation is proportional to the square of its Burgers vector:
$$E \propto |\vec{b}|^2$$

A dislocation reaction $\vec{b}_1 + \vec{b}_2 \to \vec{b}_3$ is energetically favorable (attractive) if:
$$\mathbf{b_1^2 + b_2^2 > b_3^2}$$

If $b_1^2 + b_2^2 < b_3^2$, the dislocations elastically **repel** each other.

#### D. Mathematical Example of Lomer-Cottrell Formation in FCC

Consider two glissile dislocations in an FCC lattice gliding on two different $\\{111\\}$ slip planes:

* Dislocation 1 glides on plane $(111)$ with Burgers vector:
  $$\vec{b}_1 = \frac{a}{2}[0, 1, \bar{1}]$$
* Dislocation 2 glides on plane $(11\bar{1})$ with Burgers vector:
  $$\vec{b}_2 = \frac{a}{2}[\bar{1}, 0, 1]$$

1. **Dislocation Reaction:**
   $$\vec{b}_3 = \vec{b}_1 + \vec{b}_2 = \frac{a}{2}[0 - 1, \ 1 + 0, \ -1 + 1] = \mathbf{\frac{a}{2}[\bar{1}, 1, 0]}$$
2. **Frank's Energy Check:**
   $$b_1^2 = \left(\frac{a}{2}\right)^2 (0^2 + 1^2 + (-1)^2) = \frac{2a^2}{4} = \frac{a^2}{2}$$
   $$b_2^2 = \left(\frac{a}{2}\right)^2 ((-1)^2 + 0^2 + 1^2) = \frac{2a^2}{4} = \frac{a^2}{2}$$
   $$b_1^2 + b_2^2 = \frac{a^2}{2} + \frac{a^2}{2} = a^2$$
   $$b_3^2 = \left(\frac{a}{2}\right)^2 ((-1)^2 + 1^2 + 0^2) = \frac{2a^2}{4} = \frac{a^2}{2}$$
   Since:
   $$\mathbf{b_1^2 + b_2^2 = a^2 > b_3^2 = \frac{a^2}{2}}$$
   The reaction releases energy ($\Delta E = -a^2/2 < 0$), meaning the two dislocations **strongly attract and react spontaneously**.
3. **Determination of the Slip Plane of $\vec{b}_3$:**
   The product dislocation line lies along the line of intersection of the two planes $(111)$ and $(11\bar{1})$. The intersection direction $\vec{u}$ is given by the cross product of the plane normals:
   $$\vec{u} = [1, 1, 1] \times [1, 1, -1] = [ -1 - 1, \ 1 - (-1), \ 1 - 1 ] = [-2, 2, 0] \propto [\bar{1}, 1, 0]$$
   Notice that the line direction $\vec{u} = [\bar{1}, 1, 0]$ is **parallel to the Burgers vector** $\vec{b}_3 = \frac{a}{2}[\bar{1}, 1, 0]$ (pure screw character along the intersection).

   The slip plane containing this dislocation must contain both $\vec{b}_3$ and the plane formed by subsequent partial reactions. More critically, when the leading partials of extended dislocations react, they create a sessile edge dislocation whose slip plane normal $\vec{n} = (hkl)$ is given by the Weiss zone law with line direction and $\vec{b}_3$:
   $$\vec{n} = [1, 1, 1] - [1, 1, -1] \propto \mathbf{(001)}$$
   * **Crucial Physical Fact:** In FCC metals, $\\{001\\}$ planes are **not close-packed** and do not serve as slip planes at ordinary temperatures.
   * Therefore, the product dislocation is physically **locked in the $(001)$ plane and cannot glide**.
   * It forms a rigid, immovable obstacle known as a **Lomer-Cottrell Lock (Barrier)**.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.7 / 2025 Mid-Sem — Q.7 / 2022 Mid-Sem — Q.9 / 2021 Mid-Sem — Q.4**
>
> **Q:** What is the possibility of the plane of the sessile dislocations in the case of FCC metal and Why? *(1+1 Marks)*
>
> **Q:** How sessile dislocations were formed? Explain the strain hardening mechanism through the sessile dislocations / Lomer-Cottrell barrier. *(1+3 Marks)*
>
> **Answer:**
>
> 1. **Plane of Sessile Dislocation:** The slip plane of the Lomer-Cottrell sessile dislocation in FCC is a **$\\{001\\}$ plane**, such as $(001)$ or $(100)$.
> 2. **Why It is Sessile:** In FCC crystals, slip occurs almost exclusively on the $\\{111\\}$ close-packed planes because they possess the maximum interplanar spacing and lowest Peierls stress. Because $\\{001\\}$ planes have higher Peierls resistance and the Burgers vector does not lie on a $\\{111\\}$ glide plane, the dislocation line cannot move under normal shear stresses.
> 3. **Strain Hardening Mechanism:**
>    * When mobile dislocations glide on their respective $\\{111\\}$ planes, they cannot cut through or bypass the immobile Lomer-Cottrell lock.
>    * Subsequent trailing dislocations on both slip systems pile up behind this barrier.
>    * These dislocation pile-ups produce massive long-range elastic back-stresses, blocking further dislocation motion on both planes.
>    * To continue plastic flow, a much higher applied stress is required to either force dislocations past the pile-up or activate secondary, less favorable slip systems. This directly causes **rapid Stage II strain hardening (work hardening)**.

---

<a name="part-4"></a>
## Part 4: Strengthening Mechanisms in Metals

**Exam Questions Covered:** 2024 Q.9; 2022 Q.1, Q.2, Q.3 & Q.11; End-Sem 2024 Q.1 & Q.2; End-Sem 2022 Q.10

---

### 1. Overview of Strengthening Mechanisms

Because plastic deformation in metals is governed by the movement of dislocations, **all strengthening mechanisms rely on restricting, impeding, or arresting dislocation motion**.

The six primary strengthening mechanisms are:

1. **Grain Boundary Strengthening (Hall–Petch Strengthening)**
2. **Yield Point Phenomenon & Strain Aging**
3. **Solid Solution Strengthening (Interstitial & Substitutional)**
4. **Precipitation & Dispersion Strengthening (Particle Hardening)**
5. **Strain Hardening / Work Hardening (Dislocation–Dislocation Interactions)**
6. **Transformation Hardening (e.g., Martensitic transformation in steels)**

---

### 2. Grain Boundary Strengthening

#### A. Mechanism

* A polycrystalline material consists of many grains of different crystallographic orientations separated by **grain boundaries**.
* Grain boundaries act as strong obstacles to dislocation motion for two main reasons:
  1. **Crystallographic Misorientation:** A dislocation gliding within Grain 1 must change its glide direction and slip plane upon crossing the boundary into Grain 2 because the slip systems do not align.
  2. **Atomic Disorder:** The grain boundary is a region of atomic mismatch and high disorder, creating a local energy barrier that prevents straightforward dislocation continuity.

```
       Grain 1 (Orientation A)        Grain 2 (Orientation B)
      +------------------------+--------------------------+
      |      Slip plane        |                          |
      |   ===================  |                          |
      |   T   T   T   T   T   *|                          |
      |                        |  Dislocation nucleated   |
      |   Dislocation pile-up  |  in Grain 2 by stress    |
      |   at grain boundary    |  concentration           |
      +------------------------+--------------------------+
                           Grain Boundary
```

#### B. The Dislocation Pile-up Model

* Gliding dislocations are halted at the grain boundary, forming a **dislocation pile-up**.
* If $n$ dislocations are pushed against the boundary under an effective shear stress $\tau$, the stress concentration acting on the leading dislocation is:
  $$\tau_{\text{tip}} \approx n \tau$$
* Because the number of dislocations that can fit in a pile-up is proportional to the distance to the source (which scales with grain diameter $d$), larger grains support longer pile-ups and generate higher tip stress concentrations at lower applied stress.
* In fine-grained metals, the pile-up length is severely restricted by small $d$. Consequently, a much higher applied stress is required to generate the critical stress at the boundary necessary to activate or nucleate dislocation sources in the adjacent grain.

#### C. The Hall–Petch Relation

$$\mathbf{\sigma_y = \sigma_0 + \frac{k_y}{\sqrt{d}} = \sigma_0 + k_y d^{-1/2}}$$

Where:

* $\sigma_y$ = Yield strength of the polycrystalline material.
* $\sigma_0$ = Friction stress (lattice resistance to dislocation motion for an infinitely large single crystal).
* $k_y$ = Locking parameter or Hall–Petch slope (measure of boundary resistance).
* $d$ = Average grain diameter.

#### D. Reverse Hall–Petch Effect

* When grain size is reduced to the nanocrystalline regime (typically **$d < 10 \text{ to } 15 \text{ nm}$**), the conventional Hall–Petch relationship breaks down.
* At this scale, grains are too small to sustain even a minimal dislocation pile-up (requiring at least $\sim 20\text{–}50$ dislocations).
* Deformation shifts from dislocation-mediated plasticity to **grain boundary sliding and Coble creep**.
* As a result, below $10\text{–}15 \text{ nm}$, the material softens: **strength decreases as grain size decreases** ($\frac{d\sigma_y}{dd} > 0$).

---

### 3. Yield Point Phenomenon

The **yield point phenomenon** is a sharp transition from elastic to plastic deformation accompanied by an abrupt stress drop, prominently observed in annealed **low-carbon (mild) steels** and some non-ferrous alloys (e.g., Al-Mg, brass).

```
   Stress (σ)
       ^            Upper Yield Point (UYP)
       |                 A
       |                / \
       |               /   \
       |   Elastic    /     *------*------* B (Lower Yield Point)
       |    Limit    /        \____/\____/  Lüders Strain Region (Plateau)
       |            /                    \
       |           /                      \___________ Strain Hardening
       |          /                                    Region
       +---------+-----------------------------------------------> Strain (ε)
```

#### A. Microscopic Mechanism (The Cottrell Atmosphere)

1. **Lattice Distortions Around Edge Dislocations:**
   * An edge dislocation creates a **compressive strain field** above the slip plane (around the extra half-plane of atoms) and a **tensile strain field** below the slip plane.
2. **Solute Segregation:**
   * Small interstitial solute atoms such as **Carbon ($\text{C}$)** and **Nitrogen ($\text{N}$)** are too large for the normal interstitial voids in BCC $\alpha$-iron, creating local dilatational strain.
   * Driven by elastic strain energy minimization, $\text{C}$ and $\text{N}$ atoms diffuse toward the **dilated, tensile region below the extra half-plane** of edge dislocations.
   * This dense solute segregation forms an anchored cloud called a **Cottrell Atmosphere**.

   ```
                 EXTRA HALF PLANE (Compression)
                      O     O     O
                      O     O     O
                  --------------------- Slip plane
                      O   o   o   O
                           C, N (Solutes)
                  TENSILE REGION (Cottrell Atmosphere)
   ```

3. **Upper Yield Point (UYP, Point $A$):**
   * The solute atoms pin the dislocations firmly within deep potential energy wells.
   * To initiate plastic deformation, a very high stress (the UYP) is required to either **tear (unpin) dislocations away from their Cottrell atmospheres** or rapidly nucleate new, unpinned dislocations.
4. **Yield Drop & Lower Yield Point (LYP, Point $B$):**
   * Once pulled free from their solute clouds, dislocations can glide through the lattice at a substantially lower stress because they no longer carry the heavy interstitial atmosphere:
     $$\sigma_{\text{unpinned}} \ll \sigma_{\text{pinned}}$$
   * The stress drops abruptly from the UYP to the LYP.
5. **Lüders Bands & Yield Plateau:**
   * Plastic deformation does not occur homogeneously throughout the gauge length.
   * Instead, localized bands of plastic deformation, termed **Lüders Bands**, form at stress concentrations (near the specimen grips) oriented at approximately $\sim 45^\circ$ or $50^\circ$ to the tensile axis.
   * These bands propagate steadily along the length of the specimen at constant lower yield stress until they sweep through the entire gauge length.
   * Once the entire gauge length has undergone this initial Lüders strain, uniform **strain hardening** begins.

**Note:** High-carbon steels do not exhibit a distinct sharp yield point drop because extensive carbide precipitates ($\text{Fe}_3\text{C}$) and high initial forest dislocation densities prevent collective unpinning.

---

> **EXAM QUESTION — 2024 Mid-Sem — Q.9 / 2022 Mid-Sem — Q.1 / End-Sem 2024 — Q.1**
>
> **Q:** Write down the different types of strengthening mechanisms. Explain the yield point phenomenon in detail. *(1+2 Marks)*
>
> **Answer:**
>
> **Part 1: Types of Strengthening Mechanisms** *(1 Mark)*
> All mechanisms act by impeding dislocation motion:
>
> 1. **Grain Boundary Strengthening (Hall–Petch):** Grain boundaries act as barriers to slip; $\sigma_y = \sigma_0 + k_y d^{-1/2}$.
> 2. **Yield Point Phenomenon & Strain Aging:** Interstitial $\text{C}$ and $\text{N}$ atoms pin dislocations through Cottrell atmospheres.
> 3. **Solid Solution Strengthening:** Substitutional and interstitial solutes create elastic strain fields that interact with dislocations.
> 4. **Precipitation / Dispersion Strengthening:** Coherent particles are sheared (underaged) or bypassed by Orowan looping (overaged).
> 5. **Strain (Work) Hardening:** Dislocation–dislocation interactions and pile-ups raise the flow stress.
> 6. **Transformation Hardening:** A phase transformation (e.g., martensite in steels) creates a dense, heavily strained substructure.
>
> **Part 2: Yield Point Phenomenon** *(2 Marks)*
> Annealed low-carbon (mild) steel shows a sharp **upper yield point (UYP)**, an abrupt stress drop, and a **lower yield point (LYP)** plateau before normal strain hardening begins.
>
> * **Cause:** Interstitial $\text{C}$ and $\text{N}$ atoms diffuse to the dilated (tensile) region below the extra half-plane of edge dislocations, forming **Cottrell atmospheres** that pin the dislocations.
> * **UYP:** A high stress is required to tear the dislocations free of their solute atmospheres.
> * **Yield drop to LYP:** Once unpinned, dislocations glide at a much lower stress, causing the abrupt drop.
> * **Lüders bands:** Localized plastic bands nucleate at stress concentrations (e.g., near the grips) and propagate along the gauge length at constant LYP stress (the Lüders plateau). Uniform strain hardening follows after the bands sweep the entire gauge length.

---

### 4. Strain Aging and Dynamic Strain Aging (DSA)

#### A. Static Strain Aging

If a low-carbon steel specimen is strained past its yield point through the Lüders region into the strain hardening zone (Point $X$), and the load is completely removed:

```
   Stress (σ)
       ^                 Reloaded after aging (Time t or mild heat):
       |                 New higher UYP reappears! (Curve 3)
       |                 /---\
       |     (Curve 1)  /     \
       |       /\      /       *------
       |      /  \____/  |    /
       |     /        |  |   /
       |    /         |  |  /  Reloaded immediately:
       |   /          |  | /   No yield drop, smooth flow (Curve 2)
       +--+-----------+--++--------------------------------------> Strain (ε)
          0           Unload
```

* **Immediate Reloading (Curve 2):**
  * If the specimen is reloaded immediately, yielding resumes smoothly at the unloading stress level **without any yield drop or upper yield point**.
  * *Reason:* Dislocations are already unpinned and free of solute atmospheres.
* **Reloading After Aging Time / Heat (Curve 3):**
  * If the unloaded specimen is allowed to rest at room temperature for several weeks, or aged at a moderate temperature ($60^\circ\text{C} - 100^\circ\text{C}$ for a few hours), the mobile interstitial $\text{C}$ and $\text{N}$ atoms have sufficient time to diffuse back to the newly formed, stationary dislocations.
  * New Cottrell atmospheres form around these dislocations.
  * Upon retesting, **the yield point phenomenon reappears**, with an **increased yield strength ($\sigma_y \uparrow$)**, an **increased tensile strength ($\text{UTS} \uparrow$)**, and a **decrease in ductility ($\%EL \downarrow$)**. This process is termed **Static Strain Aging**.

#### B. Dynamic Strain Aging (DSA) & The Portevin–Le Chatelier (PLC) Effect

* **Definition:** Dynamic Strain Aging occurs when solute diffusion takes place **simultaneously with plastic deformation** at intermediate working temperatures (typically $100^\circ\text{C} - 250^\circ\text{C}$ in steels, or room temperature in certain Al-Mg alloys) and specific strain rates.

```
   Stress (σ)
       ^
       |          /\    /\    /\    /\
       |         /  \  /  \  /  \  /  \    Serrations (Portevin-Le Chatelier effect)
       |     /\ /    \/    \/    \/    \
       |    /  *
       |   /
       +--+----------------------------------------------------> Strain (ε)
```

* **Mechanism:**
  * When the average velocity of mobile dislocations ($v_d$) matches the diffusion velocity of interstitial solute atoms ($v_s$):
    $$v_d \approx v_s$$
  * While moving dislocations temporarily halt at obstacles (e.g., forest dislocations), mobile solutes diffuse rapidly and pin them.
  * The applied stress must rise to unpin the dislocations. Once unpinned, they accelerate away until they arrest at the next obstacle, where solutes catch up and pin them again.
  * This repeated cycle of pinning and unpinning creates **serrated yielding (jerky flow)** on the stress–strain curve.
* **Key Characteristics of DSA:**
  1. Pronounced serrations in the plastic regime of the stress–strain curve.
  2. **Negative Strain Rate Sensitivity (NSRS):** Higher strain rates give solutes less time to pin dislocations, lowering flow stress.
  3. Reduction in ductility and high work hardening rate.

---

> **EXAM QUESTION — 2022 Mid-Sem — Q.1 / End-Sem 2024 — Q.1**
>
> **Q:** Differentiate between strain aging and dynamic strain aging with the help of stress–strain response. *(1+1 Marks)*
>
> **Answer Comparison:**
>
> | Feature | Static Strain Aging | Dynamic Strain Aging (DSA) |
> | :--- | :--- | :--- |
> | **Occurrence** | Occurs **after** deformation, during a static holding period (at room temp or moderate annealing). | Occurs **during** plastic deformation at intermediate temperatures ($100\text{–}250^\circ\text{C}$). |
> | **Dislocation State** | Solutes diffuse to stationary dislocations created by prior prestrain. | Solutes diffuse to moving dislocations that are temporarily arrested at obstacles. |
> | **Stress–Strain Curve** | Single sharp upper and lower yield point reappears upon reloading; overall curve is smooth. | Produces continuous, repetitive **serrations (jerky flow / PLC effect)** throughout the plastic curve. |
> | **Rate Dependency** | Governed by aging time and storage temperature before test. | Strongly dependent on the competition between **strain rate ($\dot{\epsilon}$)** and **solute diffusion coefficient ($D$)**. |

---

### 5. Solid Solution Strengthening

The introduction of foreign solute atoms into a pure host metal lattice impedes dislocation glide by creating local elastic strain fields that interact with the strain fields of dislocations.

```
       Substitutional Solute (Larger Atom)             Interstitial Solute
              O     O     O     O                         O     O     O
              O   ( O )   O     O                         O   o   O     O
              O     O     O     O                         O     O     O
          (Compressive stress field)                  (Tetragonal distortion)
```

1. **Types of Solid Solutions:**
   * **Substitutional:** Solute atoms replace solvent atoms on regular lattice sites. If the solute atom is larger, it induces compressive stress; if smaller, it induces tensile stress.
   * **Interstitial:** Small solute atoms (e.g., $\text{C, N, H, B}$) occupy interstitial void spaces between solvent atoms, creating non-spherical (tetragonal) distortion fields (as in BCC $\alpha$-Fe).
2. **Hume-Rothery Rules for Solid Solubility:**
   * **Atomic size factor:** Difference in atomic radii ($\Delta r$) must be $< 15\%$.
   * **Crystal structure:** Solute and solvent must possess the same crystal structure for high solubility.
   * **Electronegativity:** Electronegativity values must be similar (large differences favor intermetallic compound formation).
   * **Valency:** A metal has greater solubility for an element of higher valency than of lower valency.
3. **Effect on Stress–Strain Behavior:**
   * As solute concentration ($c$) increases, both the yield strength ($\sigma_y$) and ultimate tensile strength ($\text{UTS}$) increase:
     $$\Delta \sigma_y \propto c^n \quad (n \approx 1/2 \text{ to } 2/3)$$
   * Young's modulus ($E$, the initial elastic slope) remains virtually unchanged because it depends primarily on the base solvent matrix bonds.
   * Ductility decreases moderately with increasing solute content.

---

> **EXAM QUESTION — 2022 Mid-Sem — Q.2**
>
> **Q:** Explain solid solution strengthening. What is the effect of solute content on the stress–strain response? *(1+1 Marks)*
>
> **Answer:**
>
> **Part 1: Solid Solution Strengthening** *(1 Mark)*
> Foreign solute atoms dissolved in the host lattice create local elastic strain fields that interact with the strain fields of dislocations and impede their glide:
>
> * **Substitutional solutes:** Replace solvent atoms on regular lattice sites; larger atoms induce compressive stress, smaller atoms induce tensile stress.
> * **Interstitial solutes:** Small atoms (e.g., $\text{C, N, H, B}$) occupy interstitial voids between solvent atoms and produce non-spherical (tetragonal) distortion fields.
> * These solute strain fields pin dislocations and raise the stress required to initiate and sustain plastic flow.
>
> **Part 2: Effect of Solute Content on the Stress–Strain Response** *(1 Mark)*
> Recall the stress–strain plot of pure Al vs. $\text{Al}+c_1$ vs. $\text{Al}+c_2$ where $c_2 > c_1$:
>
> * **Elastic slope ($E$) is essentially unchanged:** Young's modulus depends primarily on the base solvent matrix bonds.
> * **Yield strength ($\sigma_y$) and UTS increase** with solute content: $\Delta\sigma_y \propto c^n$ with $n \approx 1/2$ to $2/3$.
> * **Ductility (failure elongation) decreases** progressively as the solute content rises.

---

### 6. Fine Particle / Precipitation Strengthening

Finely dispersed second-phase particles act as strong barriers to dislocation motion. Particles may be classified as:

* **Precipitates:** Thermally unstable; form via phase transformations during solid-state aging heat treatments (e.g., $\text{Al}_2\text{Cu}$, $\text{Mg}_2\text{Si}$). Coherent or semi-coherent at small sizes.
* **Dispersoids:** Thermally stable; introduced externally (e.g., via oxide dispersion strengthening / powder metallurgy) and remain undissolved up to near the melting point. Typically large and incoherent.

#### A. Dislocation–Particle Interaction Mechanisms

```
     1. SHEARING / CUTTING MECHANISM                    2. OROWAN BYPASSING / LOOPING
           (For r < r_c, Coherent)                           (For r > r_c, Incoherent)
     
        Dislocation Line                              Dislocation bows between particles
        =============>                                     )       )       )
             |                                             |       |       |
             O Particle                                    O       O       O
             |                                              \     / \     /
        Dislocation cuts through;                         Bypasses leaving residual Orowan loop
        creates sheared step at particle                   O---O   O---O   O---O
             |                                             (O)     (O)     (O)
           --O--                                           Loop left around particle
```

1. **Shearing / Cutting Mechanism (Particle size $r < r_c$):**
   * Operates when precipitates are small and coherent with the matrix lattice.
   * A gliding dislocation shears through the precipitate, creating new particle–matrix interface area, breaking intermetallic bonds, and forcing the dislocation to overcome antiphase boundary (APB) or coherency strain energy.
   * **Strength increases with precipitate radius ($r$):**
     $$\mathbf{\tau_{\text{cutting}} \propto r^{1/2}}$$
2. **Orowan Bypassing / Looping Mechanism (Particle size $r > r_c$):**
   * Operates when precipitates are large, widely spaced, or incoherent (such that the stress required to cut the particle exceeds that needed to bow around it).
   * The dislocation bows outward between adjacent particles separated by interparticle spacing $L$, forming semicircular loops that pinch off, leaving a **residual dislocation loop (Orowan loop)** encircling each particle.
   * **Strength decreases with precipitate radius ($r$):**
     $$\mathbf{\tau_{\text{Orowan}} \approx \frac{G b}{L} \propto \frac{1}{r}}$$

#### B. Critical Particle Radius ($r_c$ or $d_c$)

```
   Yield Strength (σ_y)
       ^
       |                       Peak Aged (r = r_c)
       |                               *
       |                              / \
       |    Underaged                /   \     Overaged
       |   (Shearing / Cutting)     /     \   (Orowan Bypassing)
       |    τ ∝ r^(1/2)            /       \   τ ∝ 1/r
       |                          /         \
       +-------------------------+-----------+-------------------> Precipitate Radius (r)
                                  r_c (Critical size)
```

The transition between cutting and looping defines the **critical particle size ($r_c$)**:
$$\tau_{\text{cutting}} = \tau_{\text{Orowan}} \implies \mathbf{r = r_c}$$

* **$r < r_c$ (Underaged):** Cutting mechanism controls flow stress. Strength increases with aging time.
* **$r = r_c$ (Peak Aged):** Maximum yield strength is achieved.
* **$r > r_c$ (Overaged):** Orowan looping controls flow stress. Strength progressively drops as precipitates coarsen (Ostwald ripening).

---

### 7. Precipitation Hardening in Al-Mg-Si Alloys

In the age-hardenable $\text{Al-Mg-Si}$ system (6000-series aluminum alloys), hardening is achieved through the following sequence:

#### A. Heat Treatment Steps

1. **Solution Heat Treatment:** Heated to $\sim 500\text{–}540^\circ\text{C}$ to dissolve all solute into a single-phase solid solution.
2. **Quenching:** Rapidly cooled in water to room temperature to form a **Supersaturated Solid Solution (SSSS)** with trapped excess vacancies.
3. **Artificial Aging:** Reheated to an intermediate temperature ($150\text{–}200^\circ\text{C}$) for controlled precipitation.

#### B. Precipitation Sequence

$$\mathbf{\text{SSSS} \longrightarrow \text{Solute Clusters / GP Zones} \longrightarrow \beta'' \longrightarrow \beta' \longrightarrow \beta \ (\text{Mg}_2\text{Si})}$$

1. **GP (Guinier–Preston) Zones:** Extremely fine, fully coherent, solute-rich spherical clusters ($1\text{–}3\text{ nm}$). Easily sheared by dislocations.
2. **$\beta''$ Phase:** Fully coherent, needle-like precipitates along $\langle 100\rangle_{\text{Al}}$ directions. Generates strong coherency strain fields in the matrix and delivers the **peak hardness and yield strength**.
3. **$\beta'$ Phase:** Semi-coherent, rod-shaped precipitates. Coherency begins to break down.
4. **$\beta$ Phase ($\text{Mg}_2\text{Si}$):** Completely incoherent, coarse plate-like equilibrium phase ($> 100\text{ nm}$). Dislocations bypass these particles via Orowan looping.

---

> **EXAM QUESTION — 2022 Mid-Sem — Q.3 & Q.11 / End-Sem 2024 — Q.2 / End-Sem 2022 — Q.10**
>
> **Q:** Explain (briefly) the influence of metastable to stable precipitates on the stress–strain response of the Al-Mg-Si alloy in detail with the help of a diagram and compare it with pure Al alloy. *(3+1 / 5 Marks)*
>
> **Q:** What is the effect of stable to metastable precipitates on the strength of Al-Mg-Si alloy? Explain it with the help of yield strength vs. aging time plot briefly. *(1+1 Marks)*
>
> **1. Yield Strength vs. Aging Time Plot:**
>
> ```
>    Yield Strength (σ_y)
>        ^                           Peak Aged (β'' needle-like)
>        |                                      *
>        |                                     / \
>        |                    Under Aged      /   \
>        |                   (GP Zones)      /     \     Over Aged
>        |                      /-----------/       \   (β' rod, β plate)
>        |                     /                     \_______
>        |         SSSS       /                              \
>        |       *-----------/                                \
>        +-------+---------------------------------------------+--------> Aging Time (t)
> ```
>
> * **SSSS:** Lowest initial strength; all solutes are in solid solution.
> * **Under-Aged (GP Zones):** Strength rises rapidly due to coherency strains and dislocation cutting of GP zones.
> * **Peak-Aged ($\beta''$):** Maximum yield strength; fine, high-density needle-shaped $\beta''$ precipitates provide maximum resistance at the critical transition radius $r_c$.
> * **Over-Aged ($\beta'$ and stable $\beta$):** Precipitates coarsen, lose coherency with the matrix, and interparticle spacing increases ($L \uparrow$). Dislocations easily bypass particles via Orowan looping, causing strength and hardness to fall.
>
> **2. Comparative Stress–Strain Curves:**
>
> ```
>    Stress (σ)
>        ^
>        |                       1. Peak Aged (β'') - Highest σ_y, lowest ductility
>        |                          /---\
>        |                         /     \
>        |              2. Under Aged (GP Zones)
>        |                   /---------\
>        |                  /           \
>        |       3. Over Aged (β' / β)   \
>        |            /-------------------\
>        |           /                     \
>        |        4. SSSS                   \
>        |         /-------------------------\
>        |        /                           \
>        |     5. Pure Al                      \
>        |       /------------------------------\  - Lowest σ_y, highest ductility
>        +------+--------------------------------+----------------------------> Strain (ε)
> ```
>
> **3. Detailed Comparison:**
> 1. **Pure Al:** Possesses no solute drag or precipitation barriers; yields at a very low stress ($\sigma_y \sim 20\text{–}30 \text{ MPa}$) but exhibits highest total elongation and ductility.
> 2. **SSSS:** Solutes in solution provide mild solid solution strengthening; yield stress increases slightly over pure Al, retaining excellent ductility.
> 3. **Under-Aged Condition (GP Zones):** Coherent clusters pin and impede dislocations via cutting; yield strength increases markedly with moderate ductility.
> 4. **Peak-Aged Condition ($\beta''$):** Dislocation motion is severely hindered by dense, coherent $\beta''$ needles; material achieves its **maximum yield and ultimate tensile strength ($\sigma_y \sim 350\text{–}400 \text{ MPa}$)**, accompanied by a substantial reduction in uniform elongation and failure ductility.
> 5. **Over-Aged Condition ($\beta'$ and stable $\beta$):** Large, incoherent precipitates offer less resistance to Orowan bypassing; yield strength drops relative to peak age, while elongation and ductile behavior recover.

---

<a name="exam-strategy--preparation-tips"></a>
## Exam Strategy & Preparation Tips

### Mid-Semester Revision Summary Checklist

| Concept | Key Governing Relation | Core Mechanism to Remember |
| :--- | :--- | :--- |
| **True vs. Engg Strain** | $\epsilon_T = \ln(1+\epsilon)$ | Additive over multistep deformation; net zero on complete reverse deformation. |
| **Theoretical Shear Strength** | $\tau_m \approx G/2\pi$ | Simultaneous bond shearing vs. real sequential dislocation glide ($100\times$ difference). |
| **Schmid's Law** | $\tau_{\text{CRSS}} = \sigma_y \cos\phi \cos\lambda$ | $\tau_{\text{CRSS}}$ is invariant material property; $\sigma_y$ varies with crystal orientation. |
| **Slip in FCC vs. BCC** | FCC: 12 systems; BCC: 48 systems | FCC produces straight slip lines; BCC exhibits wavy lines due to pencil glide / cross-slip. |
| **Slip vs. Twinning** | Fractional $b$ vs. integer $b$ | Slip lines polish away (surface steps); twins persist (internal lattice reorientation). |
| **Bauschinger Effect** | $\tau_{\text{reverse}} < \tau_{\text{forward}}$ | Pile-up back-stress ($\tau_b$) opposes forward flow, aids reverse flow; opposite-sign annihilation. |
| **Frank-Read Source** | $\tau_{\text{crit}} = Gb/L$ | Pinned segment bows to critical semicircle $R = L/2$, loops, annihilates, and regenerates. |
| **Lomer-Cottrell Lock** | $b_1^2 + b_2^2 > b_3^2$ | Glissile dislocations on intersecting $\\{111\\}$ form sessile dislocation on non-slip $\\{001\\}$ plane. |
| **Yield Point Phenomenon** | Upper & Lower Yield Points | Interstitial $\text{C/N}$ form Cottrell atmosphere below extra half-plane; Lüders band propagation. |
| **Dynamic Strain Aging** | Serrated yielding (PLC effect) | Solute diffusion speed matches dislocation glide speed ($v_s \approx v_d$); repeated catch-and-release. |
| **Precipitation Peak** | $r = r_c$ ($\tau_{\text{cutting}} = \tau_{\text{Orowan}}$) | Cutting dominates for small coherent particles; Orowan looping dominates for coarsened overaged particles. |

---

### Historical Paper Insights & Trends

Based directly on the historical papers (2021, 2022, 2024, 2025) and lecture notes, the mid-semester paper is **remarkably predictable** — the instructor repeats core questions almost verbatim every year.

#### The "Guaranteed 80%" (Questions that appear in virtually every exam)

1. **Schmid's Law & CRSS Derivation (Every single year — 5 Marks):**
   * Derivation of $\tau_{\text{RSS}} = \sigma \cos\phi \cos\lambda$.
   * Distinction between **Schmid Factor** (geometric, dimensionless, $0 \le m \le 0.5$) and **Schmid's Law / $\tau_{\text{CRSS}}$** (material constant, independent of orientation).
2. **The Bauschinger Effect / Forward vs. Reverse Yielding (Every single year — 4 to 5 Marks):**
   * Either asked directly as *"Explain Bauschinger effect"* or phrased as *"Why yield stress in forwarding direction is greater than backward direction?"*
   * Answer must feature: the **hysteresis loop diagram**, the **back-stress ($\tau_b$) pile-up equation**, and **opposite-sign dislocation annihilation**.
3. **Slip vs. Twinning & The Polishing Question (Every single year — 3 to 4 Marks):**
   * Difference table between Slip and Twin.
   * Conceptual question: *"Why slip lines disappear upon polishing, but twin planes / deformation bands do not?"*
4. **Dislocation Fundamentals & Vector Relations (Every single year — 3 to 4 Marks):**
   * Types (Edge, Screw, Mixed) paired with their Burgers vector relationships ($\vec{b} \perp \hat{t}$, $\vec{b} \parallel \hat{t}$, $0^\circ < \theta < 90^\circ$).
   * Glide vs. Climb vs. Cross-slip.
5. **Dislocation Multiplication Mechanisms (Rotates between two questions — 4 Marks):**
   * **Even years (2022, 2024):** Frank-Read Source (bow-out, semicircle $R = L/2$, loop pinch-off).
   * **Odd years / Variations (2021, 2025):** Lomer–Cottrell lock / Sessile dislocation (reaction on intersecting $\\{111\\}$ forming lock on $\\{001\\}$, Frank's $b^2$ rule).
6. **Slip Line Morphology in BCC vs. FCC (2022, 2024 — 2 Marks):**
   * Straight in FCC (planar slip on $\\{111\\}$) vs. Wavy in BCC (pencil glide, frequent cross-slip of screw dislocations among $\\{110\\}$, $\\{112\\}$, $\\{123\\}$).
7. **Theoretical vs. Real Shear Strength (2025, 2021 — 3 to 5 Marks):**
   * Derivation of $\tau_m \approx G/2\pi$ and why real yield strength is 100–1000 times lower (simultaneous bond breaking vs. sequential dislocation glide).

---

### Syllabus & Topic Priority Weightage

| Priority Tier | Topics | Expected Marks |
| :--- | :--- | :--- |
| **Tier 1 (Crucial — High Return)** | • CRSS derivation & Schmid factor<br>• Bauschinger effect & back stresses<br>• Frank-Read source & Lomer-Cottrell locks<br>• Slip vs. Twin + Polishing behavior | **~16 – 18 / 30 Marks** |
| **Tier 2 (Very High Probability)** | • Theoretical shear strength ($\tau_m \approx G/2\pi$)<br>• Yield point phenomenon & Cottrell atmosphere<br>• Wavy slip in BCC ($\alpha$-Fe) vs. straight in FCC<br>• True strain proof of additivity | **~8 – 10 / 30 Marks** |
| **Tier 3 (Concept Specifics)** | • Static vs. Dynamic strain aging (serrated flow)<br>• Al-Mg-Si aging curve & stress–strain response<br>• Coarse-to-fine grain fragmentation during rolling | **~4 – 6 / 30 Marks** |

---

### Tonight & Tomorrow Morning Preparation Strategy

Because the exam is imminent, **do not read unstructured theory**. Focus on reproducing **diagrams, equations, and concise bullet points**:

1. **Phase 1: Practice the 4 Essential Derivations (1 Hour)**
   * Grab a blank sheet of paper and write out without looking:
     1. **True vs. Engineering relations:** $\sigma_T = \sigma_e(1+\epsilon)$ and $\epsilon_T = \ln(1+\epsilon)$, followed by the 2-step additivity proof showing $\Sigma\epsilon_T = 0$ vs. $\Sigma\epsilon \neq 0$.
     2. **Frenkel's Sinusoidal Model:** $\tau = \tau_m \sin(2\pi x/b)$, small angle approximation $\tau = \tau_m(2\pi x/b)$, Hooke's Law $\tau = G(x/a) \implies \tau_m = \frac{G}{2\pi}$.
     3. **Schmid's Law:** Force resolution $F_D = F\cos\lambda$, area projection $A_s = A/\cos\phi \implies \tau_{\text{RSS}} = \sigma \cos\phi \cos\lambda$.
     4. **Lomer-Cottrell Reaction:** $\frac{a}{2}[0,1,\bar{1}] + \frac{a}{2}[\bar{1},0,1] = \frac{a}{2}[\bar{1},1,0]$, calculate $b_1^2 + b_2^2 > b_3^2$ ($a^2 > a^2/2$), show slip plane is $(001)$.
2. **Phase 2: Master the 5 Key Microstructural Sketches (45 Minutes)**
   * **Bauschinger Effect:** $\sigma\text{--}\epsilon$ cyclic curve + dislocation pile-up showing $\tau_{\text{applied}}$ and $\tau_b$.
   * **Frank-Read Source:** 5-stage bow-out sequence ending with the loop pinch-off.
   * **Yield Point Phenomenon:** Stress drop curve showing UYP, LYP, and Lüders band propagation + sketch of Cottrell atmosphere below extra half-plane.
   * **Al-Mg-Si Aging Sequence:** $\sigma_y$ vs. aging time showing Underaged (cutting) $\to$ Peak ($\beta''$) $\to$ Overaged (Orowan bypass) + comparative stress–strain curves.
   * **Grain Fragmentation:** 4-stage diagram showing grain elongation $\to$ cell walls/DDWs $\to$ subgrains ($2^\circ < \theta < 15^\circ$) $\to$ new fine grains ($\theta > 15^\circ$).
3. **Phase 3: Morning Warm-Up (30 Minutes Before Exam)**
   * Review vector conditions:
     * Edge: $\vec{b} \perp \hat{t}$
     * Screw: $\vec{b} \parallel \hat{t}$
     * Weiss Zone Law for finding slip directions on planes: $h \cdot u + k \cdot v + l \cdot w = 0$.
   * Memorize exact definitions: Schmid factor ($m$), $\tau_{\text{CRSS}}$, Cottrell atmosphere, Peierls–Nabarro stress.

---

### Question Attempt & Scoring Strategy in the Exam Hall

Note the paper header: **"Please be brief and to the point while answering."** The professor grades on **technical keywords, neat sketches, and equations**, not long narrative paragraphs.

#### A. How to Structure Every Answer to Get Full Marks

1. **Always State the Core Governing Relation First:**
   * If asked about CRSS, state $\tau_{\text{RSS}} = \sigma \cos\phi \cos\lambda$ right away.
   * If asked about Bauschinger, write $\tau_{\text{eff}} = \tau_{\text{applied}} - \tau_b$ and $\tau_{\text{rev}} = \tau_{\text{applied}} + \tau_b$ before writing words.
2. **Never Skip the Diagram (Even for 1- or 2-mark questions):**
   * For *"Why slip lines disappear on polishing..."*: Draw a simple surface step being sliced off vs. a twin boundary continuing into the bulk. This instantly secures the 2 marks.
   * For *"Yield point phenomenon..."*: Draw the UYP/LYP curve and label the Lüders strain region.
3. **Respect Sub-Question Mark Splits:**
   * If a question is marked **(3+2)**:
     * Part 1 (3 marks): Give the complete derivation with proper geometry diagrams.
     * Part 2 (2 marks): Present a clean 2-column comparative table (do not write paragraphs).
   * If a question is marked **(1+1+2)**:
     * 1 mark for definition.
     * 1 mark for types.
     * 2 marks for Burgers vector relationship ($\vec{b} \perp \hat{t}$ vs $\vec{b} \parallel \hat{t}$).

#### B. Time Management (30 Marks / Typically 60–90 Minutes)

* **First 5 Minutes:** Scan the paper and spot the familiar questions. Start immediately with the **derivation (CRSS or theoretical shear strength)** or the **Bauschinger effect**. These are mechanical, high-scoring questions that build momentum.
* **Next 40–50 Minutes:** Answer all descriptive and conceptual questions in crisp bullet points.
* **Final 10 Minutes:** Check all diagrams: Ensure all axes are labeled (e.g., $\sigma$ vs. $\epsilon$, $\tau$ vs. $\gamma$), vectors have arrows ($\vec{b}, \hat{t}$), and planes/directions have correct brackets ($\\{ \\}$ for planes, $\langle \rangle$ for directions, $( )$ for specific plane, $[ ]$ for specific direction).
