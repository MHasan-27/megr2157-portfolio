# A5 – [Bracket Design]

## 1. Assignment Objectives (in Simple Words)

- *Design for Strength & Safety:* Determine the minimum thickness/diameter for each structural feature on the bracket so that the material does not yield or break under a 600 lbf load with a Factor of Safety of 4.
- *Design for Stiffness & Deflection:* Calculate the minimum required dimensions so that elastic deflection/stretching stays within 0.005 in per feature.
- *Load Path Tracing:* Transfer calculated reaction forces sequentially from Feature A through Feature E to ensure static equilibrium across the entire mounting bracket assembly.
- *Manufacturing Precision (Fits):* Select appropriate ANSI B4.1 standard fits and tolerances for interface dimensions to ensure proper mechanical assembly with mating components.
- *Technical Documentation:* Present complete Free Body Diagrams (FBDs), step-by-step algebraic/numerical solutions, and multiview engineering drawings in your virtual portfolio site.

## 2. Material & Global Parameters Baseline

- *Material:* Steel (ASTM A36)
- *Applied Force (F):* 600 lbf (Symmetric total force 2 * F_leg = 600 lbf => F_leg = 300 lbf)
- *Yield Strength (Y_s):* 36,259.43 psi
- *Elastic Modulus (E):* 29,007,547.53 psi
- *Factor of Safety (N_s):* 4.0
- *Allowable Stress (sigma_allow):*
  sigma_allow = Y_s / N_s = 36,259.43 / 4.0 = 9,064.86 psi (~ 9.06 ksi)

## 3. Calculating Dimensions from Stress Analysis: Feature A

Following the sequential load path (Appendix A & Appendix D guidelines), *Feature A* is the cylindrical support pin holding the polyester strap.

### (a) Knowns

- Applied Load (F): 600 lbf transverse point load at free end
- P = F/2 = 300 lbf
- Pin Length (L_A): 2.00 in (assumed based on strap width)
- Yield Strength (Y_s): 36,259.43 psi
- Factor of Safety (N_s): 4.0
- Allowable Bending Stress (sigma_allow): 9,064.86 psi

### (b) Unknowns

- Required minimum pin radius (r_stress) and diameter (d_stress) based on bending stress.
- Support reaction force (R_y) and reaction moment (M_max) at the connection interface.

### (c) Assumptions

1. *Beam Model:* Feature A behaves as a solid circular cantilever beam rigidly fixed at x = 0.
2. *Loading:* Transverse point load F = 600 lbf applied at x = L_A = 2.00 in.
3. *Shear Stress:* Direct shear failure is non-governing per prompt instructions.
4. *Material:* Homogeneous, linear-elastic A36 steel.

### (d) Free Body Diagram and Calculation (FBD)

***(Adding Picture of Calculation)


### Feature A: Conclusion

Comparing the required minimum dimensions derived from both analyses:

* **Stress Analysis Dimension:** d_stress= 0.8768  in
* **Stiffness Analysis Dimension:** d_stiff = 0.5788 in

Since d_stress > d_stiff, **Stress Analysis governs** the dimensioning for Feature A.

To ensure safety, ease of manufacturing, and alignment with standard stock sizes, the nominal dimension for Feature A is rounded up to **d_A = 1.000  in**.

Here is the complete **Feature B Analysis** (Vertical Connecting Link / Tension Bar) formatted using simple, clean plain text for all spatial characters, variables, and mathematical expressions:

---

### Baseline Transferred Parameters from Feature A

* **Transferred Reaction Force (P_B):** 300 lbf (symmetrical half-load per side, `P_B = F / 2 = 300 lbf`)
* **Feature Length (L_B):** 2.00 in
* **Feature Width (w_B):** 1.00 in (set equal to Feature A nominal diameter `d_A = 1.00 in`)
* **Yield Strength (sigma_y):** 36,259.43 psi (ASTM A36 Steel)
* **Elastic Modulus (E):** 29,007,547.53 psi
* **Factor of Safety (N_s):** 4.0
* **Allowable Stress (sigma_allow):**
`sigma_allow = sigma_y / N_s = 36259.43 / 4.0 = 9064.86 psi`
* **Maximum Deflection (delta_max):** 0.005 in

---

## 1. Feature B: Stress Analysis (Axial Tension)

#### (a) Known Values

* Transferred Tensile Load (P_B): 300 lbf
* Feature Length (L_B): 2.00 in
* Feature Width (w_B): 1.00 in
* Allowable Tensile Stress (sigma_allow): 9,064.86 psi

#### (b) Unknowns

* Required minimum cross-sectional area (A_stressB)
* Required minimum thickness (t_stressB)

#### (c) Assumptions

1. Feature B behaves as a two-force member in pure uniaxial vertical tension.
2. Bending moments, buckling, and direct shear failure are neglected per instructions.
3. Tensile stress is uniformly distributed across the rectangular cross-section (`A_B = w_B * t_B`).

