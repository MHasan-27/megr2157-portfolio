## A8: Gearbox Design

# 1. Design of the Shafts

## a. Input Shaft (Power-Transmission)

### i. Knowns and Unknowns

**Knowns:**
- Output Torque (To):  
- Output Speed (no):  
- Gear Ratio (i):  
- Input Speed (ni):  
- Input Torque (Ti):  
- Input Shaft Diameter (di):  
- Input Shaft Length (Li):  
- Pinion Material: Brass (McMaster-Carr 7880K19)

**Unknowns:**
- Transmitted Horsepower (HP)
- Allowable Horsepower capacity (HP_allow)
- Minimum required diameter (d_min)
- Maximum torsional shear stress (tau_max)
- Adequacy of di

### iii. Equations & Algebraic Modeling

*(Equations and calculations to be inserted here in plain text)*

### v. Conclusion & Recommendation

- **Verdict:** Sufficient.
- **Explanation:** The minimum required diameter (d_min) is significantly smaller than the provided shaft diameter (di). Furthermore, the power transmitted (HP) is well within the shaft’s allowable power capacity (HP_allow).
- **Recommendation:** di is fully adequate; no diameter increase is required.

---

## b. Output Shaft (Short Shaft)

### i. Knowns and Unknowns

**Knowns:**
- Output Torque (To):  
- Output Speed (no):  
- Output Shaft Diameter (do):  
- Output Shaft Length (Lo):  
- Output Gear Material: Brass (McMaster-Carr 7880K24)

**Unknowns:**
- Transmitted Horsepower (HP)
- Allowable Horsepower capacity (HP_allow)
- Minimum required diameter (d_min)
- Maximum torsional shear stress (tau_max)
- Adequacy of do

### iii. Equations & Algebraic Modeling

*(Equations and calculations to be inserted here in plain text)*

### v. Conclusion & Recommendation

- **Verdict:** Sufficient.
- **Explanation:** The required minimum diameter (d_min) is far below the actual shaft diameter (do). The allowable power capacity (HP_allow) also easily exceeds the transmitted power (HP).
- **Recommendation:** do is fully adequate; no diameter change is required.

# 2. Design Journal Bearings

## a. Size, Length, Pressure, Velocity, and PV Rating

### i. Knowns and Unknowns

**Knowns:**
- Gear Ratio (i):  
- System Power (HP):  
- Input Torque (Ti):  
- Output Torque (To):  
- Input Speed (ni):  
- Output Speed (no):  
- Input Shaft Diameter (di):  
- Output Shaft Diameter (do):  
- Shaft Lengths (L):  
- Gear Pitch Diameters:  (7880K24),  (7880K19)
- Pressure Angle (φ):  
- Selected Journal Bearing Length (L):  
- Fit / Clearance Class: RC 5 Running Fit clearance of  

**Unknowns:**
- Bearing load (W)
- Journal bearing projected area (A)
- Journal bearing pressure (P), velocity (V), and PV rating
- Journal bearing wall thickness
- Material selection based on pressure, velocity, and PV rating

### iii. Equations & Algebraic Modeling

*(Equations and calculations to be inserted here in plain text)*

### v. Material Selection Using Lecture Table 4

- **Selected Material:** Porous Bronze (Oil-Embedded SAE 841 Bronze)
- **Table 4 Material Limits (Machinery's Handbook):**
  - Load Capacity (P):  
  - Max Surface Speed (V):  
  - PV Limit:  
- **Justification:** The governing input shaft PV demand ( ) exceeds non-metallic limits like Acetal ( ). Oil-embedded SAE 841 Porous Bronze satisfies all pressure, velocity, and PV requirements with a factor of safety.

---

## b. Design the Thickness of the Journal Bearing

### i. Knowns and Unknowns

**Knowns:**
- Resultant Bearing Load (W):  
- Input Shaft Diameter / Bearing Inner Diameter (di):  ( )
- Output Shaft Diameter / Bearing Inner Diameter (do):  ( )
- Bearing Length (L):  
- Bearing Material: Oil-Embedded SAE 841 Porous Bronze
- Allowable Tensile/Compressive Strength of SAE 841 Bronze (σ_allow):  to  
- Allowable Shear Stress (τ_allow):  
- Standard Commercial Wall Thickness (t):  ( ) for  and  sleeve bearings

**Unknowns:**
- Tangential hoop stress (σ_t) and radial stress (σ_r) due to press fit / internal load
- Minimum required wall thickness (t_min) for mechanical integrity under radial bearing load
- Outer diameter of the journal bearings (Do)

### iii. Equations & Algebraic Modeling

*(Equations and calculations to be inserted here in plain text)*

---

## c. McMaster-Carr Component Selection

The following off-the-shelf McMaster-Carr Sleeve Bearings made from self-lubricating, oil-embedded SAE 841 porous bronze satisfy all dimensional, wall thickness, and PV requirements:

**1. Input Shaft Journal Bearing ( ID ×  OD × L):**
- Component Name: SAE 841 Oil-Embedded Bronze Sleeve Bearing
- McMaster-Carr Part Number: 6391K111
- Dimensions:  ID ×  OD ×  Length (  Wall Thickness)

**2. Output Shaft Journal Bearing ( ID ×  OD × L trimmed /  L):**
- Component Name: SAE 841 Oil-Embedded Bronze Sleeve Bearing
- McMaster-Carr Part Number: 6391K136
- Dimensions:  ID ×  OD ×  Length (or 6391K131 for  length)
    
