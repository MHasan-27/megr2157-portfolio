# A11 – Motor Selection Design

## Team Members
- Mohammad Hasan (mhasan27@charlotte.edu)
- Brayan Maldonado-Guzman (bmaldon3@charlotte.edu)
- Candy Vasquez (cvasque6@charlotte.edu)

---

## 1. Motor Selection & Verification (Brayan)

I began by reviewing the torque and speed requirements from the leadscrew design.

The tensile tester uses two leadscrews to distribute the load and move the crosshead. Each motor needs enough torque to turn its screw while supporting the required crosshead speed range.

I selected the McMaster-Carr 4855N17 DC gearmotor as the motor. Its published continuous operating point is 20 rpm at 100 in-lb of torque, which exceeds the preliminary torque-selection target and closely matches the required maximum screw speed.

The motor specifications are:
- Operating voltage: 90 V DC
- Full-load current: 0.54 A
- Continuous operating speed: 20 rpm
- Continuous operating torque: 100 in-lb
- Output shaft: 1/2-inch keyed shaft
- Rotation: Clockwise and counterclockwise

I reviewed the motor specifications and torque-speed chart, then downloaded its CAD model and inserted it into the assembly. I used the gearbox output speed rather than the higher internal motor speed when comparing it with the leadscrew requirements.

I also distinguished starting torque from continuous torque because the higher starting value cannot be treated as a continuous operating rating.

The motor provides a suitable nominal operating point for the preliminary design. Performance across the full required speed range still needs confirmation, particularly at low speed. The two motors must remain synchronized to prevent crosshead tilting, and separate bearing supports are intended to carry the leadscrew thrust.

---

## 2. Motor Mount Bracket / Housing Design (Brayan)

I designed an elevated motor mount using a square plate. This arrangement provides space for the coupler above the frame and leaves an opening for access to its retaining screws.

The plate began as a centered sketch. I examined the motor CAD model and measured the shaft location relative to the mounting-hole pattern. Since the shaft is offset from the pattern center, I positioned the plate's clearance opening approximately 15.00 mm from its center.

I measured the raised side around the shaft and selected a 29 mm opening to provide clearance.

The mounting specifications are:
- Clearance opening: 29 mm
- Opening offset from plate center: 15.00 mm
- Mounting holes: 4 x 5.2 mm
- Mounting pattern: 67.183 mm x 40.00 mm
- Plate thickness: 8 mm

I inserted the plate into the assembly and aligned its mounting holes with the motor. After positioning the motor and coupler, I measured the space between the motor mounting face and the frame.

I evaluated mounting-hole bearing stress and performed a plate-bending check. These calculations supported retaining the 8 mm plate under the stated assumptions.

I then used Interference Detection to inspect the motor, plate, and coupler. The mount provides a layout for maintaining shaft alignment and accessing the coupling.

---

## 3. Coupler Design & Torsional Shear Analysis (Brayan)

I designed a custom coupler to connect the motor's smooth keyed shaft to the fully threaded Acme leadscrew.

I investigated purchased couplers first, but did not verify a ready-made McMaster coupling that directly matched both interfaces without modifying the screw.

### Coupler Dimensions

- Outside diameter: 25 mm
- Overall length: 56 mm
- Motor-side bore diameter: 12.7 mm
- Motor-side bore depth: 25 mm
- Keyway width: 3.175 mm
- Leadscrew-side starting bore diameter: 10.16 mm
- Leadscrew-side bore depth: 28 mm

I added a cosmetic thread identifying a half-inch, 10-thread-per-inch, right-hand Acme connection with 25.4 mm of full engagement. This kept the CAD model manageable while communicating the intended thread.

I created a tangent reference plane to locate the radial retaining holes. Using Hole Wizard, I added an M4 tapped hole near the motor end and another near the leadscrew end.

I corrected the original hole depth after it extended into the opposite wall, reducing it to an 8 mm blind hole.

