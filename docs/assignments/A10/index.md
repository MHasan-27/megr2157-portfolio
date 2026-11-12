# A10 – Lead Screw Translating System

**Team Members**  
- Mohammad Hasan (mhasan27@charlotte.edu)  
- Brayan Maldonado-Guzman (bmaldon3@charlotte.edu)  
- Candy Vasquez (cvasque6@charlotte.edu)

# Leadscrew Diameter: (Mohammad)

Part 1 (Leadscrew Diameter) using AISI 1018 Low-Carbon Steel (Sy = 370 MPa = 53,700 psi), formatted according to your assignment structure.

## 1.) Minimum Diameter (d) using Axial Stress

### a.) List all Knowns and Unknowns 

**Knowns:**
- Total required tensile load: F_total = 2 kN = 2000 N
- Number of parallel leadscrews: n = 2
- Safety factor: ns = 4
- Material: AISI 1018 Low-Carbon Steel (Yield strength Sy ≈ 370 MPa = 370 × 10^6 N/m²)

**Unknowns:**
- Force applied to each leadscrew: Fa
- Allowable axial stress: sigma_allow
- Minimum required root/minor diameter of each screw: dr

<img width="678" height="809" alt="image" src="https://github.com/user-attachments/assets/99e6f337-68e1-40e4-b13f-913b5e4ad59f" />
<img width="974" height="531" alt="image" src="https://github.com/user-attachments/assets/a1564001-76cc-46a8-9def-1def132790ff" />


## 2.) Range of Rotational Speed Given Linear Speed 

### a.) List Knowns and Unknowns 

**Knowns:**
- Minimum crosshead linear velocity: V_min = 1 mm/min
- Maximum crosshead linear velocity: V_max = 50 mm/min
- Standard chosen 1018 steel screw thread: 1/2"-10 Single-Start Acme Screw (McMaster-Carr Part 99030A005)
- Screw lead (travel distance per turn): L = 0.100 in/rev = 2.54 mm/rev

**Unknowns:**
- Minimum rotational speed: N_min (in RPM)
- Maximum rotational speed: N_max (in RPM)

<img width="777" height="1006" alt="image" src="https://github.com/user-attachments/assets/72e9a785-def2-4062-b0b1-b739a623e3fd" />


---

## 3.) Maximum Driving Torque per Screw for 2 kN Load 

### a.) List Knowns and Unknowns 

**Knowns:**
- Axial load per screw: Fa = 1000 N
- Nominal outside diameter: d = 0.500 in = 12.7 mm
- Pitch: p = 0.100 in ⇒ p = 2.54 mm
- Mean thread diameter: dm = d − p/2 = 12.7 − 1.27 = 11.43 mm = 0.01143 m
- Lead angle: tan lambda = L / (pi dm) = 2.54 / (pi × 11.43) ≈ 0.0707 ⇒ lambda ≈ 4.05°
- Acme thread flank angle: alpha = 14.5°
- Friction coefficient (steel screw on bronze nut, lubricated): mu ≈ 0.15
- Thrust collar friction radius (assuming collar mean diameter dc ≈ 15 mm = 0.015 m) & friction coefficient muc ≈ 0.12

**Unknowns:**
- Torque required to raise load (raise axial tension): TR

<img width="844" height="1093" alt="image" src="https://github.com/user-attachments/assets/2509760d-36f3-4eac-93ad-de800585c9f9" />


---

## 4.) Select the Leadscrew from Catalog Resources 

Based on the calculated minimum root diameter (dr ≥ 3.71 mm), structural rigidity requirements, and standard component availability from McMaster-Carr:

- **Selected Part:** 1/2"-10 Precision Right-Hand Acme Lead Screw
- **McMaster-Carr Part Number:** 99030A005 (3 ft length)
- **Material:** 1018 Low-Carbon Steel
- **Specifications:**
  - Major Diameter (d): 0.500 in (12.7 mm)
  - Minor/Root Diameter (dr): 0.387 in (9.83 mm) — Well above 3.71 mm minimum constraint
  - Lead / Travel per turn: 0.100 in (2.54 mm)
  - Thread Class: Acme Class 2C single-start

**Or; From LeadScrew**  
Acme Lead Screw, 1/2 – 10, RH, Steel  
Part Number: 59284

### Select a Nut and Flange: (Brayan)

