# A10 – Lead Screw Translating System

# Leadscrew Diameter: (Mohammad)

Part 1 (Leadscrew Diameter) using AISI 1018 Low-Carbon Steel (Sy = 370 MPa = 53,700 psi), formatted according to your assignment structure.

## 1.) Minimum Diameter (d) using Axial Stress (Mohammad)

### a.) List all Knowns and Unknowns (0.5 pts)

**Knowns:**
- Total required tensile load: F_total = 2 kN = 2000 N
- Number of parallel leadscrews: n = 2
- Safety factor: ns = 4
- Material: AISI 1018 Low-Carbon Steel (Yield strength Sy ≈ 370 MPa = 370 × 10^6 N/m²)

**Unknowns:**
- Force applied to each leadscrew: Fa
- Allowable axial stress: sigma_allow
- Minimum required root/minor diameter of each screw: dr

*(Insert FBD / handwritten notes image here)*

### b.) FBD

*(Insert FBD image here)*

### c.) Symbolic Solve

sigma_allow = Sy / SF

sigma = F_screw / Ar = 4 F_screw / (pi d²)

sigma ≤ sigma_allow

4 F_screw / (pi d²) ≤ Sy / SF

dr ≥ sqrt( 4 F_screw * SF / (pi * Sy) )

### d.) Numerical Solve

sigma_allow = (370 × 10^6 N/m²) / 4 = 92.5 × 10^6 N/m²

dr ≥ sqrt( 4 (1000) * 4 / (pi * 370 × 10^6) )

dr ≥ 0.00371 m ≈ 3.71 mm ≈ 0.146 in

---

## 2.) Range of Rotational Speed Given Linear Speed (10 pts)

### a.) List Knowns and Unknowns (0.5 pts)

**Knowns:**
- Minimum crosshead linear velocity: V_min = 1 mm/min
- Maximum crosshead linear velocity: V_max = 50 mm/min
- Standard chosen 1018 steel screw thread: 1/2"-10 Single-Start Acme Screw (McMaster-Carr Part 99030A005)
- Screw lead (travel distance per turn): L = 0.100 in/rev = 2.54 mm/rev

**Unknowns:**
- Minimum rotational speed: N_min (in RPM)
- Maximum rotational speed: N_max (in RPM)

*(Insert rotational speed FBD / handwritten notes image here)*

### Symbolic Solve

Linear velocity = V  
Rotational speed = omega or N  

V = omega * L  →  omega = V / L  

omega_min = V_min / L  
omega_max = V_max / L  

### Numerical Solve

N_min = V_min / L = 1 mm/min / 2.54 mm/rev ≈ 0.394 RPM  

N_max = V_max / L = 50 mm/min / 2.54 mm/rev ≈ 19.69 RPM  

---

## 3.) Maximum Driving Torque per Screw for 2 kN Load (10 pts)

### a.) List Knowns and Unknowns (0.5 pts)

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

*(Insert torque FBD / handwritten notes image here)*

### Symbolic Solve

T_thread = (Fa * dm / 2) * [ (mu sec alpha + tan lambda) / (1 − mu sec alpha * tan lambda) ]

Tc = (Fa * muc * dc) / 2

T_total = T_thread + Tc

### Numerical Solve

mu sec(14.5°) = 0.15 * sec(14.5°) ≈ 0.1548 (approx 0.124 in source notes)

tan lambda = 0.0707

T_thread ≈ 1.123 N·m

Tc ≈ 0.900 N·m

T_max = 1.123 + 0.900 = 2.023 N·m ≈ 17.9 in·lbf

---

## 4.) Select the Leadscrew from Catalog Resources (5 pts)

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

1. Acme Threaded Mount Nut, 1/2 - 10, RH, Bronze  
2. Mounting Flange, .938 - 16 UN, Steel

**Or; (Same Alternative Parts from McMaster)**  
1. Precision Acme Externally Threaded Nut: 673 Bronze, 1/2"-10 Thread Size  
2. Precision Acme Flange: Black-Oxide 1117 Carbon Steel, 15/16"-16 Thread

*(Insert product images / catalog screenshots here)*

---

## Nut Analysis

**Knowns:**  
Bronze Nut Roton 90222  
Mounting Flange Roton 89838  
Thread 1/2 - 10 RH  
Pitch (p) 2.54 mm  
Axial load per nut (F) 1000 N  
SF 4  
Operating load rating 1250 lbf  
Nut static load rating 4000 lbf

**Unknowns:**  
Engaged Threads  
Bearing Stress  
Bending Stress

F_design = SF(F) = 4(1000) = 4000 N  
F_rated = 1250(4.44822) = 5560.3 N

*(Insert Nut FBD image here)*