#### (d) Free Body Diagram And Calculation (FBD)



## 3. Feature B: Conclusion

Comparing the required minimum dimensions derived from both analyses:

* **Stress Analysis Dimension:** `t_stressB = 0.0331 in`
* **Stiffness Analysis Dimension:** `t_stiffB = 0.00414 in`

Since `t_stressB > t_stiffB`, **Stress Analysis governs** the dimensioning for Feature B.

To ensure structural robustness, ease of manufacturing, and standard stock material sizing, the nominal thickness for Feature B is selected as **`t_B = 0.250 in`** (1/4 inch plate).

---

### Verification & Double Check

Re-evaluating stress and deflection using nominal thickness `t_B = 0.250 in`:

1. **Tensile Stress Check (sigma_B):**
`sigma_B = 300 / (1.00 * 0.250) = 1,200 psi`
`sigma_B = 1,200 psi <= sigma_allow = 9,064.86 psi` (Passes)
2. **Axial Deflection Check (delta_B):**
`delta_B = (300 * 2.00) / (1.00 * 0.250 * 29007547.53) = 600 / 7251886.88 = 0.0000827 in`
`delta_B = 0.0000827 in <= delta_max = 0.005000 in` (Passes)

**Final Decision:** Use **`t_B = 0.250 in`** (and width `w_B = 1.000 in`) for Feature B.

Here is the complete **Feature C Analysis** (Cross Beam / Simply Supported Beam) following the sequential load path, formatted using simple plain text for all spatial variables:

---

---

## 1. Feature C: Stress Analysis (Center Point Load Bending)

#### (a) Known Values

* Transferred Center Load (P_C): 300 lbf
* Beam Span Length (L_C): 2.50 in
* Cross-Section Width (w_C): 1.00 in
* Allowable Stress (sigma_allow): 9,064.86 psi

#### (b) Unknowns

* End support reaction forces (R_1C, R_2C)
* Maximum mid-span bending moment (M_maxC)
* Required Section Modulus (Z_reqC)
* Required minimum height/thickness (h_stressC)

#### (c) Assumptions

1. Feature C behaves as a simply supported rectangular beam with supports at `x = 0` and `x = L_C`.
2. Transferred load `P_C = 300 lbf` acts as a concentrated center point load at `x = L_C / 2 = 1.25 in`.
3. Direct shear stress failure is non-governing per project instructions.

#### (d) Free Body Diagram And Calculation (FBD)



## 2. Feature C: Stiffness Analysis (Center Point Deflection)

#### (b) Unknowns

* Required Area Moment of Inertia (I_reqC)
* Required minimum height/thickness (h_stiffC)

#### (c) Assumptions

1. Feature C experiences mid-span vertical elastic deflection under point load `P_C = 300 lbf`.
2. Mid-span deflection follows standard simply supported beam elastic curve theory (`delta = (P * L^3) / (48 * E * I)`).
3. Shear deformations are assumed negligible.

#### (d) Free Body Diagram (FBD)



## 3. Feature C: Conclusion

Comparing the required minimum dimensions derived from both analyses:

* **Stress Analysis Dimension:** `h_stressC = 0.3523 in`
* **Stiffness Analysis Dimension:** `h_stiffC = 0.2007 in`

Since `h_stressC > h_stiffC`, **Stress Analysis governs** the dimensioning for Feature C.

To align with standard nominal plate stock sizes, the nominal thickness/height for Feature C is selected as **`h_C = 0.375 in`** (3/8 inch plate).

---

### Verification & Double Check

Re-evaluating bending stress and deflection using nominal height `h_C = 0.375 in`:

1. **Bending Stress Check (sigma_C):**
`Z_C = (1.00 * (0.375)^2) / 6 = 0.02344 in^3`
`sigma_C = 187.5 / 0.02344 = 7,999.15 psi`
`sigma_C = 7,999.15 psi <= sigma_allow = 9,064.86 psi` (Passes)
2. **Deflection Check (delta_C):**
`I_C = (1.00 * (0.375)^3) / 12 = 0.004395 in^4`
`delta_C = (300 * (2.50)^3) / (48 * 29007547.53 * 0.004395) = 4687.5 / 6119339.46 = 0.000766 in`
`delta_C = 0.000766 in <= delta_max = 0.005000 in` (Passes)

**Final Decision:** Use **`h_C = 0.375 in`** (and width `w_C = 1.000 in`) for Feature C.

Here is the complete **Feature D Analysis** (Vertical Wall Support / Cantilever Web) following the sequential load path, formatted using simple plain text for all spatial variables:

---

### Baseline Transferred Parameters from Feature C

