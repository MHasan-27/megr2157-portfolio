# A6: Bracket Drawing (Drawings Part 1)

## Download CAD & Drawing Files
- **Bracket Solid Model:** [A6 Bracket Drawing.SLDPRT](https://github.com/MHasan-27/megr2157-portfolio/raw/main/docs/assignments/A06/A6%20Bracket%20Drawing.SLDPRT)
- **Bracket Engineering Drawing:** [A6 Bracket Drawing.SLDDRW](https://github.com/MHasan-27/megr2157-portfolio/raw/main/docs/assignments/A06/A6%20Bracket%20Drawing.SLDDRW)
- **Link Solid Model (2157 Only):** [Link.SLDPRT](https://github.com/MHasan-27/megr2157-portfolio/raw/main/docs/assignments/A06/Link.SLDPRT)
- **Link Engineering Drawing (2157 Only):** [Link.SLDDRW](https://github.com/MHasan-27/megr2157-portfolio/raw/main/docs/assignments/A06/Link.SLDDRW)

---

## 1. Parametric Design

### Global Variables & Equations Table
To make the CAD model fully dynamic, feature dimensions were tied to global variables driven by analytical stress and stiffness equations calculated in Assignment 5.

![SolidWorks Equations and Global Variables](Equation%20List%20and%20Global%20Variable.png)

| Name | Value / Equation | Evaluates to | Comments |
| :--- | :--- | :--- | :--- |
| `"F"` | `= 600` | `600.00` | Applied Load [lbf] |
| `"P"` | `= "F" / 2` | `300.00` | Symmetric Leg Force [lbf] |
| `"Ys"` | `= 36259.43` | `36259.43` | Material Yield Strength (ASTM A36) [psi] |
| `"E"` | `= 29007547.53` | `29007547.53` | Elastic Modulus (ASTM A36) [psi] |
| `"Ns"` | `= 4.0` | `4.00` | Factor of Safety |
| `"sigma_allow"`| `= "Ys" / "Ns"` | `9064.86` | Allowable Stress [psi] |
| `"delta_max"` | `= 0.005` | `0.005` | Maximum Deflection Limit [in] |
| `"L_A"` | `= 2.00` | `2.00` | Feature A Pin Length [in] |
| `"d_stress_A"` | `= ((32 * "P" * "L_A") / (pi * "sigma_allow"))^(1/3)` | `0.8768` | Min Bending Stress Diameter [in] |
| `"d_stiff_A"` | `= ((64 * "P" * ("L_A"^3)) / (3 * pi * "E" * "delta_max"))^(1/4)` | `0.5788` | Min Stiffness Diameter [in] |
| `"d_A"` | `= 1.000` | `1.000` | Selected Nominal Diameter [in] |
| `"w_B"` | `= "d_A"` | `1.000` | Feature B Width (Tied to Pin Dia) [in] |
| `"t_B"` | `= 0.250` | `0.250` | Feature B Selected Thickness [in] |
| `"h_C"` | `= 0.375` | `0.375` | Feature C Selected Height [in] |
| `"t_D"` | `= 0.500` | `0.500` | Feature D Selected Thickness [in] |
| `"h_E"` | `= 0.500` | `0.500` | Feature E Selected Thickness [in] |

---

### Step-by-Step Modeling Process

#### Step 1: Feature A – Transverse Support Pin
Created the base cylinder driven by parameter `"d_A"`.

![Step 1 - Modeling Feature A](Step%201.png)

#### Step 2: Feature B – Vertical Connecting Link
Extruded the vertical connecting link, parameterizing the width directly to `"w_B"` (equal to `"d_A"`).

![Step 2 - Modeling Feature B](Step%202.png)

#### Step 3: Feature C – Simply Supported Cross-Beam
Added the central horizontal cross-beam, setting its depth/height equal to `"h_C"`.

![Step 3 - Modeling Feature C](Step%203.png)

#### Step 4: Feature D – Vertical Cantilever Web
Extruded the vertical web support using parameter `"t_D"`.

![Step 4 - Modeling Feature D](Step%204.png)

#### Step 5: Feature E – Mounting Base Flange
Constructed the base attachment flange using parameter `"h_E"`.

![Step 5 - Modeling Feature E](Step%205.png)

#### Step 6: Complete Bracket & Parametric Validation
Final bracket geometry rebuilds dynamically whenever global load or allowable stress variables are adjusted.

![Step 6 - Bracket Completion](Step%206.png)
![Step 6.1 - Final Solid Model View](Step%206.1.png)

---

## 2. Multi-View Engineering Drawing & Tolerancing

### Projection & Layout
The drawing was created on an ANSI standard sheet in **Third Angle Projection** conforming to ASME Y14.3 standards.

![Bracket Multiview Drawing Page 1](Drwaing%201.png)
![Bracket Multiview Drawing Page 2](A6%20Bracket%20Drawing%202.JPG)

### Tolerance Block & Fits
A standard title block tolerance note was applied across the drawing:
- `X.X ± .02`
- `X.XX ± .01`
- `X.XXX ± .005`

The T-slot sliding interface over the rigid beam was dimensioned using the tighter `X.XXX ± .005` tolerance to guarantee smooth linear motion without excessive play or binding under dynamic load conditions.

---

## 3. Reflections & Analytical Justification

### Analytical Driving Equation
Feature A (Pin Diameter $d_A$) was directly driven by the maximum bending stress equation for a circular cantilever pin:

$$\sigma = \frac{M c}{I} = \frac{32 P L_A}{\pi d_A^3} \implies d_A = \sqrt[3]{\frac{32 \cdot P \cdot L_A}{\pi \cdot \sigma_{allow}}}$$

In SolidWorks Equation Manager, this was bound as:
`"d_stress_A" = ((32 * "P" * "L_A") / (pi * "sigma_allow"))^(1/3)`

When allowable stress $\sigma_{allow}$ or load $P$ changes, SolidWorks re-evaluates `"d_stress_A"`. Dependent geometric features—such as Feature B width `"w_B"`—automatically scale and rebuild without manual intervention.

### Tolerancing & Manufacturing Justification
- **Tighter Class (`X.XXX ± .005`):** Applied to the T-slot sliding channel. Because this surface forms a precision sliding fit over the rigid beam, tight control over dimensions prevents joint backlash, jamming, and uneven wear.
- **Looser Class (`X.X ± .02`):** Applied to outer structural fillets and non-mating plate lengths. These surfaces do not engage with mating parts.
- **Cost & Feasibility Impact:** Defaulting to tight tolerances across non-critical dimensions forces machinists to use slower feed rates, finer tooling passes, and rigorous CMM inspection routines, significantly increasing manufacturing costs and scrap rates without providing functional benefit.

### Time Log
- **Parametric CAD Modeling:** 2.5 hours
- **Engineering Drawing & GD&T Setup:** 2.0 hours
- **2157 Link Design & Drawing:** 1.5 hours
- **Documentation & Portfolio Formatting:** 1.0 hour
- **Total Time Spent:** 7.0 hours

---

## 4. 2157 Students Only (20%) – Connecting Link Design

### Parametric Link Equations
A connecting link was modeled to attach to the bracket's Feature A pin interface. The hole diameter is parametrically bound to the pin diameter `$d_A$` with clearance.

![Link Equations and Global Variables](Link%20Global%20Variable%20and%20Equation.png)

| Name | Value / Equation | Evaluates to | Comments |
| :--- | :--- | :--- | :--- |
| `"P"` | `= 300` | `300.00` | Tensile Load [lbf] |
| `"sigma_allow"`| `= 9064.86` | `9064.86` | Allowable Stress [psi] |
| `"E"` | `= 29007547.53` | `29007547.53` | Elastic Modulus [psi] |
| `"w_link"` | `= 1.50` | `1.50` | Link Overall Width [in] |
| `"L_link"` | `= 3.00` | `3.00` | Total Link Length [in] |
| `"d_hole"` | `= 1.00` | `1.00` | Nominal Pin Hole Diameter [in] |
| `"center_dist"`| `= 2.00` | `2.00` | Center-to-Center Distance [in] |
| `"A_net_req"` | `= "P" / "sigma_allow"` | `0.03309` | Required Net Area [in^2] |
| `"w_net"` | `= "w_link" - "d_hole"` | `0.50` | Net Width Across Hole [in] |
| `"t_stress"` | `= "A_net_req" / "w_net"` | `0.06618` | Minimum Stress Thickness [in] |
| `"t_nominal"` | `= 0.250` | `0.250` | Selected Plate Thickness [in] |
| `"delta_act"` | `= ("P" * "L_link") / ("A_net_act" * "E")` | `0.000248` | Actual Extension [in] ($\le 0.005\text{ in}$) |

### Link CAD Model & Isometric View

![Link Solid Model View 1](Link%201.png)
![Link Solid Model Isometric View](Link%20IsoMetric%20View.png)

### Link Engineering Drawing
The multi-view drawing was produced using Third Angle Projection with ASME Y14.5 dimensioning standards. An **H8** hole fit tolerance was assigned to the pin hole interface to guarantee a smooth RC close running fit over the bracket pin.

![Link Engineering Drawing](Link.JPG)

### 2157 Reflection
Part-to-part compatibility requires strict coordination between mating tolerances. Assigning an **H8** internal fit tolerance on the link hole paired with a **g6** shaft fit on the bracket pin ensures that thermal expansion or manufacturing variances do not cause binding, while avoiding excessive clearance that could induce shock loading.