### Nut Analysis Calculations

F = 2000 / 2 = 1000 N per nut, SF = 4, P = 2.54 mm  
d_pit = 12.7 − 2.54/2 = 11.43 mm  
Le = 19.05, Sy = 125 MPa  

nt = Le / P  
sigma_b = 2F / (pi * d_pit * nt * P)  
M = Fb / 4  
Z = nt * (P/2)^2 * pi * P * d_min / 6  

d_min = d − P  
sigma_allow = Sy / SF  

nt = 19.05 / 2.54 = 7.5  
d_min = 12.7 − 2.54 = 10.16 mm  

sigma_b = 2(1000) / (pi * 11.43 * 7.5 * 2.54) = 2.92 MPa  
sigma_bend = 6(1000) / (7.5 * pi * 10.16 * 2.54) = 9.87 MPa  
sigma_allow = 125 / 4 = 31.25 MPa  

9.87 < 31.25  
n = 125 / 9.87 = 12.7 > 4

---

## Design the Crosshead

### 1. Simple Beam Stress/Strength Analysis

**Knowns and Unknowns and FBD**

*(Insert Crosshead FBD image here)*

**Knowns:**  
Center load (P) = 2000 N  
SF = 4  
Max deflection = 0.1 mm  
Each nut = 1000 N  
Screw Center - Center (L) = 300 mm  
Crosshead width (b) = 60 mm  
Crosshead vertical height (h) = ?  

sigma_max = ? , delta_max = ?

ΣMB = 0 → RB = P/2 = 1000 N ↑  
ΣFy = 0 → RA = 1000 N ↑  
M_max = RA * L / 2 = P L / 4 = 2000 * 300 / 4 = 150,000 N·mm

### Symbolic Solution – Crosshead

M_max = P L / 4  
I = b h³ / 12  
C = h / 2  

sigma_max = M_max * C / I → 3 P L / (2 b h²)  

sigma_max ≤ Sy / SF  
3 P L / (2 b h²) ≤ Sy / SF  

h_min,strength = sqrt( 3 P L * SF / (2 b Sy) )

### Numerical Solution Using 6061-T6 aluminum Sy = 276 MPa

sigma_allow = Sy / SF = 276 / 4 = 69 MPa  

h_min = sqrt( 3 * 2000 * 300 * 4 / (2 * 60 * 276) ) = 14.74 mm

---

### 2. Simple Beam Deflection Analysis (10 pts)

**Crosshead Deflection Analysis**

E = 68900 N/mm²  
delta_allow = 0.1 mm  
RA = 1000  
RB = 1000  

delta_max = P L³ / (48 E I)  
I = b h³ / 12  

h_min,deflection = [ P L³ / (4 E b delta_allow) ]^(1/3) ≈ 31.96 mm  

h_min,strength = 14.74 mm  
h_min,deflection = 31.96 mm  

Selected: b = 60 mm, h = 35 mm  

I = b h³ / 12 = 60 * (35)³ / 12 = 214,375 mm⁴  

sigma_max = M_max * C / I = 150000 * (35/2) / 214375 ≈ 12.24 MPa  

N = Sy / sigma_max = 276 / 12.24 ≈ 22.54 > 4  

delta_max = P L³ / (48 E I) = 2000 * (300)³ / (48 * 68900 * 214375) ≈ 0.0762 mm

---

### 3. Multiview Paper Sketch of the Crosshead

*(Insert Multiview sketch image here)*

**Flange Details**  
Outside = Ø 66.04  
Bolt Circle = Ø53.086  
4-flange holes = Ø6.756  
Hole angles: 45°, 135°, 225°, 315°  
8 × 1/4"-20 UNC Tapped Holes  
12.7 mm Thread Depth  
4 holes equally spaced on Ø53.086

**Global Variables Setup:**

*(Insert Global Variables screenshot here)*

- **Step 1 (Base Extrusion):** Sketch a 400 mm × 60 mm rectangle on the Front Plane and perform a Boss-Extrude to a depth of 35 mm to create the main solid crosshead body.

*(Insert Step 1 CAD screenshot here)*

- **Step 2 (Leadscrew Clearance Holes):** Sketch two Ø14 mm circles spaced 300 mm apart (50 mm from each edge) and perform a Cut-Extrude through-all to create clearance holes for the leadscrews.

*(Insert Step 2 CAD screenshot here)*

- **Step 3 (Flange Mounting Tapped Holes):** Use the Hole Wizard to add eight 1/4"-20 UNC tapped holes (4 around each leadscrew hole on a Ø53.086 mm bolt circle) to secure the bronze nut mounting flanges.

*(Insert Step 3 CAD screenshot here)*

---

