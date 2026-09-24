# A5 – [Bracket Design]

# Bracket Design — Assignment Objectives & Feature A Stress Analysis

## 1. Assignment Objectives

### Design for Strength & Safety

Determine the minimum thickness/diameter for each structural feature of the bracket so that the material does not yield or break under a **600 lbf** load with a **Factor of Safety (FoS) of 4**.

### Design for Stiffness & Deflection

Calculate the minimum required dimensions so that elastic deflection/stretching remains within **0.005 in per feature**.

### Load Path Tracing

Transfer the calculated reaction forces sequentially from **Feature A through Feature E** to ensure static equilibrium throughout the entire mounting bracket assembly.

### Manufacturing Precision — Fits

Select appropriate **ANSI B4.1 standard fits and tolerances** for interface dimensions to ensure proper mechanical assembly with mating components.

### Technical Documentation

Present the following in the virtual portfolio:

* Complete Free Body Diagrams (FBDs)
* Step-by-step algebraic solutions
* Numerical calculations
* Multiview engineering drawings
* Final design dimensions
* CAD model and verification
* Manufacturing fits and tolerances

---

# 2. Material & Global Parameters Baseline

| Parameter                                     |             Value |
| --------------------------------------------- | ----------------: |
| **Material**                                  |    ASTM A36 Steel |
| **Applied Force, $F$**                        |           600 lbf |
| **Force per Leg, $F_{\text{leg}}$**           |           300 lbf |
| **Yield Strength, $Y_s$**                     |     36,259.43 psi |
| **Elastic Modulus, $E$**                      | 29,007,547.53 psi |
| **Factor of Safety, $N_s$**                   |               4.0 |
| **Allowable Stress, $\sigma_{\text{allow}}$** |      9,064.86 psi |

The total applied load is symmetric:

$$
2F_{\text{leg}} = 600\text{ lbf}
$$

Therefore,

$$
F_{\text{leg}} = \frac{600}{2} = 300\text{ lbf}
$$

### Allowable Stress

The allowable stress is calculated using the Factor of Safety:

$$
\sigma_{\text{allow}}
=
\frac{Y_s}{N_s}
$$

$$
\sigma_{\text{allow}}
=
\frac{36,259.43}{4.0}
$$

$$
\boxed{\sigma_{\text{allow}} = 9,064.86\text{ psi}}
$$

or approximately:

$$
\boxed{\sigma_{\text{allow}} \approx 9.06\text{ ksi}}
$$

---

# 3. Feature A — Stress Analysis

Following the sequential load path described in **Appendix A** and **Appendix D**, Feature A is modeled as the **cylindrical support pin holding the polyester strap**.

## 3.1 Known Parameters

| Parameter                | Symbol                  |         Value |
| ------------------------ | ----------------------- | ------------: |
| Applied Load             | $F$                     |       600 lbf |
| Pin Length               | $L_A$                   |       2.00 in |
| Yield Strength           | $Y_s$                   | 36,259.43 psi |
| Factor of Safety         | $N_s$                   |           4.0 |
| Allowable Bending Stress | $\sigma_{\text{allow}}$ |  9,064.86 psi |

---

## 3.2 Unknowns

The following values must be determined:

* Minimum pin radius based on bending stress, $r_{\text{stress}}$
* Minimum pin diameter based on bending stress, $d_{\text{stress}}$
* Support reaction force, $R_y$
* Maximum reaction bending moment, $M_{\max}$

---

## 3.3 Assumptions

1. **Beam Model:**
   Feature A behaves as a solid circular cantilever beam rigidly fixed at $x=0$.

2. **Loading:**
   A transverse point load of $F=600$ lbf is applied at $x=L_A=2.00$ in.

3. **Shear Stress:**
   Direct shear failure is considered non-governing according to the assignment instructions.

4. **Material:**
   The material is assumed to be homogeneous and linearly elastic A36 steel.

---

# 4. Feature A — Free Body Diagram (FBD)

The support at $x=0$ provides:

* A vertical reaction force, $R_y$
* A reaction bending moment, $M_{\max}$

The free end experiences the applied strap load.

### Support Reaction

From static equilibrium:

$$
\sum F_y = 0
$$

Therefore,

$$
R_y = F
$$

$$
\boxed{R_y = 600\text{ lbf}}
$$

### Maximum Bending Moment

The maximum bending moment occurs at the fixed support:

$$
M_{\max}=F L_A
$$

Therefore:

$$
M_{\max}
=
(600\text{ lbf})(2.00\text{ in})
$$

$$
\boxed{M_{\max}=1,200\text{ lb}\cdot\text{in}}
$$

---

# 5. Feature A — Algebraic Stress Model

The bending stress is calculated using:

$$
\sigma = \frac{M_{\max}}{Z}
$$

The design must satisfy:

$$
\sigma \leq \sigma_{\text{allow}}
$$

Therefore, the required section modulus is:

$$
Z_{\text{req}}
=
\frac{M_{\max}}{\sigma_{\text{allow}}}
$$

Since:

$$
M_{\max}=F L_A
$$

we can write:

$$
\boxed{
Z_{\text{req}}
=
\frac{F L_A}{\sigma_{\text{allow}}}
}
$$

---

## 5.1 Section Modulus for a Solid Circular Pin

For a solid circular cross-section:

$$
Z=\frac{\pi r^3}{4}
$$

Alternatively, using diameter:

