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

### (d) Free Body Diagram (FBD)

- *At Support (x = 0):* Vertical reaction force R_y = 600 lbf (pointing upward) and reaction bending moment M_max = F * L_A = 1,200 lb*in (counter-clockwise).
- *At Free End (x = 2.00 in):* Downward force F = 600 lbf applied by the strap.

### (e) Algebraic Model

Maximum bending moment occurs at the fixed support (x = 0):
M_max = F * L_A

Bending stress formula:
sigma = M_max / Z <= sigma_allow

For a solid circular cross-section:
Z = (pi * r^3) / 4 = (pi * d^3) / 32

Solving algebraically for required Section Modulus (Z_req) and minimum radius (r_stress):
Z_req = M_max / sigma_allow = (F * L_A) / sigma_allow
r_stress = ((4 * Z_req) / pi)^(1/3) = ((4 * F * L_A) / (pi * sigma_allow))^(1/3)
d_stress = 2 * r_stress

### (f) Numerical Solution

1. *Calculate Maximum Bending Moment:*
   M_max = (600 lbf) * (2.00 in) = 1,200 lb*in

2. *Calculate Required Section Modulus (Z_req):*
   Z_req = (1,200 lb*in) / (9,064.86 psi) ~ 0.13238 in^3

3. *Calculate Minimum Radius (r_stress):*
   r_stress = ((4 * 0.13238) / pi)^(1/3) = (0.16855)^(1/3) ~ 0.5524 in

4. *Calculate Minimum Diameter (d_stress):*
   d_stress = 2 * 0.5524 in = 1.105 in

## Reaction Force Transfer to Feature B

The reaction forces at the base of Feature A become the applied loads for Feature B:
- *Transverse Force (P_B):* R_y = 600 lbf
- *Moment (M_B):* 1,200 lb*in
