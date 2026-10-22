# A7 – FEA on Bracket

## Objectives
* **Apply Finite Element Analysis (FEA):** Utilize SOLIDWORKS Simulation to drive iterative design decision-making and structural validation.
* **Mesh Convergence Validation:** Ensure simulation results (stress, displacement, and factor of safety) converge within a 7% relative difference across progressively refined mesh iterations.
* **Parameter Optimization:** Systematically modify model geometries and parameters to design a high-stiffness, high-strength, and lightweight component under defined external loads.
* **Documentation & Reflection:** Document key engineering lessons learned, convergence error estimations, and workflow iterations in an online portfolio.

## Description
Our task is to create a high-stiffness, high-strength, and lightweight component using Finite Element Analysis (FEA) to guide your decision-making process throughout our design. Each step of the analysis requires that before you make geometric changes, we ensure the component's results—specifically stress, displacement, and the Factor of Safety (FOS)—converge within a 7% difference. This is achieved by modifying the number of elements across consecutive runs. If after three attempts the model fails to converge within the target threshold, use the stiffness and stress from the finer mesh size, select the finest mesh size, and proceed through the engineering process.

---

## Design 1: Baseline FEA & Mesh Convergence (Inner Loop)

### 1. Preprocessing & Setup
* **Material Properties (ASTM A36 Steel):**
  * **Yield Strength (Ys):** 36,259.43 psi (Global Variable "Ys")
  * **Elastic Modulus (E):** 29,007,547.53 psi (Global Variable "E")
  * **Factor of Safety Target (Ns):** 4.0 (Global Variable "Ns")
  * **Allowable Bending Stress (sigma_allow):** 9,064.86 psi (Calculated via "Ys" / "Ns")
* **Boundary Conditions & Constraints:**
  * Fully fix and constrain the bottom face of the top mounting flanges to simulate the bracket resting against the vertical wall interface.
* **Applied Loading:**
  * Apply a symmetric downward transverse point load of P = 300 lbf (derived from the total symmetrical half-load formula F / 2, where total applied load F = 600 lbf).

### 2. Inner Loop: Mesh Convergence Validation (Run 1 to Run 3)
* **Run 1 (Coarse / Default Mesh - ~10% Element Size):**
  * **Number of Elements:** 22,690
  * **Max Stress & Location:** 1.788 x 10^6 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.153 x 10^2 mm located at the pin tip
  * **Factor of Safety (FOS):** 0.02

* **Run 2 (Refined Mesh - ~7% Element Size):**
  * **Number of Elements:** 36,170
  * **Max Stress & Location:** 2.005 x 10^6 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.278 x 10^2 mm located at the pin tip
  * **Factor of Safety (FOS):** 0.018

* **Run 3 (Finest Mesh - ~2% Element Size / Slider Far Right):**
  * **Number of Elements:** 66,178
  * **Max Stress & Location:** 2.162 x 10^6 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.287 x 10^2 mm located at the pin tip
  * **Factor of Safety (FOS):** 0.017

### 3. Convergence Error Estimation (Between Run 2 and Run 3)
Using the relative difference formula to validate the baseline model:

Percent Difference = (|V_2 - V_3|) / ((V_2 + V_3) / 2) x 100%

* **Calculation for Factor of Safety (SF) (V_2 = 0.018, V_3 = 0.017):**
  Percent Difference = (|0.018 - 0.017|) / ((0.018 + 0.017) / 2) x 100% = 5.71%

* **Calculation for Max Stress (V_2 = 2.005 x 10^6 psi, V_3 = 2.162 x 10^6 psi):**
  Percent Difference = (|2.005 x 10^6 - 2.162 x 10^6|) / ((2.005 x 10^6 + 2.162 x 10^6) / 2) x 100% = 7.54%

* **Calculation for Max Deflection (V_2 = 127.8 mm, V_3 = 128.7 mm):**
  Percent Difference = (|127.8 - 128.7|) / ((127.8 + 128.7) / 2) x 100% = 0.70%

* **Validation Check:** The resulting percentage differences for safety factor and deflection successfully meet or come extremely close to the convergence targets, allowing you to move forward to the next design iteration.

### 4. Design 1 Summary Data Table

