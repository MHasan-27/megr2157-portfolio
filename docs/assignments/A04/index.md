# A4: Motor Mount Assignment

## Objective
The objective of this assignment is to design a 3D-printable motor mount that safely attaches a planetary gear motor to a solid wall while keeping bending stresses low and preventing excessive deflection under load.

---

## Core Goals & Requirements

* **Structural Support:**Mount a Brushed 24V DC Gear Motor to rigid Wall A, carrying an applied end force of P = 300N on the motor shaft.
* **Dual Design Criteria:** 
  1. **Yield Strength:** Ensure the structure holds the load with a Safety Factor of 3 [sigma_{allow} = sigma_y / 3].
  2. **Deflection Limit:** Keep total deflection at the free end under 0.30 mm.
* **Two Main Features:**
  * **Feature 1:** The section attached directly to the motor (analyzed as a cantilever beam).
  * **Feature 2:** The section connecting Feature 1 to Wall A (analyzed as a cantilever beam).
* **Material Selection:** Select ABS, PETG, or PLA for 3D printing. I select PLA for my parts. 
* **Deliverables:**
  * Hand-drawn FBDs and isometric sketches.
  * Mathematical beam calculations for stress and deflection.
  * Fully parametric 3D CAD model with fastener and shaft clearance holes.
  * Portfolio documentation including headers, CAD download link, and lessons learned.

## Analyze
## Feature 1: Motor Attachment

### All Knowns and Unknowns

* **Knowns:**
  * Shaft Load: $P = 300\text{ N}$
  * Maximum allowable deflection at free end: $\delta_{max} = 0.30\text{ mm} = 0.0003\text{ m}$
  * Safety Factor: $SF = 3$
  * Feature length: $L_1 = 50\text{ mm} = 0.050\text{ m}$
  * Selected Material: **PLA**
    * Yield Strength: $\sigma_y = 60\text{ MPa} = 60 \times 10^6\text{ Pa}$
    * Young's Modulus: $E = 3.5\text{ GPa} = 3.5 \times 10^9\text{ Pa}$
* **Unknowns:**
  * Allowable Bending Stress ($\sigma_{allow}$)
  * Rectangular cross-section dimensions: Width ($b_1$) and Height ($h_1$)

---

### Feature 1 FBD

* Model Feature 1 as a horizontal cantilever beam of length $L_1 = 50\text{ mm}$ fixed at $x = 0$ (at the interface with Feature 2) and free at $x = L_1$.
* At the free end ($x = L_1$), apply the downward transverse motor load $P = 300\text{ N}$.
* At the fixed end ($x = 0$), show the vertical reaction force $R_{y1} = P = 300\text{ N}$ and reaction moment $M_1 = P \cdot L_1 = 300 \cdot 0.050 = 15\text{ N}\cdot\text{m}$.

---

### Symbolically Solving for Equations to find $b_1$ and $h_1$

* **Allowable Bending Stress:**
  $$\sigma_{allow} = \frac{\sigma_y}{SF} = \frac{\sigma_y}{3}$$

* **Yield Strength Criterion:**
  For a rectangular cross-section with Moment of Inertia $I_1 = \frac{b_1 h_1^3}{12}$ and distance to outer fiber $c = \frac{h_1}{2}$:
  $$\sigma_{max} = \frac{M_1 c}{I_1} = \frac{(P L_1) \left(\frac{h_1}{2}\right)}{\frac{b_1 h_1^3}{12}} = \frac{6 P L_1}{b_1 h_1^2}$$
  Setting $\sigma_{max} \le \sigma_{allow}$:
  $$b_1 h_1^2 \ge \frac{6 P L_1}{\sigma_{allow}}$$

* **Deflection Criterion:**
  Maximum deflection at the free end of a cantilever beam under load $P$:
  $$\delta_{max} = \frac{P L_1^3}{3 E I_1} = \frac{P L_1^3}{3 E \left(\frac{b_1 h_1^3}{12}\right)} = \frac{4 P L_1^3}{E b_1 h_1^3}$$
  Solving symbolically for $b_1 h_1^3$:
  $$b_1 h_1^3 \ge \frac{4 P L_1^3}{E \delta_{max}}$$

---

### Numerically Solving for Equations to find $b_1$ and $h_1$

Assuming a square cross-section where $b_1 = h_1$:

* **Allowable Stress:**
  $$\sigma_{allow} = \frac{60 \times 10^6\text{ Pa}}{3} = 20 \times 10^6\text{ Pa} \quad (20\text{ MPa})$$