**Roton Option:**
1. [Acme Threaded Mount Nut, 1/2 - 10, RH, Bronze](https://www.roton.com/product/acme-bronze-threaded-mount-nut-right-90222/) (Part No. 90222)
2. [Mounting Flange, .938 - 16 UN, Steel](https://www.roton.com/product/flange-steel-flange-89838/) (Part No. 89838)

**Or; (Same Alternative Parts from McMaster-Carr)**
1. [Precision Acme Externally Threaded Nut: 673 Bronze, 1/2"-10 Thread Size](https://www.mcmaster.com/95072A209/) (Part No. 95072A209 – Left Hand version used in cost table)
2. [Precision Acme Flange: Black-Oxide 1117 Carbon Steel, 15/16"-16 Thread](https://www.mcmaster.com/1329K102/) (Part No. 1329K102)

<img width="974" height="1261" alt="image" src="https://github.com/user-attachments/assets/d16d9d0b-42a1-4184-bcf8-bdf14a6c3d83" />


---
<img width="974" height="1010" alt="image" src="https://github.com/user-attachments/assets/c7d8eb66-1738-4162-87da-c8d630dac9fa" />

## Nut Analysis
<img width="974" height="904" alt="image" src="https://github.com/user-attachments/assets/86d2931f-ef2b-4880-9ab9-f62ad26107b3" />


---

## Design the Crosshead

### 1. Simple Beam Stress/Strength Analysis

**Knowns and Unknowns and FBD**

<img width="974" height="932" alt="image" src="https://github.com/user-attachments/assets/5aa46a87-314f-4ae0-b681-ab045af28c20" />
 
  **Symbolically and Numerical Solve the Unknown**
  
<img width="974" height="839" alt="image" src="https://github.com/user-attachments/assets/fc0b7a00-3259-4c7d-a31c-1b9c8985e4d3" />

---

### 2. Simple Beam Deflection Analysis 

**Crosshead Deflection Analysis**

<img width="853" height="640" alt="image" src="https://github.com/user-attachments/assets/032c3213-227a-4337-be46-4ef6d14f9ff0" />

<img width="844" height="548" alt="image" src="https://github.com/user-attachments/assets/31db75ba-855b-41a1-aa67-a3d0ca62a2a4" />

---

### 3. Multiview Paper Sketch of the Crosshead

*(Insert Multiview sketch image here)*

<img width="974" height="855" alt="image" src="https://github.com/user-attachments/assets/3881ebc4-9196-43fa-9a13-623c6aa8ec29" />


**Global Variables Setup:**

<img width="974" height="283" alt="image" src="https://github.com/user-attachments/assets/fb0ef6ba-700a-4a47-ae4c-8a9ea36549eb" />


- **Step 1 (Base Extrusion):** Sketch a 400 mm × 60 mm rectangle on the Front Plane and perform a Boss-Extrude to a depth of 35 mm to create the main solid crosshead body.

<img width="973" height="603" alt="image" src="https://github.com/user-attachments/assets/f57587a3-336f-4f9c-b7ee-3134189f1333" />


- **Step 2 (Leadscrew Clearance Holes):** Sketch two Ø14 mm circles spaced 300 mm apart (50 mm from each edge) and perform a Cut-Extrude through-all to create clearance holes for the leadscrews.

<img width="972" height="489" alt="image" src="https://github.com/user-attachments/assets/0f9c40be-6078-4aa4-a2bd-942f80609282" />


- **Step 3 (Flange Mounting Tapped Holes):** Use the Hole Wizard to add eight 1/4"-20 UNC tapped holes (4 around each leadscrew hole on a Ø53.086 mm bolt circle) to secure the bronze nut mounting flanges.

<img width="974" height="519" alt="image" src="https://github.com/user-attachments/assets/0a682e35-dc43-49c5-a589-c0744421168f" />


---

## Tabulating Costs: (Mohammad)

### McMaster-Carr Option

If your team prefers to order all components through McMaster-Carr using the integrated flange nut setup:

| Part No.   | Description                                                                                      | Req. Qty. | Order Qty. | Unit of Measure | Price  | Total    |
|------------|--------------------------------------------------------------------------------------------------|-----------|------------|-----------------|--------|----------|
| [1329K102](https://www.mcmaster.com/1329K102/) | Precision Acme Flange Black-Oxide 1117 Carbon Steel, 15/16"-16 Thread Size | 2 | 2 | Each | $67.13 | $134.26 |
| [99030A005](https://www.mcmaster.com/99030A005/) | 1018 Carbon Steel Precision Acme Lead Screw Right Hand, 1/2"-10 Thread Size, 3 Feet Long | 2 | 2 | Each | $18.72 | $37.44 |
| [95072A209](https://www.mcmaster.com/95072A209/) | Precision Acme Externally Threaded Nut Left Hand, 673 Bronze, 1/2"-10 Thread Size | 2 | 2 | Each | $37.61 | $75.22 |
| [5537T038](https://www.mcmaster.com/5537T038/) | T-Slotted Framing 6-Slot Rail, Silver, 80mm High, 40mm Wide, Solid, 1.5' Long | 2 | 2 | Each | $39.52 | $79.04 |
| [5537T46](https://www.mcmaster.com/5537T46/) | T-Slotted Framing Double 6-Slot Rail, Silver, 80mm High, 40mm Wide, Solid 4' Long | 2 | 2 | Each | $98.37 | $196.74 |
| **Total**  |                                                                                                  |           |            |                 |        | **$522.70** |

---

### Roton Part Option

| Item Number | Qty | Name                                                                                           | Cost/Item | Total Cost | Purchase Link |
|-------------|-----|------------------------------------------------------------------------------------------------|-----------|------------|---------------|
| 1           | 2   | [Acme Lead Screw, 1/2 - 10, RH, Steel](https://www.roton.com/family/acme-right-screws-and-nuts-7059284/) | $9.10 | $18.20 | Roton Part #59284 |
| 2           | 2   | [Acme Threaded Mount Nut, 1/2 - 10, RH, Bronze](https://www.roton.com/product/acme-bronze-threaded-mount-nut-right-90222/) | $23.57 | $47.14 | Roton Part #90222 |
| 3           | 2   | [Mounting Flange, .938 - 16 UN, Steel](https://www.roton.com/product/flange-steel-flange-89838/) | $49.63 | $99.26 | Roton Part #89838 |
| 4           | 1   | 80/20 T-Slot Framing System Profile: Rectangle, 40 Series, Smooth, Double, 3 m Lg, 80mm x 40mm | $270.09 | $270.09 | Grainger Model 40-4080-1M |
| **Total**   |     |                                                                                                |           | **$434.69** |               |
---

## Parametric Modeling & CAD Assembly (Brayan and Mohammad)

- **Crosshead (Designed):** Parametrically modeled in SOLIDWORKS using global variables (Crosshead Length, Crosshead Width, Height, Screw Spacing) so all dimensions automatically update together.
- **Leadscrews (Downloaded):** Downloaded standard 3D CAD models for two 1/2"-10 RH precision carbon steel Acme leadscrews from McMaster-Carr.
- **Nuts & Flanges (Downloaded):** Sourced CAD models for two precision bronze Acme nuts and steel mounting flanges directly from McMaster-Carr.
- **Frame (Downloaded):** Downloaded 40 Series 80/20 double t-slot aluminum framing CAD files to construct the rigid outer test frame.
- **Assembly Mates:** Mated the aluminum frame using rigid mates, fixed the leadscrews in place, and applied concentric and screw mates between the nuts, flanges, and crosshead to allow realistic vertical crosshead motion.

<img width="974" height="495" alt="image" src="https://github.com/user-attachments/assets/bef42e91-0abf-4a01-81f6-d618c17c893b" />


---

## Lessons Learned

**Engineering Lessons Learned:**

- **Power Screw Drivetrain:** Applied Shigley's power screw torque equations to relate rotational driving torque (T_max = 2.023 N·m) directly to the required 2 kN axial pulling load, accounting for thread and collar friction.
- **Deflection vs. Strength Sizing:** Learned that elastic deflection (delta ≤ 0.1 mm) drives the crosshead design rather than yield strength, requiring an increased height of 35 mm (up from the 14.74 mm strength minimum).
- **Component Sourcing & Interfaces:** Selected standard 1/2"-10 Acme leadscrews from catalog resources, ensuring the 9.83 mm minor diameter comfortably exceeded the calculated 3.71 mm stress limit.
- **Parametric Assembly Modeling:** Configured global variables in SOLIDWORKS (Crosshead Length, Crosshead Width, Height, Screw Spacing) to establish robust parametric links between the custom crosshead, leadscrews, nuts, and aluminum frame.

# For 2157 Students (Candy) 

## 1.) Finite Element Analysis

### a.) Model Setup

- Constrained the flange interface against the bottom surface of the crosshead where it is meant to be screwed in, then applied the 2 kN (2,000 N) loading directly center aligned with the crosshead.  
- This decision was made using Figure #1 of the assignment as a reference, as the grip is centered to the crosshead.  
- The flange was removed in the actual mesh test so it would not affect the result of the crosshead strength analysis.

<img width="975" height="265" alt="image" src="https://github.com/user-attachments/assets/57c891fa-81c6-4610-b529-2b01a88caf67" />

<img width="560" height="211" alt="image" src="https://github.com/user-attachments/assets/fe09ba8f-034b-4be7-81bd-7c759a403073" />

<img width="618" height="179" alt="image" src="https://github.com/user-attachments/assets/ca07552e-a52c-4f7d-9854-07115a671b73" />

<img width="598" height="248" alt="image" src="https://github.com/user-attachments/assets/99b93422-d31e-4a5c-8e79-a1d4e94e35b3" />

---

### b. & c.) Meshing, Verification & Report

Use a solid mesh with local refinement at stress raisers.  
Perform a mesh convergence check (at least two refinements) and report key metrics (max von Mises stress and max vertical deflection).




<img width="443" height="167" alt="image" src="https://github.com/user-attachments/assets/9c5692db-25bb-4b73-8d62-7d3210d6aece" /> <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/cb55c9fb-3618-4fe0-a532-75f16478beb1" />



<img width="402" height="182" alt="image" src="https://github.com/user-attachments/assets/71bb54bc-cdd6-48c5-8e66-eec9130d693e" /> <img width="527" height="156" alt="image" src="https://github.com/user-attachments/assets/de1d2677-be68-4424-8de0-6ac7c0589d12" />



<img width="387" height="173" alt="image" src="https://github.com/user-attachments/assets/26f34707-2650-4882-b9c2-cb8f1f269de2" /> <img width="549" height="187" alt="image" src="https://github.com/user-attachments/assets/3a73f858-c1d4-4da8-b0db-c703f8c64556" />



**Original Design Results**

Stress:

<img width="975" height="463" alt="image" src="https://github.com/user-attachments/assets/f1a615e1-8453-429a-868a-c610c44797c2" />

 Displacement:

<img width="975" height="381" alt="image" src="https://github.com/user-attachments/assets/a1cd108c-7c22-45dc-b279-9c2782291b14" />

Factor Of Safety: 

<img width="975" height="381" alt="image" src="https://github.com/user-attachments/assets/f3a0a32d-6168-4084-8c40-9f37e41c2479" />


| Metric                  | FEA TEST I (Coarse) | FEA TEST II (Medium/Default) | FEA TEST III (Fine) |
|-------------------------|---------------------|------------------------------|---------------------|
| Max Stress (N/m²)       | 9,254,784.00        | 8,848,740.00                 | 9,804,605.00        |
| Min. Safety Factor      | 30                  | 31                           | 28                  |
| Max Deflection (mm)     | 0.014899            | 0.015074                     | 0.015128            |

The medium mesh produces the lowest stress, while the fine mesh produces the highest. The maximum deflection stays somewhat consistent across all three tests.

The 2,000 N force is applied to the center of the crosshead and travels through the crosshead toward the flange, where it is fixed in place. Since the load is applied directly in the center, there should be little twisting. The small deflection results also show that the crosshead stays fairly stiff and does not bend much under the load. Overall, the crosshead appears to handle the applied force well with no major signs of bending or deformation.

#### i. Max Stress Convergence

**Coarse Mesh to Medium Mesh**  
Percentage Change = (|8,848,740 − 9,254,784| / 9,254,784) × 100  
Percentage Change = (406,044 / 9,254,784) × 100  
Percentage Change = 4.39%

**Medium Mesh to Fine Mesh**  
Percentage Change = (|9,804,605 − 8,848,740| / 8,848,740) × 100  
Percentage Change = (955,865 / 8,848,740) × 100  
Percentage Change = 10.80%

#### ii. Max Deflection Convergence

**Coarse Mesh to Medium Mesh**  
Percentage Change = (|0.015074 − 0.014899| / 0.014899) × 100  
Percentage Change = (0.000175 / 0.014899) × 100  
Percentage Change = 1.17%

**Medium Mesh to Fine Mesh**  
Percentage Change = (|0.015128 − 0.015074| / 0.015074) × 100  
Percentage Change = (0.000054 / 0.015074) × 100  
Percentage Change = 0.36%

|                        | Coarse to Medium | Medium to Fine |
|------------------------|------------------|----------------|
| Maximum Stress         | 4.39%            | 10.80%         |
| Maximum Deflection     | 1.17%            | 0.36%          |

---

### d.) Optimization Pass

The original design had a high Factor of Safety of 28, a maximum deflection of 0.015128 mm, and a peak stress of approximately 9.80 MPa. Since the design was already strong enough to handle the applied load, the main goal of optimization was to reduce the weight without affecting its strength.

To do this, pockets were added by removing material in the area between the two mounting holes. The pockets were placed on the same surface as the mounting holes rather than on the sides of the crosshead in order to keep the side walls intact and help maintain the bracket’s strength and stiffness. 2 mm fillets were also applied to the inside walls of the pockets. This helped smooth out sharp corners and reduce potential stress concentrations around the openings.

**Optimized Design Results**

Stress:  

<img width="975" height="377" alt="image" src="https://github.com/user-attachments/assets/5bfeb1db-cdbe-48d7-96ed-3b25cda7ed38" />

Deflection: 

<img width="975" height="365" alt="image" src="https://github.com/user-attachments/assets/d23a1a53-6d28-48cc-a0d7-7422db16b488" />

Factor of Safety:

<img width="975" height="233" alt="image" src="https://github.com/user-attachments/assets/3a027f87-856d-4d88-9e1e-e0127a93a74a" />

| Metric                  | FEA TEST I (Coarse) | FEA TEST II (Medium/Default) | FEA TEST III (Fine) |
|-------------------------|---------------------|------------------------------|---------------------|
| Max Stress (N/m²)       | 8,911,211.00        | 9,239,235.00                 | 9,118,962.00        |
| Min. Safety Factor      | 31                  | 30                           | 30                  |
| Max Deflection (mm)     | 0.017141            | 0.017124                     | 0.017157            |

#### i. Max Stress Convergence

**Coarse to Medium**  
Percentage Change = (|9,239,235 − 8,911,211| / 8,911,211) × 100  
Percentage Change = (328,024 / 8,911,211) × 100  
Percentage Change = 3.68%

**Medium to Fine**  
Percentage Change = (|9,118,962 − 9,239,235| / 9,239,235) × 100  
Percentage Change = (120,273 / 9,239,235) × 100  
Percentage Change = 1.30%

#### ii. Max Deflection Convergence

**Coarse to Medium**  
Percentage Change = (|0.017124 − 0.017141| / 0.017141) × 100  
Percentage Change = 0.10%

**Medium to Fine**  
Percentage Change = (|0.017157 − 0.017124| / 0.017124) × 100  
Percentage Change = 0.19%

The optimization was successful in reducing the maximum stress while maintaining a high Factor of Safety. The maximum stress decreased by 6.99%, and the Factor of Safety improved from 28 to 30. Although the maximum deflection increased by approximately 13.41%, it is still a very small 0.017157 mm.

These optimized mesh results show good convergence, with both stress and deflection changing by less than 5% between the medium and fine meshes. Since the main goal was weight reduction, this optimization reduced the weight from 4.9 lbs (2230 g) down to 4.7 lbs (2113 g).

 original:  

<img width="399" height="284" alt="image" src="https://github.com/user-attachments/assets/b6919f77-e154-4f45-9abe-2d6fc97729b1" />

 optimized:  

<img width="432" height="290" alt="image" src="https://github.com/user-attachments/assets/ec3b8df1-979e-46ad-a625-4b250f9ba955" />

---

## 2.)  Drawing of the crosshead

<img width="975" height="758" alt="image" src="https://github.com/user-attachments/assets/b30747da-2f88-49b1-b2ee-002128f38923" />


**Total Time Spent:**

- Calculations & Theoretical Sizing: 4 hours
- Catalog Research & Part Selection: 2 hours
- SOLIDWORKS Modeling & Assembly: 5 hours
- Documentation & Portfolio Write-Up: 3.5 hours
- For 2157 Students only: 5 hours
- **Total Time: 19.50 Hours**

## Download Link

- [A10 Assembly.SLDASM](./A10%20Assembly.SLDASM)
- [Crosshead.SLDPRT](./Crosshead.SLDPRT)
- [Crosshead optimized.SLDPRT](./Crosshead%20optimized.SLDPRT)
- [Crosshead drawing.SLDDRW](./Crosshead%20drawing.SLDDRW)
- [1329K102_Precision Acme Flange.SLDPRT](./1329K102_Precision%20Acme%20Flange.SLDPRT)
- [95072A209_Precision Acme Externally Threaded Nut.SLDPRT](./95072A209_Precision%20Acme%20Externally%20Threaded%20Nut.SLDPRT)
- [99030A005_1018 Carbon Steel Precision Acme Lead Screw(2).SLDPRT](./99030A005_1018%20Carbon%20Steel%20Precision%20Acme%20Lead%20Screw(2).SLDPRT)
- [5537T038_T-Slotted Framing.SLDPRT](./5537T038_T-Slotted%20Framing.SLDPRT)
- [5537T46_T-Slotted Framing.SLDPRT](./5537T46_T-Slotted%20Framing.SLDPRT)