* **Transferred Reaction Force (P_D):** 150 lbf (symmetrical support reaction from Feature C, `P_D = R_1C = 150 lbf`)
* 
## 1. Feature D: Stress Analysis (Cantilever Bending)

#### (a) Known Values

* Transferred Transverse Load (P_D): 150 lbf
* Feature Length (L_D): 2.00 in
* Feature Width/Depth (w_D): 1.00 in
* Allowable Stress (sigma_allow): 9,064.86 psi

#### (b) Unknowns

* Support reaction force (R_yD) and reaction bending moment (M_maxD)
* Required Section Modulus (Z_reqD)
* Required minimum thickness (t_stressD)

#### (c) Assumptions

1. Feature D acts as a vertical rectangular cantilever beam fixed at `x = 0` (wall junction).
2. Point load `P_D = 150 lbf` is applied at free end `x = L_D = 2.00 in`.
3. Direct shear stress failure is non-governing per prompt instructions.

#### (d) Free Body Diagram And Calculation (FBD)



## 3. Feature D: Conclusion

Comparing the required minimum dimensions derived from both analyses:

* **Stress Analysis Dimension:** `t_stressD = 0.4456 in`
* **Stiffness Analysis Dimension:** `t_stiffD = 0.3211 in`

Since `t_stressD > t_stiffD`, **Stress Analysis governs** the dimensioning for Feature D.

To ensure safety and match standard nominal plate stock, the nominal thickness for Feature D is selected as **`t_D = 0.500 in`** (1/2 inch plate).

---

### Verification & Double Check

Re-evaluating bending stress and deflection using nominal thickness `t_D = 0.500 in`:

1. **Bending Stress Check (sigma_D):**
`Z_D = (1.00 * (0.500)^2) / 6 = 0.04167 in^3`
`sigma_D = 300 / 0.04167 = 7,199.6 psi`
`sigma_D = 7,199.6 psi <= sigma_allow = 9,064.86 psi` (Passes)
2. **Deflection Check (delta_D):**
`I_D = (1.00 * (0.500)^3) / 12 = 0.010417 in^4`
`delta_D = (150 * (2.00)^3) / (3 * 29007547.53 * 0.010417) = 1200 / 906485.86 = 0.001324 in`
`delta_D = 0.001324 in <= delta_max = 0.005000 in` (Passes)

**Final Decision:** Use **`t_D = 0.500 in`** (and width `w_D = 1.000 in`) for Feature D.

Here is the complete **Feature E Analysis** (Mounting Flange / Wall Attachment Base) following the sequential load path, formatted using simple plain text for all spatial variables:

---

## 1. Feature E: Stress Analysis (Cantilever Bending)

#### (a) Known Values

* Transferred Load (P_E): 150 lbf
* Overhang Span Length (L_E): 2.00 in
* Cross-Section Width (w_E): 1.00 in
* Allowable Stress (sigma_allow): 9,064.86 psi

#### (b) Unknowns

* Reaction bending moment at wall connection (M_maxE)
* Required Section Modulus (Z_reqE)
* Required minimum thickness/height (h_stressE)

#### (c) Assumptions

1. Feature E behaves as a short rectangular cantilever base fixed at the wall anchor interface (`x = 0`).
2. Transferred force `P_E = 150 lbf` acts at the cantilever tip (`x = L_E = 2.00 in`).
3. Direct shear stresses and fastener tear-out are neglected per baseline problem constraints.

#### (d) Free Body Diagram And Calculation (FBD)



## 3. Feature E: Conclusion

Comparing the required minimum dimensions derived from both analyses:

* **Stress Analysis Dimension:** `h_stressE = 0.4456 in`
* **Stiffness Analysis Dimension:** `h_stiffE = 0.3211 in`

Since `h_stressE > h_stiffE`, **Stress Analysis governs** the dimensioning for Feature E.

To ensure safety and match standard nominal plate stock, the nominal thickness/height for Feature E is selected as **`h_E = 0.500 in`** (1/2 inch plate).

---

### Verification & Double Check

Re-evaluating bending stress and deflection using nominal dimension `h_E = 0.500 in`:

1. **Bending Stress Check (sigma_E):**
`Z_E = (1.00 * (0.500)^2) / 6 = 0.04167 in^3`
`sigma_E = 300 / 0.04167 = 7,199.6 psi`
`sigma_E = 7,199.6 psi <= sigma_allow = 9,064.86 psi` (Passes)
2. **Deflection Check (delta_E):**
`I_E = (1.00 * (0.500)^3) / 12 = 0.010417 in^4`
`delta_E = (150 * (2.00)^3) / (3 * 29007547.53 * 0.010417) = 1200 / 906485.86 = 0.001324 in`
`delta_E = 0.001324 in <= delta_max = 0.005000 in` (Passes)

**Final Decision:** Use **`h_E = 0.500 in`** (and width `w_E = 1.000 in`) for Feature E.
