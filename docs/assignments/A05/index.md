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



