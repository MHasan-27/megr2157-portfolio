# A5 – [Bracket Design]

Here is the cleaned-up **GitHub-ready Markdown (`.md`)** version, with plain-text variable names and simple equations.

````md
# Assignment Objectives and Feature A Stress Analysis

## 1. Assignment Objectives (in Simple Words)

- **Design for Strength & Safety:** Determine the minimum thickness/diameter for each structural feature on the bracket so that the material does not yield or break under a 600 lbf load with a Factor of Safety of 4.

- **Design for Stiffness & Deflection:** Calculate the minimum required dimensions so that elastic deflection/stretching stays within 0.005 in per feature.

- **Load Path Tracing:** Transfer calculated reaction forces sequentially from Feature A through Feature E to ensure static equilibrium across the entire mounting bracket assembly.

- **Manufacturing Precision (Fits):** Select appropriate ANSI B4.1 standard fits and tolerances for interface dimensions to ensure proper mechanical assembly with mating components.

- **Technical Documentation:** Present complete Free Body Diagrams (FBDs), step-by-step algebraic/numerical solutions, and multiview engineering drawings in the virtual portfolio site.

---

# 2. Material & Global Parameters Baseline

| Parameter | Value |
|---|---:|
| Material | Steel (ASTM A36) |
| Applied Force, F | 600 lbf |
| Force per Leg, F_leg | 300 lbf |
| Yield Strength, Y_s | 36,259.43 psi |
| Elastic Modulus, E | 29,007,547.53 psi |
| Factor of Safety, N_s | 4.0 |

The total applied force is symmetric:

```text
2*F_leg = 600 lbf

F_leg = 300 lbf
````

### Allowable Stress

The allowable stress is calculated using:

```text
sigma_allow = Y_s / N_s
```

Substituting the given values:

```text
sigma_allow = 36,259.43 / 4.0
```

```text
sigma_allow = 9,064.86 psi
```

Therefore:

```text
sigma_allow = 9,064.86 psi
             = 9.06 ksi
