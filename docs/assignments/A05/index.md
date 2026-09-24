# A5 – [Bracket Design]

### 1. Assignment Objectives (in Simple Words)

* **Design for Strength & Safety:** Determine the minimum thickness/diameter for each structural feature on the bracket so that the material does not yield or break under a $600 \text{ lbf}$ load with a Factor of Safety of 4.
* **Design for Stiffness & Deflection:** Calculate the minimum required dimensions so that elastic deflection/stretching stays within $0.005 \text{ in}$ per feature.
* **Load Path Tracing:** Transfer calculated reaction forces sequentially from Feature A through Feature E to ensure static equilibrium across the entire mounting bracket assembly.
* **Manufacturing Precision (Fits):** Select appropriate ANSI B4.1 standard fits and tolerances for interface dimensions to ensure proper mechanical assembly with mating components.
* **Technical Documentation:** Present complete Free Body Diagrams (FBDs), step-by-step algebraic/numerical solutions, and multiview engineering drawings in your virtual portfolio site.

---

### 2. Material & Global Parameters Baseline

* **Material:** Steel (ASTM A36)
* **Applied Force ($F$):** $600 \text{ lbf}$ (Symmetric total force $2F_{\text{leg}} = 600 \text{ lbf} \implies F_{\text{leg}} = 300 \text{ lbf}$)
* **Yield Strength ($Y_s$):** $36,259.43 \text{ psi}$
* **Elastic Modulus ($E$):** $29,007,547.53 \text{ psi}$
* **Factor of Safety ($N_s$):** $4.0$
* **Allowable Stress ($\sigma_{\text{allow}}$):**

$$\sigma_{\text{allow}} = \frac{Y_s}{N_s} = \frac{36,259.43}{4.0} = 9,064.86 \text{ psi} \quad (\approx 9.06 \text{ ksi})$$



---

### 3. Calculating Dimensions from Stress Analysis: Feature A

Following the sequential load path (Appendix A & Appendix D guidelines), **Feature A** is the cylindrical support pin holding the polyester strap.

#### (a) Knowns

* Applied Load ($F$): $600 \text{ lbf}$ transverse point load at free end
* Pin Length ($L_A$): $2.00 \text{ in}$ (assumed based on strap width)
* Yield Strength ($Y_s$): $36,259.43 \text{ psi}$
* Factor of Safety ($N_s$): $4.0$
* Allowable Bending Stress ($\sigma_{\text{allow}}$): $9,064.86 \text{ psi}$

#### (b) Unknowns

* Required minimum pin radius ($r_{\text{stress}}$) and diameter ($d_{\text{stress}}$) based on bending stress.
* Support reaction force ($R_y$) and reaction moment ($M_{\max}$) at the connection interface.

#### (c) Assumptions

1. **Beam Model:** Feature A behaves as a solid circular cantilever beam rigidly fixed at $x = 0$.
2. **Loading:** Transverse point load $F = 600 \text{ lbf}$ applied at $x = L_A = 2.00 \text{ in}$.
3. **Shear Stress:** Direct shear failure is non-governing per prompt instructions.
4. **Material:** Homogeneous, linear-elastic A36 steel.

#### (d) Free Body Diagram (FBD)

* **At Support ($x = 0$):** Vertical reaction force $R_y = 600 \text{ lbf}$ (pointing upward) and reaction bending moment $M_{\max} = F \cdot L_A = 1,200 \text{ lb}\cdot\text{in}$ (counter-clockwise).
* **At Free End ($x = 2.00 \text{ in}$):** Downward force $F = 600 \text{ lbf}$ applied by the strap.

#### (e) Algebraic Model

Maximum bending moment occurs at the fixed support ($x = 0$):


$$M_{\max} = F \cdot L_A$$

Bending stress formula:


$$\sigma = \frac{M_{\max}}{Z} \le \sigma_{\text{allow}}$$

For a solid circular cross-section:


$$Z = \frac{\pi r^3}{4} = \frac{\pi d^3}{32}$$

Solving algebraically for required Section Modulus ($Z_{\text{req}}$) and minimum radius ($r_{\text{stress}}$):


$$Z_{\text{req}} = \frac{M_{\max}}{\sigma_{\text{allow}}} = \frac{F \cdot L_A}{\sigma_{\text{allow}}}$$

$$r_{\text{stress}} = \sqrt[3]{\frac{4 \cdot Z_{\text{req}}}{\pi}} = \sqrt[3]{\frac{4 \cdot F \cdot L_A}{\pi \cdot \sigma_{\text{allow}}}}$$

$$d_{\text{stress}} = 2 \cdot r_{\text{stress}}$$

#### (f) Numerical Solution

1. **Calculate Maximum Bending Moment:**

$$M_{\max} = (600 \text{ lbf}) \cdot (2.00 \text{ in}) = 1,200 \text{ lb}\cdot\text{in}$$


2. **Calculate Required Section Modulus ($Z_{\text{req}}$):**

$$Z_{\text{req}} = \frac{1,200 \text{ lb}\cdot\text{in}}{9,064.86 \text{ psi}} \approx 0.13238 \text{ in}^3$$


3. **Calculate Minimum Radius ($r_{\text{stress}}$):**

$$r_{\text{stress}} = \sqrt[3]{\frac{4 \cdot (0.13238)}{\pi}} = \sqrt[3]{0.16855} \approx \mathbf{0.5524 \text{ in}}$$


4. **Calculate Minimum Diameter ($d_{\text{stress}}$):**

$$d_{\text{stress}} = 2 \cdot 0.5524 \text{ in} = \mathbf{1.105 \text{ in}}$$



---

### Reaction Force Transfer to Feature B

The reaction forces at the base of Feature A become the applied loads for Feature B:

* **Transverse Force ($P_B$):** $R_y = 600 \text{ lbf}$
* **Moment ($M_B$):** $1,200 \text{ lb}\cdot\text{in}$

Whenever you are ready, let me know to proceed to **Feature B (Stress Analysis)**!
