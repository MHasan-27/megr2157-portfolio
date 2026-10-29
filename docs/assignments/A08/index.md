## A8 : Gearbox Design

# 1. Design of the Shafts

## a. Input Shaft (Power-Transmission)

### i. Knowns and Unknowns

**Knowns:**
- Output Torque (Tout): 1.25 in-lbf
- Output Speed (Nout): 1100 RPM
- Gear Ratio (Ngear:Npinion): 24:9 (48 teeth : 18 teeth)
- Input Speed (Nin): 1100 × (24/9) ≈ 2933.33 RPM
- Input Torque (Tin): 1.25 × (9/24) = 0.46875 in-lbf
- Input Shaft Diameter (din): 0.125 in
- Input Shaft Length (Lin): 1.0 in
- Pinion Material: Brass (McMaster-Carr 7880K19)

**Unknowns:**
- Transmitted Horsepower (Pin)
- Allowable Horsepower capacity (Pallow,in)
- Minimum required diameter (Dreq,in)
- Maximum torsional shear stress (τin)
- Adequacy of din = 0.125 in

### iii. Equations & Algebraic Modeling

![A 8-1](A%208-1.jpg)
![A 8-2](A%208-2.jpg)

### v. Conclusion & Recommendation

- **Verdict:** Sufficient
- **Explanation:** The minimum required diameter (Dreq,in ≈ 0.065 in) is significantly smaller than the provided shaft diameter (din = 0.125 in). Furthermore, the power transmitted (0.022 hp) is well within the shaft’s allowable power capacity (0.1508 hp).
- **Recommendation:** din = 0.125 in is fully adequate; no diameter increase is required.

---

## b. Output Shaft (Short Shaft)

### i. Knowns and Unknowns

**Knowns:**
- Output Torque (Tout): 1.25 in-lbf
- Output Speed (Nout): 1100 RPM
- Output Shaft Diameter (dout): 0.250 in
- Output Shaft Length (Lout): 1.0 in
- Output Gear Material: Brass (McMaster-Carr 7880K24)

**Unknowns:**
- Transmitted Horsepower (Pout)
- Allowable Horsepower capacity (Pallow,out)
- Minimum required diameter (Dreq,out)
- Maximum torsional shear stress (τout)
- Adequacy of dout = 0.250 in

### iii. Equations & Algebraic Modeling

![A 8-3](A%208-3.jpg)

### v. Conclusion & Recommendation

- **Verdict:** Sufficient
- **Explanation:** The required minimum diameter (Dreq,out ≈ 0.09125 in) is far below the actual shaft diameter (dout = 0.250 in). The allowable power capacity (0.4523 hp) also easily exceeds the transmitted power (0.022 hp).
- **Recommendation:** dout = 0.250 in is fully adequate; no diameter change is required.

---

# 2. Design Journal Bearings

## a. Size, Length, Pressure, Velocity, and PV Rating

### i. Knowns and Unknowns

**Knowns:**
- Gear Ratio: 24:9 (48 teeth : 18 teeth)
- System Power (P): 0.022 hp
- Input Torque (Tin): 0.46875 in-lbf
- Output Torque (Tout): 1.25 in-lbf
- Input Speed (Nin): 2933.33 RPM
- Output Speed (Nout): 1100 RPM
- Input Shaft Diameter (din): 0.125 in
- Output Shaft Diameter (dout): 0.250 in
- Shaft Lengths (Lshaft): 1.0 in
- Gear Pitch Diameters: dp,gear = 1.0 in (7880K24), dp,pinion = 0.375 in (7880K19)
- Pressure Angle (φ): 20°
- Selected Journal Bearing Length (L): 0.250 in
- Fit / Clearance Class: RC 5 Running Fit clearance of 0.001 in

**Unknowns:**
- Bearing load (Fb)
- Journal bearing projected area (A)
- Journal bearing pressure (P), velocity (V), and PV rating
- Journal bearing wall thickness
- Material selection based on pressure, velocity, and PV rating

### iii. Equations & Algebraic Modeling

![A 8-4](A%208-4.jpg)
![A 8-5](A%208-5.jpg)

### v. Material Selection Using Lecture Table 4

- **Selected Material:** Porous Bronze (Oil-Embedded SAE 841 Bronze)
- **Table 4 Material Limits (Machinery’s Handbook):**
  - Load Capacity (Plimit): 4,500 psi
  - Max Surface Speed (Vmax): 1,500 ft/min
  - PV Limit: 50,000 psi·ft/min