I inserted the coupler into the assembly and used concentric and distance mates to establish its alignment and position. I then aligned the motor shaft with the keyed bore and set its depth to 25 mm. When the key and keyway initially faced opposite directions, I corrected the mate alignment so they matched.

The preliminary analysis included coupler-body torsion and key shear and bearing checks. The keyway bearing calculation established a minimum yield-strength requirement of 500 MPa for both the coupler and key.

---

## 4. Frame Corner Bracket & Twist Analysis (Mohammad)

### a.) Knowns and Unknowns

**Knowns:**

- Top Horizontal Crossbeam (L_beam): 1.5 ft = 457.2 mm
- Crossbeam: McMaster #5537T038, 80 mm x 40 mm 40-Series rail, laid flat with 80 mm depth front-to-back and 40 mm vertical height.
- Vertical Standoffs: 4 ft, McMaster #5537T46, 80 mm x 40 mm 40-Series rail, oriented with 40 mm width along the front span and 80 mm depth front-to-back.
- Crosshead Length: 400 mm
- Leadscrew Spacing: 300 mm apart (50 mm from each end of the crosshead).

**Equal Side Clearances (c_side):**

```text
c_side = (457.2 - 400)/2

c_side = 28.6 mm
```

**Effective Span (L):**

Center-to-center distance between vertical standoffs, with 40 mm column width and 20 mm from the inner face to centerline on each side:

```text
L = 457.2 + 20 + 20

L = 497.2 mm
```

**Leadscrew Offset from Column Center (a):**

```text
a = (497.2 - 300)/2

a = 98.6 mm
```

**Axial Load per Screw (F_s):**
- 1000 N downward reaction
- 2000 N total

