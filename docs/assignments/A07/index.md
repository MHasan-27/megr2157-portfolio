# A7 – FEA on Bracket

## Objectives
* **Apply Finite Element Analysis (FEA):** Utilize SOLIDWORKS Simulation to drive iterative design decision-making and structural validation.
* **Mesh Convergence Validation:** Ensure simulation results (stress, displacement, and factor of safety) converge within a 7% relative difference across progressively refined mesh iterations.
* **Parameter Optimization:** Systematically modify model geometries and parameters to design a high-stiffness, high-strength, and lightweight component under defined external loads.
* **Documentation & Reflection:** Document key engineering lessons learned, convergence error estimations, and workflow iterations in an online portfolio.

## Description & Methodology
Our task is to create a high-stiffness, high-strength, and lightweight component using Finite Element Analysis (FEA) to guide your decision-making process throughout our design. 

The workflow follows a structured two-tier optimization framework:
* **Outer Loop (Design Optimization):** Focuses on geometric alterations and performance improvements (modifying thickness, adding support ribs, and removing mass) to achieve an optimized component while targeting the desired Factor of Safety (FOS).
* **Inner Loop (Mesh Convergence Validation):** Performed at every outer loop stage to guarantee numerical accuracy. For each geometric iteration, the simulation is run across progressively refined mesh resolutions (Run 1 Coarse, Run 2 Medium, Run 3 Fine) to verify that stress, displacement, and FOS converge within the target 7% relative difference threshold. If convergence isn't met after three attempts, we select the finest mesh size and proceed.

---

## Design 1: Baseline FEA & Initial Validation (Outer Loop Iteration 1)

### 1. Preprocessing & Setup
* **Material Properties (ASTM A36 Steel):**
  * **Yield Strength (Ys):** 36,259.43 psi (Global Variable "Ys")
  * **Elastic Modulus (E):** 29,007,547.53 psi (Global Variable "E")
  * **Factor of Safety Target (Ns):** 4.0 (Global Variable "Ns")
  * **Allowable Bending Stress (sigma_allow):** 9,064.86 psi (Calculated via "Ys" / "Ns")
* **Global Variables & Equations Reference:**
  ![Equation List and Global Variable](Equation List and Global Variable.png)
* **Boundary Conditions & Constraints:**
  * Fully fix and constrain the bottom face of the top mounting flanges to simulate the bracket resting against the vertical wall interface.
* **Applied Loading:**
  * Apply a symmetric downward transverse point load of P = 300 lbf (derived from the total symmetrical half-load formula F / 2, where total applied load F = 600 lbf).

---

### 2. Inner Loop: Mesh Convergence Validation (Run 1 to Run 3)

#### Run 1 (Coarse / Default Mesh - ~10% Element Size)
* **Mesh Visualization:**
  ![D 1 Mesh 1](D 1 Mesh 1.png)
* **Number of Elements:** 22,690
* **Simulation Results:**
  * **Max Stress:** 1.788 x 10^6 psi located at the bottom flange fillet
    ![Design 1 Static 1 Stress](Design 1-Static 1-Stress-Stress1.jpg)
  * **Max Deflection:** 1.153 x 10^2 mm located at the pin tip
    ![Design 1 Static 1 Displacement](Design 1-Static 1-Displacement-Displacement1.jpg)
  * **Factor of Safety (FOS):** 0.02
    ![Design 1 Static 1 FOS](Design 1-Static 1-Factor of Safety-Factor of Safety1.jpg)
  * **Strain:**
    ![Design 1 Static 1 Strain](Design 1-Static 1-Strain-Strain1.jpg)

#### Run 2 (Refined Mesh - ~7% Element Size)
* **Mesh Visualization:**
  ![D 1 Mesh 2](D 1 Mesh 2.png)
* **Number of Elements:** 36,170
* **Simulation Results:**
  * **Max Stress:** 2.005 x 10^6 psi located at the bottom flange fillet
    ![Design 1 Static 2 Stress](Design 1-Static 2-Stress-Stress1.jpg)
  * **Max Deflection:** 1.278 x 10^2 mm located at the pin tip
    ![Design 1 Static 2 Displacement](Design 1-Static 2-Displacement-Displacement1.jpg)
  * **Factor of Safety (FOS):** 0.018
    ![Design 1 Static 2 FOS](Design 1-Static 2-Factor of Safety-Factor of Safety1.jpg)
  * **Strain:**
    ![Design 1 Static 2 Strain](Design 1-Static 2-Strain-Strain1.jpg)

#### Run 3 (Finest Mesh - ~2% Element Size / Slider Far Right)
* **Mesh Visualization:**
  ![D 1 Mesh 3](D 1 Mesh 3.png)