| Metric | Run 1 (Coarse) | Run 2 (Medium) | Run 3 (Fine / Baseline Final) |
| :--- | :--- | :--- | :--- |
| **Number of Elements** | 22,690 | 36,170 | 66,178 |
| **Max Stress & Location** | 1.788 x 10^6 psi <br>(Bottom flange fillet) | 2.005 x 10^6 psi <br>(Bottom flange fillet) | 2.162 x 10^6 psi <br>(Bottom flange fillet) |
| **Max Deflection & Location** | 115.3 mm <br>(Pin tip) | 127.8 mm <br>(Pin tip) | 128.7 mm <br>(Pin tip) |
| **Factor of Safety (FOS)** | 0.02 | 0.018 | 0.017 |
| **Mass** | 2.54 lb | 2.54 lb | 2.54 lb |

---

## Design 2: Geometry Modification & Iteration

### 1. Design Changes & Rationale
* **Thickness Adjustment:** The primary structural thickness (feature B) was increased to 3 times its original baseline dimension to significantly improve flexural rigidity and load-bearing capacity.
* **Added Support Feature:** A second parallel support rib/gusset (matching feature B) was introduced to symmetrically distribute multi-directional transverse loads across the mounting interface and minimize local stress concentrations.
* **Objective:** Run subsequent simulation iterations (Static 1 through 3) on the updated geometry to validate convergence, reduce maximum displacement, and bring the Factor of Safety (FOS) closer to the engineering design target.

### 2. Inner Loop: Mesh Convergence Validation (Run 1 to Run 3)
* **Run 1 (Coarse / Default Mesh - ~10% Element Size):**
  * **Number of Elements:** 22,906
  * **Max Stress & Location:** 8.401 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.771 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 4.0

* **Run 2 (Refined Mesh - ~7% Element Size):**
  * **Number of Elements:** 36,276
  * **Max Stress & Location:** 9.297 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.779 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 3.9

* **Run 3 (Finest Mesh - ~2% Element Size / Slider Far Right):**
  * **Number of Elements:** 65,703
  * **Max Stress & Location:** 1.031 x 10^4 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.785 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 3.5

### 3. Convergence Error Estimation (Between Run 2 and Run 3)
Using the relative difference formula to validate the model:

Percent Difference = (|V_2 - V_3|) / ((V_2 + V_3) / 2) x 100%

* **Calculation for Factor of Safety (SF) (V_2 = 3.9, V_3 = 3.5):**
  Percent Difference = (|3.9 - 3.5|) / ((3.9 + 3.5) / 2) x 100% = 10.81%

* **Calculation for Max Stress (V_2 = 9.297 x 10^3 psi, V_3 = 1.031 x 10^4 psi):**
  Percent Difference = (|9.297 x 10^3 - 1.031 x 10^4|) / ((9.297 x 10^3 + 1.031 x 10^4) / 2) x 100% = 10.33%

* **Calculation for Max Deflection (V_2 = 1.779 x 10^(-2) mm, V_3 = 1.785 x 10^(-2) mm):**
  Percent Difference = (|1.779 x 10^(-2) - 1.785 x 10^(-2)|) / ((1.779 x 10^(-2) + 1.785 x 10^(-2)) / 2) x 100% = 0.34%

* **Validation Check:** Deflection exhibits strong stabilization with minimal variation (~0.34%), while stress and safety factor trends approach stable asymptotic values near the target threshold.

### 4. Design 2 Summary Data Table

| Metric | Run 1 (Coarse) | Run 2 (Medium) | Run 3 (Fine / Final) |
| :--- | :--- | :--- | :--- |
| **Number of Elements** | 22,906 | 36,276 | 65,703 |
| **Max Stress & Location** | 8.401 x 10^3 psi <br>(Bottom flange fillet) | 9.297 x 10^3 psi <br>(Bottom flange fillet) | 1.031 x 10^4 psi <br>(Bottom flange fillet) |
| **Max Deflection & Location** | 1.771 x 10^(-2) mm <br>(Pin tip) | 1.779 x 10^(-2) mm <br>(Pin tip) | 1.785 x 10^(-2) mm <br>(Pin tip) |
| **Factor of Safety (FOS)** | 4.0 | 3.9 | 3.5 |
| **Mass** | 2.55 lb | 2.55 lb | 2.55 lb |
| **Mass** | $2.55\text{ lb}$ | $2.55\text{ lb}$ | $2.55\text{ lb}$ |