- **Justification:** The governing input shaft PV demand (8,172.30 psi·ft/min) exceeds non-metallic limits like Acetal (3,000 ft/min). Oil-embedded SAE 841 Porous Bronze satisfies all pressure, velocity, and PV requirements with a factor of safety FS > 6.

---

## b. Design the Thickness of the Journal Bearing

### i. Knowns and Unknowns

**Knowns:**
- Resultant Bearing Load (Fb): 2.66 lbf
- Input Shaft Diameter / Bearing Inner Diameter (din): 0.125 in (1/8 in)
- Output Shaft Diameter / Bearing Inner Diameter (dout): 0.250 in (1/4 in)
- Bearing Length (L): 0.250 in
- Bearing Material: Oil-Embedded SAE 841 Porous Bronze
- Allowable Tensile/Compressive Strength of SAE 841 Bronze (σallow): ≈ 10,000 psi to 18,000 psi
- Allowable Shear Stress (τallow): ≈ 0.577 × σallow ≈ 5,770 psi
- Standard Commercial Wall Thickness (tstd): 0.0625 in (1/16 in) for 1/8 in and 1/4 in sleeve bearings

**Unknowns:**
- Tangential hoop stress (σt) and radial stress (σr) due to press fit / internal load
- Minimum required wall thickness (treq) for mechanical integrity under radial bearing load
- Outer diameter of the journal bearings (Dout,b)

### iii. Equations & Algebraic Modeling

![A 8-6](A%208-6.jpg)

---

## c. McMaster-Carr Component Selection

The following off-the-shelf McMaster-Carr Sleeve Bearings made from self-lubricating, oil-embedded SAE 841 porous bronze satisfy all dimensional, wall thickness, and PV requirements:

**1. Input Shaft Journal Bearing (1/8 in ID × 1/4 in OD × 1/4 in L)**
- Component Name: SAE 841 Oil-Embedded Bronze Sleeve Bearing
- McMaster-Carr Part Number: 6391K111
- Dimensions: 0.126 in ID × 0.252 in OD × 0.250 in Length (1/16 in Wall Thickness)

**2. Output Shaft Journal Bearing (1/4 in ID × 3/8 in OD × 3/8 in L trimmed / 1/4 in L)**
- Component Name: SAE 841 Oil-Embedded Bronze Sleeve Bearing
- McMaster-Carr Part Number: 6391K136
- Dimensions: 0.251 in ID × 0.377 in OD × 0.375 in Length (or 6391K131 for 1/4 in length)

---

# 3. Gearbox Housing Sketch & Fastening Method

The gearbox housing is designed as a two-piece split housing (Top Cover and Bottom Base) with a horizontal parting line aligned across the shaft centers.

![A 8-7](A%208-7.jpg)

## Fastening Method Selection & Justification

- **Selected Fasteners:** 4 × Black-Oxide Alloy Steel Socket Head Screws, M3 × 0.5 mm Thread Size, 12 mm Long (McMaster-Carr 91290A500)
- **Selected Fastening Assembly:** Corner bolted connection through clearance holes in the Top Cover into heat-set brass threaded inserts (M3 × 0.5 mm) embedded into the Bottom Base

### Comparison with Alternative (Snap-Fit)
- **Snap-Fit Joints:** While easy to assemble initially, repeated cycles lead to plastic fatigue, tab creep, and lost clamping force, which degrades gear mesh alignment over time.
- **Bolted Connection:** Four corner M3 bolts provide rigid, high-clamping force across the parting line, ensuring exact center distance (Cd = 0.6875 in) between the 18T pinion (7880K19) and 48T gear (7880K24).

### Justification
The high tensile strength (170,000 psi, Class 12.9) of alloy steel M3 socket head screws guarantees that the housing halves stay aligned during high-speed rotation (2933.33 RPM) without loosening, while permitting infinite assembly and disassembly cycles.

---

# 4. CAD Model Generation & Parametric Workflow

## a. Parametric Modeling Strategy & Equations Setup

To ensure full design adaptability, all critical geometric features of the gearbox housing and assembly are driven by SolidWorks Global Variables (Tools > Equations).

### Derived Feature Equations in CAD Sketches
1. Center-to-Center Bore Spacing: = "Cd" (0.6875 in)
2. Input Journal Bearing Bore Diameter: = "Din" + 2 * "t" (0.250 in)
3. Output Journal Bearing Bore Diameter: = "Dout" + 2 * "t" (0.375 in)
4. Gear Cavity Clearance: = "Gout" + 0.125" (1.125 in)