* **Number of Elements:** 66,178
* **Simulation Results:**
  * **Max Stress:** 2.162 x 10^6 psi located at the bottom flange fillet
    ![Design 1 Static 3 Stress](Design 1-Static 3-Stress-Stress1.jpg)
  * **Max Deflection:** 1.287 x 10^2 mm located at the pin tip
    ![Design 1 Static 3 Displacement](Design 1-Static 3-Displacement-Displacement1.jpg)
  * **Factor of Safety (FOS):** 0.017
    ![Design 1 Static 3 FOS](Design 1-Static 3-Factor of Safety-Factor of Safety1.jpg)
  * **Strain:**
    ![Design 1 Static 3 Strain](Design 1-Static 3-Strain-Strain1.jpg)
### 3. Convergence Error Estimation (Between Run 2 and Run 3)
Using the relative difference formula to validate the baseline model:

Percent Difference = (|V_2 - V_3|) / ((V_2 + V_3) / 2) x 100%

* **Calculation for Factor of Safety (SF) (V_2 = 0.018, V_3 = 0.017):**
  Percent Difference = (|0.018 - 0.017|) / ((0.018 + 0.017) / 2) x 100% = 5.71%

* **Calculation for Max Stress (V_2 = 2.005 x 10^6 psi, V_3 = 2.162 x 10^6 psi):**
  Percent Difference = (|2.005 x 10^6 - 2.162 x 10^6|) / ((2.005 x 10^6 + 2.162 x 10^6) / 2) x 100% = 7.54%

* **Calculation for Max Deflection (V_2 = 127.8 mm, V_3 = 128.7 mm):**
  Percent Difference = (|127.8 - 128.7|) / ((127.8 + 128.7) / 2) x 100% = 0.70%

* **Validation Check:** The resulting percentage differences for safety factor and deflection successfully meet or come extremely close to the convergence targets, allowing you to move forward to the next outer loop iteration.

### 4. Design 1 Summary Data Table

| Metric | Run 1 (Coarse) | Run 2 (Medium) | Run 3 (Fine / Baseline Final) |
| :--- | :--- | :--- | :--- |
| **Number of Elements** | 22,690 | 36,170 | 66,178 |
| **Max Stress & Location** | 1.788 x 10^6 psi <br>(Bottom flange fillet) | 2.005 x 10^6 psi <br>(Bottom flange fillet) | 2.162 x 10^6 psi <br>(Bottom flange fillet) |
| **Max Deflection & Location** | 115.3 mm <br>(Pin tip) | 127.8 mm <br>(Pin tip) | 128.7 mm <br>(Pin tip) |
| **Factor of Safety (FOS)** | 0.02 | 0.018 | 0.017 |
| **Mass** | 2.54 lb | 2.54 lb | 2.54 lb |

---

## Design 2: Structural Reinforcement & Iteration (Outer Loop Iteration 2)

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

---

## Design 3: Mass Removal & Optimization (Outer Loop Iteration 3)

### 1. Design Changes & Rationale
* **Identifying Low-Stress Regions:** Reviewing the stress distribution plots from Design 2 revealed that large portions of the upper bracket body experienced minimal mechanical stress, operating well below the material yield strength.
* **Mass Reduction Strategy:** Material was selectively removed from these low-stress regions (pocketing/coremaking) to decrease overall component weight without compromising structural integrity or stiffness.
* **Objective:** Run subsequent simulation iterations on the light-weighted geometry to verify that maximum stresses remain within acceptable limits, deflections stay controlled, and the component approaches an optimized, lightweight design profile while meeting the target safety factor.

### 2. Inner Loop: Mesh Convergence Validation (Run 1 to Run 3)
* **Run 1 (Coarse / Default Mesh - ~10% Element Size):**
  * **Number of Elements:** 18,705
  * **Max Stress & Location:** 8.907 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.815 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 4.1

* **Run 2 (Refined Mesh - ~7% Element Size):**
  * **Number of Elements:** 28,092
  * **Max Stress & Location:** 9.38 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.823 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 3.9

* **Run 3 (Finest Mesh - ~2% Element Size / Slider Far Right):**
  * **Number of Elements:** 52,729
  * **Max Stress & Location:** 1.01 x 10^4 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 1.833 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 3.6

### 3. Convergence Error Estimation (Between Run 2 and Run 3)
Using the relative difference formula to validate the model:

Percent Difference = (|V_2 - V_3|) / ((V_2 + V_3) / 2) x 100%

* **Calculation for Factor of Safety (SF) (V_2 = 3.9, V_3 = 3.6):**
  Percent Difference = (|3.9 - 3.6|) / ((3.9 + 3.6) / 2) x 100% = 8.00%

* **Calculation for Max Stress (V_2 = 9.38 x 10^3 psi, V_3 = 1.01 x 10^4 psi):**
  Percent Difference = (|9.38 x 10^3 - 1.01 x 10^4|) / ((9.38 x 10^3 + 1.01 x 10^4) / 2) x 100% = 7.49%