**Motor Torque (McMaster #4855N17):**

- Operating Torque (T_op): 2.204 N*m per motor
- Design Torque (T_design at SF = 4): 8.816 N*m per motor
- Stall Torque (T_stall): 22.6 N*m per motor

**Unknowns:**
- End Vertical Reactions: R_Ay and R_By
- End Stabilizing Forces: F_stab (couple forces resisting motor twist)
- T-Slot Connector and Fastener Stress:
  - Tensile stress (sigma_t)
  - Shear stress (tau)

### Selected Connector (McMaster-Carr Double-Rail Corner Brackets)

**Primary Part:**
- McMaster-Carr #5537T665
- 40-Series Open Gusset Corner Bracket for 40 mm High Double/Quad Rails
- Length: 1 37/64 in (40 mm)
- Material: Anodized aluminum
- Price: $15.26 each
- Includes M8 drop-in screws and T-slot nuts.

**Closed-Side Alternative:**
- McMaster-Carr #5537T197
- 40-Series Extended Closed Gusset Corner Bracket for 40 mm High Double/Quad Rails
- Length: 1 27/64 in
- Material: Aluminum with cover
- Price: $21.40 each
- Fasteners included.

**Engineering Justification:**

Designed for the 40 mm height side of double T-slot rails (#5537T112), its compact 1 37/64 in (40 mm) leg length provides full clearance for the leadscrew/coupler pass-through holes (78.6 mm from each end of the top rail) without physical interference.

Mounted on both the front and back faces across the 80 mm depth (d = 40 mm slot spacing) underneath the top crossbeam, it resists out-of-plane motor twist (565 N at stall) while supporting the 2000 N vertical load in direct compression.

---

## 5. Top Frame Beam FEA Verification (Heavy 40-Series) (Mohammad and Candy)

### a.) Model Setup (Geometry, Material, Constraints & Loads)

#### 1. Part & Material

- Component: Top horizontal crossbeam (#5537T038 / #5537T112)
- Dimensions: 80 mm deep x 40 mm high x 457.2 mm long
- Orientation: Laid flat with the two 40 mm-spaced T-slots facing top/bottom.
- Material: 6061-T6 Aluminum Alloy

Material Properties:

| Property | Value |
|---|---:|
| Yield Strength (Sy) | 276 MPa |
| Elastic Modulus (E) | 68,900 MPa |
| Poisson's Ratio (v) | 0.33 |

#### 2. Split Lines (Creating Exact Load & Constraint Faces in SOLIDWORKS)

Use Insert > Curve > Split Line on the top and bottom faces of the extrusion to isolate the exact contact footprints so loads and fixtures are realistic (avoiding point-load singularities).

- End Corner Bracket Footprints (Left & Right Ends):
  - Split a 40 mm x 40 mm pad at each end of the bottom face (and end faces) representing the #5537T6 Extended Open Gusset Corner Brackets.
- Motor / Thrust Mount Footprints:
  - Split two mounting pads matching the motor mount footprint, e.g., 110 mm x 110 mm for the #4855N17 motor base.

#### 3. Boundary Conditions (Fixtures)

Apply Fixed Geometry to the two 40 mm x 40 mm end bracket contact pads (or specifically to the 4 M8 bolt-pad regions per end) where the #5537T6 corner brackets clamp the top beam to the vertical standoffs.

#### 4. Applied Loads

**Leadscrew Axial Reactions:**

Apply Fy = -1000 N (downward) on each of the two motor/thrust bearing split pads (2000 N total axial tension path).

**Motor Reaction Torques:**

Apply a torque of T = 8.816 N*m (SF = 4 design torque per motor; or 2.204 N*m operating torque) about the vertical axis (y-axis) on each motor mount pad, both acting in the same rotational direction (CCW/CW).

Apply the loads to both sides (x2).

### b.) Meshing & Verification (Mesh Convergence Study)

**Mesh Type:**

Curvature-based Solid Tetrahedral Mesh with Local Mesh Control (1.5 mm - 2.0 mm element size) applied along the inner T-slot neck fillets (R = 1 - 2 mm) and split-line edges around the motor mounts and corner brackets where stress concentrations occur.

**Mesh Convergence Table:**

| Mesh Pass | Global Element Size | Local Control Size | Max von Mises Stress (MPa) | % Change (Stress) | Max Vertical Deflection (mm) | % Change (Deflection) | Min Factor of Safety |
|---|---:|---:|---:|---:|---:|---:|---:|
| Coarse | 8.0 mm | 4.0 mm | 67.1654 | - | 0.016666 | - | 0.82 |
| Medium | 5.0 mm | 2.5 mm | 119.8494 | 78.44% | 0.017669 | 6.02% | 0.46 |
| Fine | 3.0 mm | 1.5 mm | 98.7234 | 17.64% | 0.017779 | 0.62% | 0.56 |

**Analytical Benchmark Check:**

Treating the 457.2 mm rail as a doubly clamped/guided beam with Ix approximately equal to 1.38 x 10^5 mm^4:

- Analytical peak bending stress: sigma approximately 22 - 28 MPa
- Peak midspan deflection: delta approximately 0.04 - 0.06 mm
- Theoretical Factor of Safety: SF approximately 10 - 12, greater than 4.

Your converged FEA stress will be slightly higher, typically 30 - 45 MPa, due to local T-slot flange stress concentrations around the motor mount bolts.

### c.) Results to Report

**i. Maximum von Mises Stress & Location**

Report peak converged value:

```text
sigma_max = [X.XX] MPa
```

The stress is located at the inner T-slot flange root / corner bracket edge nearest the leadscrew load application pads, where combined bending shear and T-slot flange pull-up occur.

**ii. Maximum Vertical Deflection at the Grip Line (Midspan)**

Report maximum y-displacement at the center grip axis:

```text
delta_max = [0.0XX] mm
```

The result should remain well below the 0.1 mm alignment threshold established in Part 1.

**iii. Factor of Safety**

Based on 6061-T6 yield strength Sy = 276 MPa:

```text
SF = Sy/sigma_max

SF = 276 MPa/sigma_max

SF > 4
```

This meets the required SF = 4 constraint when the calculated value is greater than or equal to 4.

There is good convergence between the maximum vertical displacement as the mesh size improves. The difference between the medium and fine meshes is 0.62%, which means the predicted displacement does not need much improvement.

On the other hand, unfortunately there is a big difference of 17.64% in the maximum von Mises stress between the medium and fine meshes. This means stress convergence has not yet been achieved.

**iv. Load Path & Twisting/Warping Discussion**

**Load Path:**

The two 1000 N downward forces enter through the motor/thrust bearing mounting pads, travel outward along the top and bottom flanges and central web of the 80 mm x 40 mm extrusion, and transfer into the #5537T6 corner brackets at the ends.

**Twisting & Warping Tendencies:**

Because the two synchronous motors apply equal reaction torques (8.816 N*m each) in the same direction about the vertical axis, the top crossbeam experiences a slight S-shaped in-plane horizontal racking/twist in the x-z plane.

However, laying the 80 mm dimension horizontally maximizes the transverse moment of inertia (Iy approximately 4.9 x 10^5 mm^4, roughly 3.5 times stiffer laterally than vertically), keeping torsional warping negligible.

### d.) Optimization Pass

To optimize this design, I decided to remove material from low-stress regions to reduce overall weight, similarly to the last assignment.

However, from my last optimization I learned to avoid removing material near high-stress areas as it impacts its ability to withstand bending. I also decided to add fillets to reduce stress concentrations via sharp corners.

**Optimization Results:**

| Parameter | Original Fine Mesh | Optimized Fine Mesh | Change |
|---|---:|---:|---:|
| Maximum von Mises Stress (MPa) | 98.7234 | 87.7194 | 11.15% decrease |
| Maximum Deflection (mm) | 0.017779 | 0.021894 | 23.15% increase |
| Factor of Safety | 0.56 | 0.63 | 12.50% increase |

This optimization represents a more successful improvement compared with the original design.

The reduction in maximum von Mises stress and increase in factor of safety indicate that the modified geometry provides better stress distribution and improved resistance to yielding.

Although vertical deflection increased by 23.15%, this represents that the optimized bracket bends slightly more under the applied loading, but the absolute displacement remains relatively small, which is positive.

Overall, the optimized design achieved an 11.15% reduction in maximum stress and a 12.50% increase in factor of safety.

The results suggest that the optimization was beneficial overall, particularly in improving the bracket's strength characteristics. However, additional improvements are necessary to increase bending stiffness and achieve a factor of safety greater than 1.0.

---

## 6. Vertical Frame Standoff FEA Verification (Heavy 40-Series) (Mohammad and Candy)

### a.) Model Setup (Geometry, Material, Constraints & Loads)

#### 1. Part & Material

- Component: One vertical standoff column (McMaster #5537T46 / #5537T112)
- Dimensions: 80 mm x 40 mm x 4 ft (1219.2 mm)
- Orientation: 40 mm width along the front span and 80 mm depth front-to-back.
- Material: 6061-T6 Aluminum Alloy

Material Properties:

| Property | Value |
|---|---:|
| Yield Strength (Sy) | 276 MPa |
| Elastic Modulus (E) | 68,900 MPa |
| Poisson's Ratio (v) | 0.33 |

#### 2. Split Lines (Isolating Bracket Interfaces in SOLIDWORKS)

Use Insert > Curve > Split Line to create realistic contact footprints.

**Top Corner Bracket Interface (Inner Face):**

On the upper inner 80 mm face, split two 40 mm x 40 mm pads spaced 40 mm apart (located 40 mm down from the top edge, directly beneath the top horizontal crossbeam) where the two #5537T665 gusset brackets attach.

#### 3. Boundary Conditions (Fixtures)

**Bottom Base Face:**

Apply Fixed Geometry to the bottom end face (and base bracket mounting pads) to anchor the column to the baseplate/frame.

#### 4. Applied Loads (Two Required Loads)

**1. Axial Compression Load (F_axial):**

Apply Fy = -1000 N (downward compression, or -4000 N if running at SF = 4) onto the top inner #5537T665 corner bracket footprints (transferred down from the top crossbeam under the 2000 N tensile pull).

**2. Transverse Twist Force (F_transverse):**

Apply the end stabilizing force couple from Section 4 onto the two parallel T-slot bracket pads (d = 40 mm apart) in the transverse (z) direction.

At Design Torque (T_design = 8.816 N*m, SF = 4):

```text
F_transverse = +/-220.4 N

+220.4 N on the front bracket pad
-220.4 N on the back bracket pad
```

Or at Worst-Case Motor Stall Torque (T_stall = 22.6 N*m):

```text
F_transverse = +/-565.0 N
```

### b.) Meshing & Verification (Mesh Convergence Study)

**Mesh Type:**

Curvature-based Solid Tetrahedral Mesh with Local Mesh Control (1.5 mm - 2.0 mm element size) applied to the inner T-slot neck fillets along the #5537T665 bracket split pads and the fixed base transition.

**Mesh Convergence Table:**

| Mesh Pass | Global Element Size | Local Control Size | Max von Mises Stress (MPa) | % Change (Stress) | Max Deflection (mm) | % Change (Deflection) | Min Factor of Safety |
|---|---:|---:|---:|---:|---:|---:|---:|
| Coarse | 12.0 mm | 5.0 mm | 76.5020 | - | - | - | - |
| Medium | 8.0 mm | 3.0 mm | 81.6757 | +6.77% | 21.1284 | -0.059% | 0.73 |
| Fine | 5.0 mm | 1.5 mm | 88.1300 | +7.90% | 21.1403 | +0.115% | 0.63 |

The mesh convergence shows how the maximum vertical deflection stayed pretty consistent across all mesh refinements, with values staying close to 21.14 mm.

Maximum von Mises stress increased as the mesh became finer, indicating that smaller elements captured stress concentrations more accurately.

The medium and fine mesh results showed a relatively small difference in stress, suggesting that the solution is approaching convergence.

The fine mesh produced a maximum stress of 88.13 MPa and a factor of safety of 0.63, indicating that the design may exceed the material's yield strength under the applied loading conditions.

**Analytical Check:**

For a 1219.2 mm 40-Series 80 x 40 column (A approximately 1160 mm^2), pure axial compression under 1000 N produces:

```text
sigma_c = 1000/1160

sigma_c = 0.86 MPa
```

Axial shortening:

```text
delta_y = (F*L)/(A*E)

delta_y = 0.015 mm
```

Combined with the transverse twist couple, peak localized stress occurs at the T-slot bracket interface.

### c.) Results to Report

**i. Maximum von Mises Stress & Location**

Report peak converged value:

```text
sigma_max = [X.XX] MPa
```

The stress is located at the T-slot flange root edges of the upper #5537T665 corner bracket pads (or at the fixed base fillet where bending and axial compression combine).

**ii. Maximum Vertical Deflection at the Grip Line**

Report maximum y-displacement (axial compression at the upper bracket / grip-line height):

```text
delta_y,max = [0.015 - 0.030] mm
```

Also note the small transverse tip deflection (delta_z).

**iii. Factor of Safety**

Based on 6061-T6 yield strength Sy = 276 MPa:

```text
SF = Sy/sigma_max

SF = 276 MPa/sigma_max
```

**iv. Load Path & Twisting/Warping Discussion**

### d.) Optimization Pass

#### 1. Proposed Targeted Changes

The simulation results show that the highest stress is concentrated around the bottom of the rod, while the greatest amount of movement occurs near the top.

To improve the design, the connection between the rod and the base could be strengthened by increasing the material thickness in that area. This would help spread the forces more evenly and make the structure less likely to bend at its base.

To limit the movement at the top, the rod itself could be made thicker or reinforced along its length. This would increase its overall stiffness and help it withstand the applied loads with less bending or twisting.

#### 2. Shift in Critical Locations & Performance Gain

| Parameter | Original Fine Mesh | Optimized Fine Mesh | Change |
|---|---:|---:|---:|
| Maximum von Mises Stress (MPa) | 88.1300 | 85.3230 | -3.18% |
| Maximum Deflection (mm) | 21.1403 | 19.1904 | -9.22% |
| Factor of Safety | 0.63 | 0.65 | +3.17% |

The optimized design showed improvements overall in structure compared to the original model.

The maximum von Mises stress decreased by 3.18%, and maximum deflection improved by deflecting less with a percent difference of 9.22%.

Additionally, the factor of safety increased slightly from 0.63 to 0.65.

These results suggest that the design modifications improved the stiffness of the structure and helped reduce the effects of the applied loading.

Although the improvements were relatively small, they show that the optimization was beneficial.

---

## 7. Floating Bearing Mount Design (Mohammad)

### 1. Purpose & Function

This mount bolts to the bottom 40-Series aluminum rail to radially support the turned bottom journal (3/8 in / 9.525 mm) of the 1018 Carbon Steel 1/2"-10 Acme leadscrew while leaving it free to move axially.

This prevents shaft whip and thermal buckling while keeping the screw aligned with the upper motor mount.

### 2. Size & Location Justifications

**Base Plate:**
- Dimensions: 60.0 mm x 60.0 mm x 10.0 mm
- Fits cleanly on the 80.0 mm wide bottom rail.
- Clears the end corner gussets.
- Provides 10.0 mm thickness to prevent bending under bolt clamping.

**Mounting Holes:**
- Quantity: 4
- Diameter: 5.20 mm
- Pattern: 40.0 mm x 40.0 mm
- Edge distance: 10.0 mm

Matches the two parallel T-slots (40.0 mm apart) and leaves a 10.0 mm edge distance to prevent tear-out.

Per Machinery's Handbook (Metric Clearance Holes, Normal Fit), 5.20 mm gives proper clearance for M5 screws.

**Center Hub:**
- Outside Diameter: 35.0 mm
- Height: 25.0 mm
- Bore Diameter: 12.718 mm

Provides a 12.74 mm thick radial wall around the 9.525 mm bore to resist side loads without deflecting and gives 25.0 mm of engagement.

```text
L/D = 25.0/9.525

L/D = 2.6
```

**Frame Position:**
- Leadscrew spacing: 300.0 mm apart
- Distance from rail ends: 78.6 mm

Matches the upper motor mount spacing so both leadscrews stay straight and vertical.

### 3. RC3 Fit & Functional Tolerances

Because a 1/2"-10 Acme screw has a minor diameter of 0.3800 in (9.652 mm), the bottom end is turned to a 3/8 in (0.3750 in / 9.525 mm) cylindrical journal.

Per Machinery's Handbook (ANSI B4.1, RC3 Precision Running Fit, H7/f6):

**Turned Screw Journal (f6):**

```text
Diameter = 9.525 mm

Tolerance = -0.013 mm to -0.022 mm
```

**Hub Bore (H7):**

```text
Diameter = 9.525 mm

Tolerance = +0.000 mm to +0.015 mm
```

The resulting diametral running clearance is:

```text
Minimum clearance = 0.013 mm

Maximum clearance = 0.037 mm

Clearance = 0.0005 in - 0.0015 in
```

**Functional Tolerances:**

- Center Bore ID: 9.525 mm with +0.015 mm tolerance.
- Bore Perpendicularity: 0.05 mm to the bottom mounting face.
- M5 Clearance Holes: 4 x 5.20 mm with +0.18 mm tolerance.
- True Position: 0.25 mm.

These tolerances ensure proper RC3 clearance and drop-in alignment with the 40.0 mm T-slots.

### 4. SOLIDWORKS Design Steps

**1. Base Plate (Boss-Extrude1)**

Sketched a 60.0 mm x 60.0 mm center-rectangle on the Top Plane, added four 5.20 mm holes spaced 40.0 mm apart (10.0 mm from edges), and extruded 10.0 mm.

**2. Bearing Hub (Boss-Extrude2)**

Sketched concentric circles of 35.0 mm outside diameter and 12.718 mm inside diameter on the top face, then extruded 25.0 mm with Merge Result checked.

---

## 8. Bill of Material and Labor Costs (Mohammad)

### Bill of Materials

| Item | Quantity | Name | Cost/Item | Total Cost | Purchase Link |
|---|---:|---|---:|---:|---|
| 1 | 4 | T-Slotted Framing 6-Slot Rail, Silver, 80 mm High, 40 mm Wide, Solid, 1.5 ft Long (McMaster #5537T038) | $39.52 | $158.08 | [McMaster](https://www.mcmaster.com/5537T038) |
| 2 | 2 | T-Slotted Framing Double 6-Slot Rail, Silver, 80 mm High, 40 mm Wide, Solid, 4 ft Long (McMaster #5537T46) | $98.37 | $196.74 | [McMaster](https://www.mcmaster.com/5537T46) |
| 3 | 4 | T-Slotted Framing Silver Gusset Bracket for 40 mm Rail, 1-37/64 in Long (McMaster #5537T665) | $15.26 | $61.04 | [McMaster](https://www.mcmaster.com/5537T665) |
| 4 | 4 | T-Slotted Framing Gusset Bracket for 40 mm High Rail, 1-37/64 in Long (McMaster #5537T586) | $7.64 | $30.56 | [McMaster](https://www.mcmaster.com/5537T586) |
| 5 | 2 | 1018 Carbon Steel Precision Acme Lead Screw, Right Hand, 1/2"-10 Thread Size, 3 Feet Long (McMaster #99030A005) | $18.72 | $37.44 | [McMaster](https://www.mcmaster.com/99030A005) |
| 6 | 2 | Precision Acme Externally Threaded Nut, Left Hand, 673 Bronze, 1/2"-10 Thread Size (McMaster #95072A209) | $37.61 | $75.22 | [McMaster](https://www.mcmaster.com/95072A209) |
| 7 | 2 | Precision Acme Flange, Black Oxide 1117 Carbon Steel, 15/16"-16 Thread Size (McMaster #1329K102) | $67.13 | $134.26 | [McMaster](https://www.mcmaster.com/1329K102) |
| 8 | 2 | DC Gearmotor, 20 rpm at 100 in-lb Continuous Operating Torque (McMaster #4855N17) | $575.30 | $1,150.60 | [McMaster](https://www.mcmaster.com/4855N17) |
| 9 | 2 | Designed Motor Mounts | No Quote Available | - | - |
| 10 | 1 | Designed Crosshead | No Quote Available | - | - |
| 11 | 2 | Designed Floating Journal Bearings | No Quote Available | - | - |
| 12 | 2 | Custom Top Inside Corner Brackets | No Quote Available | - | - |
| 13 | Various | M5 Hex Bolts | No Quote Available | - | - |

**Total Quoted Purchased Parts Cost: $1,843.94**

### Labor Costs

| Team Member | Hours Worked | Cost per Hour | Labor Cost |
|---|---:|---:|---:|
| Brayan | 8.0 | $35 | $280.00 |
| Mohammad | 10.0 | $35 | $350.00 |
| Candy | 11.0 | $35 | $385.00 |
| **Total** | **29.0** | | **$1,015.00** |

**Total Project Cost: $3,558.94**

---

## 9. Lessons Learned (Team)

### Brayan

This assignment pushed me to connect theoretical machine design equations directly to physical off-the-shelf hardware constraints.

From deriving the required operating and stall torques from our 1/2"-10 Acme leadscrew parameters to selecting the 90V DC gearmotors, I learned how motor sizing governs the structural and mechanical requirements of the entire drivetrain.

Performing the bearing stress analysis for the motor mount bracket and the torsional shear and keyway bearing stress calculations for the shaft coupler taught me how to select material yield strengths and wall thicknesses that satisfy a strict safety factor of 4 without over-sizing components.

Working alongside my teammates also showed me the value of cross-checking interface dimensions, such as shaft diameters, bolt patterns, and axial clearances, so that custom-machined parts integrate seamlessly with purchased McMaster-Carr hardware.

In total, my portion of the motor selection, mount bracket, and coupler design took 8 hours to complete.

### Mohammad

This project strengthened my ability to translate real-world mechanical loads into accurate analytical models, finite element simulations, and standards-based CAD parts.

Analyzing the frame twist caused by the dual motor reaction torques taught me how to resolve moments into equivalent force couples across parallel T-slot channels and verify M8 fastener shear and tensile stresses before selecting double-rail gusset brackets.

Setting up the FEA studies for the top crossbeam and vertical standoffs also deepened my understanding of boundary conditions and mesh convergence, specifically how using SOLIDWORKS Split Lines and local mesh refinement along T-slot fillets prevents artificial stress singularities and reveals true peak von Mises stress locations.

Additionally, designing the lower floating bearing mount reinforced how to apply Machinery's Handbook standards for metric bolt clearance holes and ANSI B4.1 RC3 precision running fits so the leadscrew rotates concentrically while remaining free to expand axially.

Collaborating with Candy and Brayan to align every subassembly in the final CAD model and consolidate the Bill of Materials made the workflow cohesive and efficient.

In total, my structural analysis, FEA verification, floating bearing design, and BOM documentation took 10.0 hours to complete.

### Candy

Working on this assignment expanded my experience in collaborative FEA verification, full-system CAD integration, and formal engineering documentation.

Assisting with the finite element simulations on the top horizontal crossbeam and vertical 40-Series standoffs taught me how combined axial compression and transverse motor twist affect deflection at the specimen grip line, and why verifying mesh convergence across multiple refinement passes is essential before trusting simulation results.

Creating the MEGR 2157 engineering drawing package, including third-angle projection views, ASME Y14.5 geometric dimensioning and tolerancing callouts, titleblocks, and the assembly isometric drawing, also showed me how manufacturing tolerances directly protect functional fits and alignment across mating components.

Coordinating closely with Mohammad and Brayan to ensure every part number, dimension, and assembly mate matched between the 3D CAD assembly and the final drawings demonstrated how clear communication prevents costly design discrepancies.

In total, my work on the frame FEA studies, engineering drawing package, and final report documentation took 7.5 hours to complete.

---

## 10. Time Spent Documentation

| Assignment Section | Task Description | Assigned Member | Hours Spent |
|---|---|---|---:|
| 1-3 | Motor Selection, Motor Mount Bracket & Coupler Design (torque/speed sizing, bearing stress, torsion/keyway analysis) | Brayan | 8 |
| 4 | Frame Corner Bracket & Twist Analysis (FBDs, twist stabilization forces, M8 fastener checks, gusset selection) | Mohammad | 4 |
| 5 | Top Frame Beam FEA Verification (Split Lines, boundary conditions, local fillet mesh refinement & convergence) | Mohammad, Candy | 3 |
| 6 | Vertical Frame Standoff FEA Verification (axial compression + transverse twist simulation & mesh convergence) | Mohammad, Candy | 4 |
| 7 | Floating Bearing Mount Design (SOLIDWORKS modeling, Machinery's Handbook clearance holes, RC3 fit & tolerances) | Mohammad | 4 |
| 8 | Bill of Materials, Labor Cost Tabulation | Mohammad | 2.5 |
| 9 | Lessons Learned Documentation | Team | 2 |
| - | Engineering Drawing Package (ASME Y14.5 third-angle projection detail drawings, assembly isometric & BOM) | Candy | 2 |

**Total Combined Project Time: 29.5 Hours**