## b. McMaster-Carr Component Selection & File Imports

The following off-the-shelf CAD models were downloaded directly from McMaster-Carr to build the assembly:

**1. Input Pinion Gear (18T, 48 Pitch, Brass)**
- Part Number: 7880K19
- Specifications: 20° Pressure Angle, 3/8 in Pitch Diameter, 1/8 in Bore, Brass

**2. Output Gear (48T, 48 Pitch, Brass)**
- Part Number: 7880K24
- Specifications: 20° Pressure Angle, 1.0 in Pitch Diameter, 1/4 in Bore, Brass

**3. Input Shaft Journal Sleeve Bearing**
- Part Number: 6391K111
- Specifications: SAE 841 Oil-Embedded Bronze, 1/8 in ID × 1/4 in OD × 1/4 in Length

**4. Output Shaft Journal Sleeve Bearing**
- Part Number: 6391K131 (or 6391K136)
- Specifications: SAE 841 Oil-Embedded Bronze, 1/4 in ID × 3/8 in OD × 1/4 in Length

**5. Housing Fasteners**
- Part Number: 91290A500
- Specifications: Black-Oxide Alloy Steel Socket Head Screws, M3 × 0.5 mm Thread, 12 mm Length

## c. Solid Model Housing Generation & Assembly Workflow

### Housing Design Steps
1. **Base Enclosure:** Extruded a rectangular housing base (2.50 in × 2.00 in × 0.75 in) using high-performance ABS-PC (Acrylonitrile Butadiene Styrene / Polycarbonate) for high heat resistance and mechanical strength.
2. **Internal Gear Pocket Cut:** Cut-extruded an elliptical internal cavity providing a minimum of 0.0625 in wall clearance around the meshing 1.0 in gear and 0.375 in pinion.
3. **Parting Line Split:** Split the main block horizontally through the centerlines of both shaft bores, creating a Top Housing Cover and Bottom Housing Base.
4. **Bearing Seat Bores:** Added counterbore pockets at the split plane to hold the 0.250 in and 0.375 in outer diameters of the oil-embedded bronze sleeve bearings.
5. **Fastener Mounting Holes:** Added 4 corner clearance holes (3.40 mm diameter) on the top cover and 4 tapped blind holes (M3 × 0.5 mm) on the bottom base for the socket head cap screws.

### Assembly Mating (.SLDASM)
1. **Fixed Base:** Anchored the Bottom Housing Base.
2. **Concentric Mates:** Mated the sleeve bearings and rotary shafts into their respective housing bore pockets.
3. **Coincident Mates:** Positioned the pinion and output gear along the shafts so their face centers align perfectly in the mid-plane of the housing cavity.
4. **Mechanical Gear Mate:** Applied a Gear Mate between the pinion and output gear pitch diameters using the exact teeth ratio (18:48), enabling dynamic mouse-driven rotation in CAD.

---

# 5. Lessons Learned & Reflection

1. **Importance of Symbolic Algebraic Derivations Before Calculation**  
   Lesson: Solving equations algebraically before inserting numerical values made it straightforward to trace units and prevent conversion errors (such as converting RPM to rad/s or calculating horsepower using the 63,025 empirical constant).

2. **Understanding Material Limits (PV Factor vs. Pure Load)**  
   Lesson: Initially, non-metallic polymers like Acetal or Nylon seemed like good choices for plain bearings. However, evaluating the PV factor revealed that the high input shaft speed (2933.33 RPM) generates a PV demand of 8,172 psi·ft/min, exceeding polymer continuous limits (3,000 ft/min). Selecting self-lubricating SAE 841 Bronze was necessary to safely handle the load.

3. **Parametric SolidWorks Equations Save Iteration Time**  
   Lesson: Driving the center distance (Cd = 0.6875 in) through global variables (="Gin" + "Gout") / 2 ensured that if gear pitch diameters were updated, the housing bore locations automatically adjusted without breaking downstream sketch relations.

4. **Tolerancing Real-World Sleeve Bearings & Fasteners**  
   Lesson: Designing press-fit pockets for sleeve bearings requires tight tolerances (RC 5 running fit for shafts and press-fit hole tolerances for sleeves) so that pressing the bearing into the plastic housing does not collapse the internal clearance or lock up the shaft.

5. **Assembly & Mating Realities**  
   Lesson: Aligning 3D teeth manually in SolidWorks before applying a Mechanical Gear Mate is critical to prevent visually overlapping teeth during motion simulation.
