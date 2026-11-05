# Pulley System Design – Power Transmission Between Parallel Axes

## Objective

Design a pulley system to transfer power between two parallel axes separated by a center distance of 6.0 inches. The system must meet the following design constraints and performance requirements:

- **Pulley Diameter:** Both pulleys shall have a pitch diameter of 3.0 inches (D1 = D2 = 3.0 in).
- **Rotational Speed:** Operating speed selected at 2000 rpm.
- **Belt Tension (Static):** Initial static belt tension (T0) selected at 6.0 lbf under stationary conditions.
- **Material & Geometry Selection:**  
  - Pulleys constructed from 1060 Hardened Steel with a machined round groove and a 0.250 in. bore diameter.  
  - Shafts modeled using 1060 Hardened Steel.  
  - Journal bearings specified from sintered porous bronze using Machinery’s Handbook (Table 4, pg. 2440).
- **Safety Factor:** Minimum factor of safety ns = 3.0 across all stress calculations, using segmented polyurethane elastomer belting with a yield strength sigma_y = 3.25 MPa (471 psi) at 20% strain.

---

## 1. Belt Selection & Analysis (25%)

### a. Knowns & Unknowns

**Given / Design Choices:**

| Parameter                          | Value                                      |
|------------------------------------|--------------------------------------------|
| Center distance (C)                | 6.0 in                                     |
| Pulley pitch diameter (D1 = D2 = D)| 3.0 in (R = 1.5 in)                        |
| Rotational speed (n)               | 2000 rpm                                   |
| Initial static belt tension (T0)   | 6.0 lbf                                    |
| Belt material                      | Polyurethane elastomer (sigma_y = 471 psi at 20% strain) |
| Design Factor of Safety (ns)       | 3.0                                        |
| Allowable working stress (sigma_allow) | sigma_allow = sigma_y / ns = 471 / 3 = 157 psi |
| Coefficient of friction (mu)       | 0.35 (steel pulley / polyurethane belt)   |
| Contact angle (theta)              | pi rad (180 deg)                           |

**Unknowns:**
- Tight-side tension (T1) and loose-side tension (T2)
- Minimum cross-sectional area (A_min) and required belt diameter (db)
- Pitch/outer circumference of the belt (L)

### b. Free Body Diagram (FBD) of Belt/Pulley System

*(Insert Free Body Diagram here)*

### c. Symbolic Equations

Capstan (belt friction) equation:

T1 / T2 = e^(mu * theta)

Static tension relation:

T0 = (T1 + T2) / 2

Transmitted torque:

T = (T1 - T2) * R

Minimum cross-sectional area:

A_min = T1 / sigma_allow

Belt length (open belt drive, equal diameter pulleys):

L = 2C + pi * D

### d. Numerical Solutions & Belt Selection

From the relations above with T0 = 6.0 lbf, mu = 0.35, and theta = pi:

T1 / T2 = e^(0.35 * pi) ≈ 3.00

Solving simultaneously with T0 = 6.0 lbf yields:

T1 = 9.00 lbf,   T2 = 3.00 lbf

Minimum cross-sectional area:

A_min = 9.00 / 157 ≈ 0.0573 in²

Required belt diameter (assuming circular cross-section):

db = sqrt(4 * A_min / pi) ≈ 0.270 in

Belt length:

L = 2*(6.0) + pi*(3.0) = 12 + 9.42 = 21.42 in

---

## 2. Shaft Diameter Design (25%)

### a. Knowns & Unknowns

| Parameter                          | Value                                      |
|------------------------------------|--------------------------------------------|
| Shaft Material                     | 1060 Hardened Steel                        |
| Pulley Material                    | 1060 Hardened Steel (Bore diameter: 0.250 in) |
| Tensile Yield Strength (sigma_y)   | 90,000 psi                                 |
| Shear Yield Strength (tau_y)       | tau_y = 0.577 * sigma_y = 51,930 psi (Distortion Energy Theory) |
| Factor of Safety (ns)              | 3.0                                        |
| Allowable Shear Stress (tau_allow) | tau_allow = 51,930 / 3 = 17,310 psi        |

**Unknowns:**
- Radial force bending load (F_radial)
- Transmitted Torque (T)
- Minimum Shaft Diameter (ds)

### b. Free Body Diagram (FBD) of Shaft

*(Insert Free Body Diagram here)*

### c. Symbolic Equations for Minimum Shaft Diameter

Radial load:

F_radial = T1 + T2

Transmitted torque:

T = (T1 - T2) * R

