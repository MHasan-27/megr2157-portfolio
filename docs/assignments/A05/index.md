# A5 – [Bracket Design]

# 1. Assignment Objectives:

* **Design for Strength & Safety:** Determine the minimum thickness/diameter for each structural feature on the bracket so that the material does not yield or break under a 600 lbf load with a Factor of Safety of 4.

* **Design for Stiffness & Deflection:** Calculate the minimum required dimensions so that elastic deflection/stretching stays within 0.005 in per feature.

* **Load Path Tracing:** Transfer calculated reaction forces sequentially from Feature A through Feature E to ensure static equilibrium across the entire mounting bracket assembly.

* **Manufacturing Precision (Fits):** Select appropriate ANSI B4.1 standard fits and tolerances for interface dimensions to ensure proper mechanical assembly with mating components.

* **Technical Documentation:** Present complete Free Body Diagrams (FBDs), step-by-step algebraic/numerical solutions, and multiview engineering drawings in the virtual portfolio site.

---

# 2. Material & Global Parameters Baseline

| Parameter                     |             Value |
| ----------------------------- | ----------------: |
| Material                      |  Steel (ASTM A36) |
| Applied Force, F              |           600 lbf |
| Force per leg, F_leg          |           300 lbf |
| Yield Strength, Y_s           |     36,259.43 psi |
| Elastic Modulus, E            | 29,007,547.53 psi |
| Factor of Safety, N_s         |               4.0 |
| Allowable Stress, sigma_allow |      9,064.86 psi |

# The total applied force is symmetric:


2 * F_leg = 600 lbf

F_leg = 600 / 2
F_leg = 300 lbf


# Allowable Stress

sigma_allow = Y_s / N_s

sigma_allow = 36,259.43 / 4.0

sigma_allow = 9,064.86 psi

sigma_allow ≈ 9.06 ksi


# 3. Calculating Dimensions from Stress Analysis: Feature A

Following the sequential load path (Appendix A and Appendix D guidelines), **Feature A** is the cylindrical support pin holding the polyester strap.

## (a) Knowns

* Applied load, F = 600 lbf transverse point load at the free end
* Pin length, L_A = 2.00 in (assumed based on strap width)
* Yield strength, Y_s = 36,259.43 psi
* Factor of Safety, N_s = 4.0
* Allowable bending stress, sigma_allow = 9,064.86 psi

## (b) Unknowns

* Required minimum pin radius, r_stress
* Required minimum pin diameter, d_stress
* Support reaction force, R_y
* Reaction moment, M_max

## (c) Assumptions

1. **Beam Model:** Feature A behaves as a solid circular cantilever beam rigidly fixed at x = 0.
2. **Loading:** Transverse point load F = 600 lbf is applied at x = L_A = 2.00 in.
3. **Shear Stress:** Direct shear failure is non-governing per prompt instructions.
4. **Material:** Homogeneous, linear-elastic A36 steel.

---

## (d) Free Body Diagram (FBD)

At the support, x = 0:

R_y = 600 lbf
M_max = F * L_A

Therefore:

M_max = (600 lbf) * (2.00 in)
M_max = 1,200 lb-in

The support reaction force acts upward, while the reaction moment acts counter-clockwise.

At the free end, x = 2.00 in:

F = 600 lbf downward


## (e) Algebraic Model

The maximum bending moment occurs at the fixed support:

M_max = F * L_A

Bending stress is:
sigma = M_max / Z

The design requirement is:

sigma <= sigma_allow

For a solid circular cross-section, the section modulus is:

Z = pi * r^3 / 4

or

Z = pi * d^3 / 32

### Required Section Modulus

Z_req = M_max / sigma_allow

Z_req = (F * L_A) / sigma_allow

### Required Radius

r_stress = (4 * Z_req / pi)^(1/3)

Substituting Z_req:

r_stress = (4 * F * L_A / (pi * sigma_allow))^(1/3)

### Required Diameter

d_stress = 2 * r_stress


# (f) Numerical Solution

## 1. Calculate Maximum Bending Moment

M_max = F * L_A

M_max = (600 lbf) * (2.00 in)

M_max = 1,200 lb-in

---

## 2. Calculate Required Section Modulus

Z_req = M_max / sigma_allow

Z_req = (1,200 lb-in) / (9,064.86 psi)

Z_req ≈ 0.13238 in^3

Therefore:

Z_req ≈ 0.13238 in^3


## 3. Calculate Minimum Radius

r_stress = (4 * Z_req / pi)^(1/3)

r_stress = (4 * 0.13238 / pi)^(1/3)

r_stress = (0.16855)^(1/3)

r_stress ≈ 0.5524 in

Therefore:

r_stress ≈ 0.5524 in
## 4. Calculate Minimum Diameter


d_stress = 2 * r_stress

d_stress = 2 * 0.5524 in

d_stress ≈ 1.105 in
Therefore:

d_stress ≈ 1.105 in

### Feature A Stress Design Result

| Quantity                 |       Result |
| ------------------------ | -----------: |
| Maximum bending moment   |  1,200 lb-in |
| Required section modulus | 0.13238 in^3 |
| Minimum radius           |    0.5524 in |
| Minimum diameter         |     1.105 in |
| Allowable stress         | 9,064.86 psi |


# Reaction Force Transfer to Feature B

The reaction forces at the base of Feature A become the applied loads for Feature B.

P_B = R_y
P_B = 600 lbf

The reaction moment transferred to Feature B is:

```text
M_B = M_max

M_B = 1,200 lb-in
```

Therefore, the loads transferred to Feature B are:

```text
Transverse Force:

P_B = 600 lbf


Moment:

M_B = 1,200 lb-in
```

These loads are used as the applied loads for the **Feature B stress analysis**.

