# A3: Parametric and FEA Report

## Section 1: Parametric Design

### 1.a Inputs & Parameters
* **Shape:** Solid Circular Bar
* **Diameter (d):** 0.50 in
* **Cross-Sectional Area (A):** Area = (pi * d^2) / 4 = (3.1416 * (0.50)^2) / 4 = 0.19635 sq in (~0.20 sq in)
* **Load (F):** 500.00 lbf
* **Max Deflection (def):** 0.009 in
* **Material:** 1060 Alloy Aluminum
* **Young's Modulus (E):** 10,007,603.90 psi

---

### 1.b Hand Calculation for Length
Using the direct tension elongation formula: def = (F * L) / (A * E) => L = (def * A * E) / F

Substituting the parameter values: L = (0.009 in * 0.19635 sq in * 10,007,603.90 psi) / 500.00 lbf = 35.37 in

---

### 1.c CAD Parametric Setup

**Global Equations Table:**
![Global Variable](Global%20Variable%20.png)

**Step 1:** Create a circle on the Front Plane and dimension its diameter to the global variable "d".
![Design 1](Design%201.png)

**Step 2:** Extrude the circle to the global variable "L" length (35.37 in).
![Design 2](Design%202.png)

**Material Selection:**
![Material Selection 1060 Alloy](Material%20Selection%201060%20Alloy.png)

---

## Section 2: FEA (Finite Element Analysis)

> **Note:** Unable to do mesh since SolidWorks Student account has limitations on simulation and only provides the SimulationXpress wizard option.

* **Boundary Conditions:** Fixed one circular end face; applied 500 lbf axial tensile load to the opposite end face.
* **Axial Deflection:** 0.0090 in
* **Nominal Stress (sigma):** Stress = F / A = 500 lbf / 0.19635 sq in = 2,546.5 psi (~2.55 ksi)
* **Yield Strength (Sy):** 3,999.30 psi (~4.00 ksi)
* **Factor of Safety (FOS):** FOS = Sy / Stress = 3,999.30 psi / 2,546.5 psi = 1.57
---

## Section 3: Design Reflection

### 3.a Hand-Calc vs. FEA Comparison
* **Hand-calc Deflection:** 0.0090 in
* **FEA Deflection:** 0.0090 in
* **Percent Difference:** 0.00%
* **Explanation:** The hand calculation and FEA match completely because the geometry is a simple uniform cylinder under pure axial tension. There are no stress concentrations or bending moments, making the standard 1D formula exact.
* **Trusted Result:** Both results are equally trustworthy for this simple geometry.

### 3.b Pin Hole Stress Concentration Analysis
* **Stress Concentration Factor (Kt):** ~2.50
* **Estimated Peak Stress:** Peak Stress = Kt * Stress = 2.50 * 2,546.5 psi = 6,366.25 psi (~6.37 ksi)
* **Safety Factor with Hole:** FOS_hole = Sy / Peak Stress = 3,999.30 psi / 6,366.25 psi = 0.63
* **Conclusion:** Peak stress (6.37 ksi) exceeds yield strength (4.00 ksi), so the safety factor falls below 1.0 and the part would yield around the hole.

### Project Images
* **Deformation Map:**  
  ![Deformation](Deformation.png)
* **Displacement Map:**  
  ![Displacement](Displacement%20.png)
* **Stress Map:**  
  ![Stress](Stress%20%28-vonMises%29.png)
* **Factor of Safety Plot:**  
  ![FOS](FOS.png)

### Downloads & Files
* [SolidWorks CAD Part File (`A3 SolidWorks bar.SLDPRT`)](A3%20SolidWorks%20bar.SLDPRT)
* [SimulationXpress FEA PDF Report](A3%20SolidWorks%20bar-SimulationXpress%20Study-1.pdf)

---

## Section 4: Lessons Learned
* **Mistakes:** 1060 Alloy has a lower yield strength (4 ksi) than standard structural alloys like 6061-T6 Aluminum (40 ksi), which reduces the safety margin significantly.
* **Time Spent:** 6 hours total.

---
# 2157 Topic: Modify Design Parameters

## Parameter Modification & Predictions
* **Original Inputs:** d = 0.50 in, F = 500 lbf, L = 35.37 in, FOS = 1.57
* **Modified Inputs:** d = 0.60 in, F = 400 lbf
* **Prediction:** Length will increase, and Safety Factor (FOS) will increase.

## Calculations & Verification
* **Cross-Sectional Area (A):** Area = (pi * d^2) / 4 = (3.1416 * (0.60)^2) / 4 = 0.28274 sq in
* **New Designed Length (L):** L = (def * A * E) / F = (0.009 in * 0.28274 sq in * 10,007,603.90 psi) / 400 lbf = 63.67 in
* **New Nominal Stress (sigma):** Stress = F / A = 400 lbf / 0.28274 sq in = 1,414.7 psi (~1.41 ksi)
* **New Safety Factor (FOS):** FOS = Sy / Stress = 3,999.30 psi / 1,414.7 psi = 2.83

## Conclusion
* **Length:** Increased from 35.37 in to 63.67 in (+80%). Prediction was correct.
* **Safety Factor:** Increased from 1.57 to 2.83 (+80%). Prediction was correct.
* **Reasoning:** Increasing cross-sectional area and decreasing tensile load both reduce internal axial stress, raising the Factor of Safety. To maintain the target 0.009 in elongation under a smaller load and larger cross-section, the total length must increase proportionally.

### Modified Parameters Global Variables Table
![Modified Parameters](Modified%20Parameters.png)

## Resources & Links
1. [Parametric Modeling & FEA Videos](https://instructure.charlotte.edu/courses/272052/pages/parametric-modeling-and-fea-finite-element-analysis-videos?module_item_id=7950950)
2. AI used to format Markdown, embed images, and link CAD files.


---


