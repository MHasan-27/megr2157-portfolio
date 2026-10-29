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
![A 8-1](A%208-1.jpg)
![A 8-2](A%208-2.jpg)


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

![A 8-3](A%208-3.jpg)


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

![A 8-4](A%208-4.jpg)
![A 8-5](A%208-5.jpg)

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

![A 8-6](A%208-6.jpg)

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
# 3. Gearbox Housing Sketch & Fastening Method

The gearbox housing is designed as a two-piece split housing (Top Cover and Bottom Base) with a horizontal parting line aligned across the shaft centers.
![A 8-7](A%208-7.jpg)
## Fastening Method Selection & Justification

- **Selected Fasteners:** 4 Black-Oxide Alloy Steel Socket Head Screws, M3 × 0.5 mm Thread Size, 12 mm Long (McMaster-Carr 91290A500).
- **Selected Fastening Assembly:** Corner bolted connection through clearance holes in the Top Cover into heat-set brass threaded inserts (M3 × 0.5 mm) embedded into the Bottom Base.

### Comparison with Alternative (Snap-Fit)
- **Snap-Fit Joints:** While easy to assemble initially, repeated cycles lead to plastic fatigue, tab creep, and lost clamping force, which degrades gear mesh alignment over time.
- **Bolted Connection:** Four corner M3 bolts provide rigid, high-clamping force across the parting line, ensuring exact center distance (Cd) between the pinion (7880K19) and gear (7880K24).

### Justification
The high tensile strength (Class 12.9) of alloy steel M3 socket head screws guarantees that the housing halves stay aligned during high-speed rotation without loosening, while permitting infinite assembly and disassembly cycles.

---

# 4. CAD Model Generation & Parametric Workflow

## a. Parametric Modeling Strategy & Equations Setup

To ensure full design adaptability, all critical geometric features of the gearbox housing and assembly are driven by SolidWorks Global Variables (Tools > Equations).

### Primary Parameter Table (SolidWorks Equations Manager)

*(Insert Global Variables table here)*

### Derived Feature Equations in CAD Sketches
1. Center-to-Center Bore Spacing: = "Cd"
2. Input Journal Bearing Bore Diameter: = "Din" + 2 * "t"
3. Output Journal Bearing Bore Diameter: = "Dout" + 2 * "t"
4. Gear Cavity Clearance: = "Gout" + 0.125"

## b. McMaster-Carr Component Selection & File Imports

The following off-the-shelf CAD models were downloaded directly from McMaster-Carr to build the assembly:

**1. Input Pinion Gear (18T, 48 Pitch, Brass)**
- Part Number: 7880K19
- Specifications: Pressure Angle, Pitch Diameter, Bore, Brass

**2. Output Gear (48T, 48 Pitch, Brass)**
- Part Number: 7880K24
- Specifications: Pressure Angle, Pitch Diameter, Bore, Brass

**3. Input Shaft Journal Sleeve Bearing**
- Part Number: 6391K111
- Specifications: SAE 841 Oil-Embedded Bronze, ID × OD × Length

**4. Output Shaft Journal Sleeve Bearing**
- Part Number: 6391K131 (or 6391K136)
- Specifications: SAE 841 Oil-Embedded Bronze, ID × OD × Length

**5. Housing Fasteners**
- Part Number: 91290A500
- Specifications: Black-Oxide Alloy Steel Socket Head Screws, M3 × 0.5 mm Thread, 12 mm Length

## c. Solid Model Housing Generation & Assembly Workflow

### Housing Design Steps
1. **Base Enclosure:** Extruded a rectangular housing base using high-performance ABS-PC (Acrylonitrile Butadiene Styrene / Polycarbonate) for high heat resistance and mechanical strength.
2. **Internal Gear Pocket Cut:** Cut-extruded an elliptical internal cavity providing a minimum wall clearance around the meshing gear and pinion.
3. **Parting Line Split:** Split the main block horizontally through the centerlines of both shaft bores, creating a Top Housing Cover and Bottom Housing Base.
4. **Bearing Seat Bores:** Added counterbore pockets at the split plane to hold the outer diameters of the oil-embedded bronze sleeve bearings.
5. **Fastener Mounting Holes:** Added 4 corner clearance holes on the top cover and 4 tapped blind holes on the bottom base for the socket head cap screws.

### Assembly Mating (.SLDASM)
1. **Fixed Base:** Anchored the Bottom Housing Base.
2. **Concentric Mates:** Mated the sleeve bearings and rotary shafts into their respective housing bore pockets.
3. **Coincident Mates:** Positioned the pinion and output gear along the shafts so their face centers align perfectly in the mid-plane of the housing cavity.
4. **Mechanical Gear Mate:** Applied a Gear Mate between the pinion and output gear pitch diameters using the exact teeth ratio (18:48), enabling dynamic mouse-driven rotation in CAD.    



# 5. Lessons Learned & Reflection

1. **Importance of Symbolic Algebraic Derivations Before Calculation**  
   Lesson: Solving equations algebraically before inserting numerical values made it straightforward to trace units and prevent conversion errors (such as converting rpm to rad/s or calculating horsepower using the correct empirical constant).

2. **Understanding Material Limits (PV Factor vs. Pure Load)**  
   Lesson: Initially, non-metallic polymers like Acetal or Nylon seemed like good choices for plain bearings. However, evaluating the PV factor revealed that the high input shaft speed generates a PV demand that exceeds polymer continuous limits. Selecting self-lubricating SAE 841 Bronze was necessary to safely handle the load.

3. **Parametric SolidWorks Equations Save Iteration Time**  
   Lesson: Driving the center distance (Cd) through global variables (="Gin" + "Gout") / 2 ensured that if gear pitch diameters were updated, the housing bore locations automatically adjusted without breaking downstream sketch relations.

4. **Tolerancing Real-World Sleeve Bearings & Fasteners**  
   Lesson: Designing press-fit pockets for sleeve bearings requires tight tolerances (RC5 running fit for shafts and press-fit hole tolerances for sleeves) so that pressing the bearing into the plastic housing does not collapse the internal clearance or lock up the shaft.

5. **Assembly & Mating Realities**  
   Lesson: Aligning 3D teeth manually in SolidWorks before applying a Mechanical Gear Mate is critical to prevent visually overlapping teeth during motion simulation.