Minimum shaft diameter (based on shear stress):

ds = (16 * T / (pi * tau_allow))^(1/3)

### d. Numerical Calculations

F_radial = 9.00 + 3.00 = 12.0 lbf

T = (9.00 - 3.00) * 1.5 = 9.00 in-lbf

ds = (16 * 9.00 / (pi * 17,310))^(1/3) ≈ 0.138 in

**Selected standard shaft diameter:** ds = 0.250 in (matches commercial sleeve bearing bore and provides additional stiffness).

---

## 3. Journal Bearing Design (30%)

*(Machinery’s Handbook, pg. 2440 – Porous Metal / Sintered Bearings)*

### a. Knowns & Unknowns

| Parameter                          | Value                                      |
|------------------------------------|--------------------------------------------|
| Shaft Diameter (ds)                | 0.250 in                                   |
| Selected Bearing Length (Lb)       | 0.375 in (Lb / ds = 1.5)                   |
| Total Radial Load (W)              | F_radial = 12.0 lbf                        |
| Rotational Speed (n)               | 2000 rpm                                   |

**Unknowns:**
- Bearing Projected Area (Ap)
- Operating Pressure (P) in psi
- Surface Speed (V) in ft/min (fpm)
- Calculated PV Factor (psi · fpm)
- Suitable Material Selection

### b. Free Body Diagram & Schematic

*(Insert Free Body Diagram / Schematic here)*

### c. Symbolic Equations

Projected area:

Ap = ds * Lb

Operating pressure:

P = W / Ap

Surface speed:

V = (pi * ds * n) / 12   (fpm)

PV rating:

PV = P * V

### d. Numerical Solutions

Ap = 0.250 * 0.375 = 0.09375 in²

P = 12.0 / 0.09375 = 128.0 psi

V = (pi * 0.250 * 2000) / 12 = 130.90 fpm

PV = 128.0 * 130.90 = 16,755 psi · fpm

### e. Material Selection Based on Table 4

**Selected Material:** Porous Bronze (SAE 841 Oil-Embedded Bronze)

**Comparison with Table 4 Application Limits — Sintered Metal and Nonmetallic Bearings:**

| Parameter              | Calculated Value     | Table 4 Limit (Porous Bronze) | Status                  |
|------------------------|----------------------|-------------------------------|-------------------------|
| Max Pressure (P)       | 128.0 psi            | 4,500 psi                     | PASS (<< 4,500 psi)     |
| Surface Speed (V)      | 130.90 fpm           | 1,500 fpm                     | PASS (<< 1,500 fpm)     |
| PV Rating              | 16,755 psi · fpm     | 50,000 psi · fpm              | PASS (<< 50,000 psi · fpm) |

**Conclusion:** Porous bronze is the ideal match because it satisfies all individual pressure and velocity constraints while providing a substantial safety margin below the maximum allowable PV limit of 50,000 psi · fpm.

---

## 4. Frame Support Analysis

- **Structural Setup:** A-frame configuration supporting parallel 1060 steel shafts across a 6.0 in center distance.
- **Material Selection:** 0.50 in thick 6061-T6 Aluminum plate housing.
- **Load Evaluation:** Each journal bearing housing transfers a horizontal reaction load W = 12.0 lbf.  
  Direct shear stress and structural bending moments on the side plates remain under 100 psi, which is negligible compared to the yield strength of aluminum (≈ 35,000 psi). This prevents out-of-plane deflection and preserves parallel shaft alignment under rotational vibration.

---

## 5. Engineering Lessons Learned

**Lesson 1 – Capstan Friction Dynamics**  
Increasing static belt pre-tension from 5.0 lbf to 6.0 lbf proportionally increased maximum allowable tight-side tension (T1 = 9.00 lbf) and transmitted torque (9.00 in-lbf), demonstrating how mechanical pre-load directly scales power transfer capability through capstan friction (e^(mu * theta)).

**Lesson 2 – Speed Effects on PV Values**  
Operating at 2000 rpm increased linear surface speed to 130.90 fpm, driving the system PV value up to 16,755 psi · fpm. While well within the 50,000 psi · fpm threshold for oil-embedded porous bronze, it highlights how rotational speed dominates bearing thermal dissipation requirements even under modest loads.

**Lesson 3 – Standard Stock Alignment**  
Although theoretical calculations yielded a minimum shaft diameter of 0.138 in, selecting standard 0.250 in stock matches commercial sleeve bearing inner diameters and prevents localized shaft flexure under dynamic torque loads.