## Tabulating Costs: (Mohammad)

### McMaster-Carr Option

If your team prefers to order all components through McMaster-Carr using the integrated flange nut setup:

| Part No.   | Description                                                                 | Req. Qty. | Order Qty. | Unit of Measure | Price   | Total    |
|------------|-----------------------------------------------------------------------------|-----------|------------|-----------------|---------|----------|
| 1329K102   | Precision Acme Flange Black-Oxide 1117 Carbon Steel, 15/16"-16 Thread Size | 2         | 2          | Each            | $67.13  | $134.26  |
| 99030A005  | 1018 Carbon Steel Precision Acme Lead Screw Right Hand, 1/2"-10 Thread Size, 3 Feet Long | 2 | 2 | Each | $18.72 | $37.44 |
| 95072A209  | Precision Acme Externally Threaded Nut Left Hand, 673 Bronze, 1/2"-10 Thread Size | 2 | 2 | Each | $37.61 | $75.22 |
| 5537T038   | T-Slotted Framing 6-Slot Rail, Silver, 80mm High, 40mm Wide, Solid, 1.5' Long | 2 | 2 | Each | $39.52 | $79.04 |
| 5537T46    | T-Slotted Framing Double 6-Slot Rail, Silver, 80mm High, 40mm Wide, Solid 4' Long | 2 | 2 | Each | $98.37 | $196.74 |
| **Total**  |                                                                             |           |            |                 |         | **$522.70** |

### Roton Part Option

| Item Number | Qnt | Name                                                                 | Cost/Item | Total Cost | Purchase Link              |
|-------------|-----|----------------------------------------------------------------------|-----------|------------|----------------------------|
| 1           | 2   | Acme Lead Screw, 1/2 - 10, RH, Steel                                 | $9.10     | $18.20     | Roton Part #59284          |
| 2           | 2   | Acme Threaded Mount Nut, 1/2 - 10, RH, Bronze                        | $23.57    | $47.14     | Roton Part #90222          |
| 3           | 2   | Mounting Flange, .938 - 16 UN, Steel                                 | $49.63    | $99.26     | Roton Part #89838          |
| 4           | 1   | 80/20 T-Slot Framing System Profile: Rectangle, 40 Series, Smooth, Double, 3 m Lg, 80mm x 40mm | $270.09 | $270.09 | Grainger Model 40-4080-1M |
| **Total**   |     |                                                                      |           | **$434.69** |                            |

---

## Parametric Modeling & CAD Assembly (Brayan and Mohammad)

- **Crosshead (Designed):** Parametrically modeled in SOLIDWORKS using global variables (Crosshead Length, Crosshead Width, Height, Screw Spacing) so all dimensions automatically update together.
- **Leadscrews (Downloaded):** Downloaded standard 3D CAD models for two 1/2"-10 RH precision carbon steel Acme leadscrews from McMaster-Carr.
- **Nuts & Flanges (Downloaded):** Sourced CAD models for two precision bronze Acme nuts and steel mounting flanges directly from McMaster-Carr.
- **Frame (Downloaded):** Downloaded 40 Series 80/20 double t-slot aluminum framing CAD files to construct the rigid outer test frame.
- **Assembly Mates:** Mated the aluminum frame using rigid mates, fixed the leadscrews in place, and applied concentric and screw mates between the nuts, flanges, and crosshead to allow realistic vertical crosshead motion.

*(Insert Assembly CAD screenshot here)*

---

## Lessons Learned

**Engineering Lessons Learned:**

- **Power Screw Drivetrain:** Applied Shigley's power screw torque equations to relate rotational driving torque (T_max = 2.023 N·m) directly to the required 2 kN axial pulling load, accounting for thread and collar friction.
- **Deflection vs. Strength Sizing:** Learned that elastic deflection (delta ≤ 0.1 mm) drives the crosshead design rather than yield strength, requiring an increased height of 35 mm (up from the 14.74 mm strength minimum).
- **Component Sourcing & Interfaces:** Selected standard 1/2"-10 Acme leadscrews from catalog resources, ensuring the 9.83 mm minor diameter comfortably exceeded the calculated 3.71 mm stress limit.
- **Parametric Assembly Modeling:** Configured global variables in SOLIDWORKS (Crosshead Length, Crosshead Width, Height, Screw Spacing) to establish robust parametric links between the custom crosshead, leadscrews, nuts, and aluminum frame.

**Total Time Spent:**

- Calculations & Theoretical Sizing: 4 hours
- Catalog Research & Part Selection: 2 hours
- SOLIDWORKS Modeling & Assembly: 5 hours
- Documentation & Portfolio Write-Up: 3 hours
- **Total Time: 14.0 Hours**