$$
\boxed{
Z=\frac{\pi d^3}{32}
}
$$

Setting the available section modulus equal to the required section modulus:

$$
\frac{\pi r^3}{4}=Z_{\text{req}}
$$

Solving for radius:

$$
r_{\text{stress}}
=
\sqrt[3]{\frac{4Z_{\text{req}}}{\pi}}
$$

Substituting the expression for $Z_{\text{req}}$:

$$
\boxed{
r_{\text{stress}}
=
\sqrt[3]{
\frac{4F L_A}
{\pi\sigma_{\text{allow}}}
}
}
$$

The required diameter is:

$$
\boxed{
d_{\text{stress}}=2r_{\text{stress}}
}
$$

---

# 6. Feature A — Numerical Solution

## Step 1 — Calculate Maximum Bending Moment

$$
M_{\max}=F L_A
$$

$$
M_{\max}
=
(600\text{ lbf})(2.00\text{ in})
$$

$$
\boxed{
M_{\max}=1,200\text{ lb}\cdot\text{in}
}
$$

---

## Step 2 — Calculate Required Section Modulus

$$
Z_{\text{req}}
=
\frac{M_{\max}}
{\sigma_{\text{allow}}}
$$

Substituting:

$$
Z_{\text{req}}
=
\frac{1,200}
{9,064.86}
$$

Therefore:

$$
\boxed{
Z_{\text{req}}\approx0.13238\text{ in}^3
}
$$

---

## Step 3 — Calculate Minimum Radius

Using:

$$
r_{\text{stress}}
=
\sqrt[3]{
\frac{4Z_{\text{req}}}{\pi}
}
$$

Substitute:

$$
r_{\text{stress}}
=
\sqrt[3]{
\frac{4(0.13238)}{\pi}
}
$$

$$
r_{\text{stress}}
=
\sqrt[3]{0.16855}
$$

Therefore:

$$
\boxed{
r_{\text{stress}}\approx0.5524\text{ in}
}
$$

---

## Step 4 — Calculate Minimum Diameter

The required diameter is:

$$
d_{\text{stress}}
=
2r_{\text{stress}}
$$

$$
d_{\text{stress}}
=
2(0.5524)
$$

Therefore:

$$
\boxed{
d_{\text{stress}}\approx1.105\text{ in}
}
$$

---

# 7. Feature A — Final Stress Results

| Quantity                                   |        Result |
| ------------------------------------------ | ------------: |
| Applied Load, $F$                          |       600 lbf |
| Pin Length, $L_A$                          |       2.00 in |
| Reaction Force, $R_y$                      |       600 lbf |
| Maximum Moment, $M_{\max}$                 |   1,200 lb·in |
| Required Section Modulus, $Z_{\text{req}}$ |   0.13238 in³ |
| Minimum Radius, $r_{\text{stress}}$        | **0.5524 in** |
| Minimum Diameter, $d_{\text{stress}}$      |  **1.105 in** |

### Stress-Based Design Requirement

The minimum theoretical pin diameter based on bending stress is:

$$
\boxed{
d_{\text{stress}}\approx1.105\text{ in}
}
$$

A practical manufactured diameter should then be selected **at or above this theoretical minimum**, while also checking the deflection requirement, available standard sizes, connection geometry, and other applicable failure modes.

---

# 8. Reaction Force Transfer to Feature B

The reactions developed at the base of **Feature A** become the applied loads for **Feature B**.

Therefore:

### Transverse Force

$$
P_B=R_y
$$

$$
\boxed{
P_B=600\text{ lbf}
}
$$

### Applied Moment

$$
M_B=M_{\max}
$$

$$
\boxed{
M_B=1,200\text{ lb}\cdot\text{in}
}
$$

Thus, the loading passed from Feature A to Feature B is:

| Feature B Input         |           Value |
| ----------------------- | --------------: |
| Transverse Force, $P_B$ |     **600 lbf** |
| Moment, $M_B$           | **1,200 lb·in** |

This establishes the sequential load path:

$$
\boxed{
\text{Applied Load}
\rightarrow
\text{Feature A}
\rightarrow
\text{Feature B}
\rightarrow
\text{Feature C}
\rightarrow
\text{Feature D}
\rightarrow
\text{Feature E}
}
$$

Each feature will be analyzed using the reactions transferred from the preceding feature.

---

# 9. Feature A — Summary

The Feature A cylindrical support pin was modeled as a solid circular cantilever subjected to a **600 lbf transverse load** at a distance of **2.00 in** from the fixed support.

The resulting maximum bending moment is:

$$
\boxed{M_{\max}=1,200\text{ lb}\cdot\text{in}}
$$

Using an allowable stress of:

$$
\boxed{\sigma_{\text{allow}}=9,064.86\text{ psi}}
$$

the required section modulus is:

$$
\boxed{Z_{\text{req}}\approx0.13238\text{ in}^3}
$$

The resulting minimum theoretical dimensions are:

$$
\boxed{r_{\text{stress}}\approx0.5524\text{ in}}
$$

$$
\boxed{d_{\text{stress}}\approx1.105\text{ in}}
$$

The resulting reactions are transferred to Feature B for the next stage of the structural analysis.

---

## Next Analysis

The next step is to use:

$$
\boxed{P_B=600\text{ lbf}}
$$

and

$$
\boxed{M_B=1,200\text{ lb}\cdot\text{in}}
$$

as the loading conditions for the **Feature B stress and deflection analysis**.