* **Solving for $h_1$ based on Yield Strength:**
  $$h_1^3 \ge \frac{6 (300\text{ N}) (0.050\text{ m})}{20 \times 10^6\text{ Pa}} = 4.500 \times 10^{-6}\text{ m}^3$$
  $$h_1 \ge \sqrt[3]{4.500 \times 10^{-6}} = 0.01651\text{ m} = 16.51\text{ mm}$$

* **Solving for $h_1$ based on Deflection Criterion:**
  $$h_1^4 \ge \frac{4 (300\text{ N}) (0.050\text{ m})^3}{(3.5 \times 10^9\text{ Pa}) (0.0003\text{ m})} = 1.4286 \times 10^{-7}\text{ m}^4$$
  $$h_1 \ge \sqrt[4]{1.4286 \times 10^{-7}} = 0.01943\text{ m} = 19.43\text{ mm}$$

* **Governing Dimension for Feature 1:**
  Deflection governs because $19.43\text{ mm} > 16.51\text{ mm}$. Selecting $b_1 = h_1 = 20.0\text{ mm}$.

---

## Feature 2: Wall Attachment

### All Knowns and Unknowns

* **Knowns:**
  * Transferred shaft load: $P = 300\text{ N}$
  * Maximum allowable deflection: $\delta_{max} = 0.30\text{ mm} = 0.0003\text{ m}$
  * Safety Factor: $SF = 3$
  * Feature length: $L_2 = 60\text{ mm} = 0.060\text{ m}$
  * Material: **PLA** ($\sigma_y = 60\text{ MPa}$, $E = 3.5\text{ GPa}$)
* **Unknowns:**
  * Allowable Stress ($\sigma_{allow}$)
  * Cross-section dimensions: Width ($b_2$) and Height ($h_2$)

---

### Feature 2 FBD

* Model Feature 2 as a cantilever beam extending from rigid Wall A at $x = 0$ to Feature 1 at $x = L_2$.
* At $x = L_2$, apply downward load $P = 300\text{ N}$ transferred from Feature 1.
* At Wall A ($x = 0$), show vertical reaction force $R_{y2} = 300\text{ N}$ and reaction moment $M_2 = P \cdot L_2 = 300 \cdot 0.060 = 18\text{ N}\cdot\text{m}$.

---

### Symbolically Solving for $b_2$ and $h_2$ With Respect to Yield Strength

* Bending moment equation at fixed wall connection:
  $$\sigma_{max} = \frac{6 P L_2}{b_2 h_2^2} \le \sigma_{allow}$$
* Solving symbolically for $b_2 h_2^2$:
  $$b_2 h_2^2 \ge \frac{6 P L_2}{\sigma_{allow}}$$

---

### Symbolically Solving for $b_2$ and $h_2$ With Respect to Deflection

* Beam bending deflection equation at free end:
  $$\delta_{max} = \frac{4 P L_2^3}{E b_2 h_2^3} \le 0.30\text{ mm}$$
* Solving symbolically for $b_2 h_2^3$:
  $$b_2 h_2^3 \ge \frac{4 P L_2^3}{E \delta_{max}}$$

---

### Numerically Solving for $b_2$ and $h_2$ With Respect to Yield Strength

Assuming a square cross-section ($b_2 = h_2$) with length $L_2 = 60\text{ mm} = 0.060\text{ m}$:

$$h_2^3 \ge \frac{6 (300\text{ N}) (0.060\text{ m})}{20 \times 10^6\text{ Pa}} = 5.400 \times 10^{-6}\text{ m}^3$$
$$h_2 \ge \sqrt[3]{5.400 \times 10^{-6}} = 0.01754\text{ m} = 17.54\text{ mm}$$

---

### Numerically Solving for $b_2$ and $h_2$ With Respect to Deflection

$$h_2^4 \ge \frac{4 (300\text{ N}) (0.060\text{ m})^3}{(3.5 \times 10^9\text{ Pa}) (0.0003\text{ m})} = 2.4686 \times 10^{-7}\text{ m}^4$$
$$h_2 \ge \sqrt[4]{2.4686 \times 10^{-7}} = 0.02230\text{ m} = 22.30\text{ mm}$$

* **Governing Dimension for Feature 2:**
  Deflection governs over stress ($22.30\text{ mm} > 17.54\text{ mm}$). Selecting $b_2 = h_2 = 23.0\text{ mm}$.

## Decide


## Communicate