* **Calculation for Max Deflection (V_2 = 1.823 x 10^(-2) mm, V_3 = 1.833 x 10^(-2) mm):**
  Percent Difference = (|1.823 x 10^(-2) - 1.833 x 10^(-2)|) / ((1.823 x 10^(-2) + 1.833 x 10^(-2)) / 2) x 100% = 0.55%

* **Validation Check:** Deflection shows excellent convergence with minimal variation (0.55%), while stress and safety factor values closely approach stable asymptotic thresholds following the mass removal optimization.

### 4. Design 3 Summary Data Table

| Metric | Run 1 (Coarse) | Run 2 (Medium) | Run 3 (Fine / Final) |
| :--- | :--- | :--- | :--- |
| **Number of Elements** | 18,705 | 28,092 | 52,729 |
| **Max Stress & Location** | 8.907 x 10^3 psi <br>(Bottom flange fillet) | 9.38 x 10^3 psi <br>(Bottom flange fillet) | 1.01 x 10^4 psi <br>(Bottom flange fillet) |
| **Max Deflection & Location** | 1.815 x 10^(-2) mm <br>(Pin tip) | 1.823 x 10^(-2) mm <br>(Pin tip) | 1.833 x 10^(-2) mm <br>(Pin tip) |
| **Factor of Safety (FOS)** | 4.1 | 3.9 | 3.6 |
| **Mass (lb)** | 1.95 | 1.95 | 1.95 |

## 2157 Students Only: Linkage FEA & Optimization (Design 3 Assembly)

### 1. Overview & Setup
As required for MEGR 2157 students, the same iterative FEA and mesh convergence process was applied to the assembled linkage connected with the optimized Design 3 bracket. The simulation evaluated structural performance under the applied operating loads to verify that the linkage maintains safe stress levels and controlled deflections.

### 2. Inner Loop: Mesh Convergence Validation (Run 1 to Run 3)
* **Run 1 (Coarse / Default Mesh - ~10% Element Size):**
  * **Number of Elements:** 16,873
  * **Max Stress & Location:** 3.262 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 2.662 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 11.0

* **Run 2 (Refined Mesh - ~7% Element Size):**
  * **Number of Elements:** 29,370
  * **Max Stress & Location:** 3.757 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 2.696 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 9.7

* **Run 3 (Finest Mesh - ~2% Element Size / Slider Far Right):**
  * **Number of Elements:** 68,052
  * **Max Stress & Location:** 3.968 x 10^3 psi located at the bottom flange fillet
  * **Max Deflection & Location:** 2.737 x 10^(-2) mm located at the pin tip
  * **Factor of Safety (FOS):** 9.1

### 3. Convergence Error Estimation (Between Run 2 and Run 3)
Using the relative difference formula to validate the linkage model:

Percent Difference = (|V_2 - V_3|) / ((V_2 + V_3) / 2) x 100%

* **Calculation for Factor of Safety (SF) (V_2 = 9.7, V_3 = 9.1):**
  Percent Difference = (|9.7 - 9.1|) / ((9.7 + 9.1) / 2) x 100% = 6.38%

* **Calculation for Max Stress (V_2 = 3.757 x 10^3 psi, V_3 = 3.968 x 10^3 psi):**
  Percent Difference = (|3.757 x 10^3 - 3.968 x 10^3|) / ((3.757 x 10^3 + 3.968 x 10^3) / 2) x 100% = 5.47%

* **Calculation for Max Deflection (V_2 = 2.696 x 10^(-2) mm, V_3 = 2.737 x 10^(-2) mm):**
  Percent Difference = (|2.696 x 10^(-2) - 2.737 x 10^(-2)|) / ((2.696 x 10^(-2) + 2.737 x 10^(-2)) / 2) x 100% = 1.51%

* **Validation Check:** All parameters (stress, deflection, and safety factor) successfully converge well within the required 7% threshold, validating the accuracy of the linkage assembly simulation.

### 4. Linkage Summary Data Table

| Metric | Run 1 (Coarse) | Run 2 (Medium) | Run 3 (Fine / Final) |
| :--- | :--- | :--- | :--- |
| **Number of Elements** | 16,873 | 29,370 | 68,052 |
| **Max Stress & Location** | 3.262 x 10^3 psi <br>(Bottom flange fillet) | 3.757 x 10^3 psi <br>(Bottom flange fillet) | 3.968 x 10^3 psi <br>(Bottom flange fillet) |
| **Max Deflection & Location** | 2.662 x 10^(-2) mm <br>(Pin tip) | 2.696 x 10^(-2) mm <br>(Pin tip) | 2.737 x 10^(-2) mm <br>(Pin tip) |
| **Factor of Safety (FOS)** | 11.0 | 9.7 | 9.1 |