```

---

# 3. Calculating Dimensions from Stress Analysis: Feature A

Following the sequential load path described in Appendix A and Appendix D, **Feature A** is the cylindrical support pin holding the polyester strap.

## 3.1 Knowns

* Applied load:

```text
F = 600 lbf
```

* Pin length:

```text
L_A = 2.00 in
```

* Yield strength:

```text
Y_s = 36,259.43 psi
```

* Factor of Safety:

```text
N_s = 4.0
```

* Allowable bending stress:

```text
sigma_allow = 9,064.86 psi
```

---

## 3.2 Unknowns

The following values must be determined:

* Required minimum pin radius based on stress:

```text
r_stress
```

* Required minimum pin diameter based on stress:

```text
d_stress
```

* Support reaction force:

```text
R_y
```

* Maximum reaction bending moment:

```text
M_max
```

---

## 3.3 Assumptions

1. **Beam Model:** Feature A behaves as a solid circular cantilever beam rigidly fixed at `x = 0`.

2. **Loading:** A transverse point load of `F = 600 lbf` is applied at the free end:

```text
x = L_A = 2.00 in
```

3. **Shear Stress:** Direct shear failure is considered non-governing according to the assignment instructions.

4. **Material:** The material is homogeneous, linear-elastic ASTM A36 steel.

---

# 4. Feature A Free Body Diagram (FBD)

At the fixed support (`x = 0`), the support provides:

* Vertical reaction force:

```text
R_y = 600 lbf
```

* Reaction bending moment:

```text
M_max = F * L_A
```

At the free end (`x = 2.00 in`), the strap applies a downward force:

```text
F = 600 lbf
```

The maximum bending moment occurs at the fixed support.

```text
M_max = F * L_A
```

Substituting:

```text
M_max = (600 lbf)(2.00 in)
```

```text
M_max = 1,200 lb-in
```

---

# 5. Feature A Algebraic Stress Model

## 5.1 Maximum Bending Moment

The maximum bending moment is:

```text
M_max = F * L_A
```

---

## 5.2 Bending Stress

The bending stress is calculated using:

```text
sigma = M_max / Z
```

The design requirement is:

```text
sigma <= sigma_allow
```

Therefore, the required section modulus is:

```text
Z_req = M_max / sigma_allow
```

or:

```text
Z_req = (F * L_A) / sigma_allow
```

---

## 5.3 Section Modulus for a Solid Circular Pin

For a solid circular cross-section:

```text
Z = (pi * r^3) / 4
```

Using diameter:

```text
Z = (pi * d^3) / 32
```

---

## 5.4 Required Radius

Set the available section modulus equal to the required section modulus:

```text
Z_req = (pi * r^3) / 4
```

Solving for radius:

```text
r_stress = (4 * Z_req / pi)^(1/3)
```

Substituting:

```text
r_stress = (4 * F * L_A / (pi * sigma_allow))^(1/3)
```

---

## 5.5 Required Diameter

The required diameter is:

```text
d_stress = 2 * r_stress
```

---

# 6. Feature A Numerical Solution

## Step 1: Calculate Maximum Bending Moment

```text
M_max = F * L_A
```

```text
M_max = (600 lbf)(2.00 in)
```

```text
M_max = 1,200 lb-in
```

Therefore:

```text
M_max = 1,200 lb-in
```

---

## Step 2: Calculate Required Section Modulus

```text
Z_req = M_max / sigma_allow
```

```text
Z_req = (1,200 lb-in) / (9,064.86 psi)
```

```text
Z_req = 0.13238 in^3
```

Therefore:

```text
Z_req = 0.13238 in^3
```

---

## Step 3: Calculate Minimum Radius

Using:

```text
r_stress = (4 * Z_req / pi)^(1/3)
```

Substitute the calculated section modulus:

```text
r_stress = (4 * 0.13238 / pi)^(1/3)
```

```text
r_stress = (0.16855)^(1/3)
```

```text
r_stress = 0.5524 in
```

Therefore:

```text
r_stress = 0.5524 in
```

---

## Step 4: Calculate Minimum Diameter

```text
d_stress = 2 * r_stress
```

```text
d_stress = 2 * 0.5524 in
```

```text
d_stress = 1.105 in
```

Therefore:

```text
d_stress = 1.105 in
```

---

# 7. Feature A Final Results

| Quantity                        |       Result |
| ------------------------------- | -----------: |
| Applied load, F                 |      600 lbf |
| Pin length, L_A                 |      2.00 in |
| Maximum bending moment, M_max   |  1,200 lb-in |
| Allowable stress, sigma_allow   | 9,064.86 psi |
| Required section modulus, Z_req | 0.13238 in^3 |
| Minimum radius, r_stress        |    0.5524 in |
| Minimum diameter, d_stress      |     1.105 in |
| Support reaction, R_y           |      600 lbf |

### Design Diameter

The theoretical minimum diameter based on bending stress is:

```text
d_stress = 1.105 in
```

For the final CAD design, a practical standard diameter should be selected that is equal to or greater than the calculated minimum diameter.

---

# 8. Reaction Force Transfer to Feature B

The reaction forces developed at the base of Feature A become the applied loads for Feature B.

Therefore:

### Transverse Force

```text
P_B = R_y
```

```text
P_B = 600 lbf
```

### Applied Moment

```text
M_B = M_max
```

```text
M_B = 1,200 lb-in
```

Therefore, the loads transferred from Feature A to Feature B are:

```text
P_B = 600 lbf
```

```text
M_B = 1,200 lb-in
```

These values will be used as the starting loads for the **Feature B stress analysis**.

---

# 9. Summary

Feature A was modeled as a solid circular cantilever pin subjected to a 600 lbf transverse load at a length of 2.00 in.

The maximum bending moment is:

```text
M_max = 1,200 lb-in
```

Using an ASTM A36 yield strength of 36,259.43 psi and a Factor of Safety of 4:

```text
sigma_allow = 9,064.86 psi
```

The required section modulus is:

```text
Z_req = 0.13238 in^3
```

The resulting minimum pin dimensions based on bending stress are:

```text
r_stress = 0.5524 in
```

```text
d_stress = 1.105 in
```

The reaction loads transferred to Feature B are:

```text
P_B = 600 lbf
```

```text
M_B = 1,200 lb-in
```

These reaction loads will be used for the next stage of the sequential load-path analysis.

```

**Note:** I also changed the math notation to GitHub-friendly plain text such as `sigma_allow`, `r_stress`, `d_stress`, and `a = b/c`, so it will be easier to read and copy into your GitHub portfolio.
```
