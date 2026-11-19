# A11 – Motor Selection Design

## Team Members
- Mohammad Hasan (mhasan27@charlotte.edu)
- Brayan Maldonado-Guzman (bmaldon3@charlotte.edu)
- Candy Vasquez (cvasque6@charlotte.edu)

---

## 1. Motor Selection & Verification (Brayan)

I began by reviewing the torque and speed requirements from the leadscrew design.

The tensile tester uses two leadscrews to distribute the load and move the crosshead. Each motor needs enough torque to turn its screw while supporting the required crosshead speed range.

<img width="974" height="735" alt="image" src="https://github.com/user-attachments/assets/97485556-65e7-48da-a3b4-08ab7ea9fe50" />
<img width="974" height="1057" alt="image" src="https://github.com/user-attachments/assets/2584f487-b550-4a4c-abff-b854c4258aee" />


I selected the McMaster-Carr 4855N17 DC gearmotor as the motor. Its published continuous operating point is 20 rpm at 100 in-lb of torque, which exceeds the preliminary torque-selection target and closely matches the required maximum screw speed.

The motor specifications are:
- Operating voltage: 90 V DC
- Full-load current: 0.54 A
- Continuous operating speed: 20 rpm
- Continuous operating torque: 100 in-lb
- Output shaft: 1/2-inch keyed shaft
- Rotation: Clockwise and counterclockwise

<img width="974" height="1121" alt="image" src="https://github.com/user-attachments/assets/2d6c0b98-84d6-483c-91e4-712aa6461e1f" />

I reviewed the motor specifications and torque-speed chart, then downloaded its CAD model and inserted it into the assembly. I used the gearbox output speed rather than the higher internal motor speed when comparing it with the leadscrew requirements.

I also distinguished starting torque from continuous torque because the higher starting value cannot be treated as a continuous operating rating.

<img width="974" height="1261" alt="image" src="https://github.com/user-attachments/assets/2412a112-1288-4b07-b3de-cef6614d03f0" />

The motor provides a suitable nominal operating point for the preliminary design. Performance across the full required speed range still needs confirmation, particularly at low speed. The two motors must remain synchronized to prevent crosshead tilting, and separate bearing supports are intended to carry the leadscrew thrust.

<img width="974" height="864" alt="image" src="https://github.com/user-attachments/assets/b0044b2f-e81d-4121-9454-4d3f27dae39e" />

---

## 2. Motor Mount Bracket / Housing Design (Brayan)

<img width="974" height="1098" alt="image" src="https://github.com/user-attachments/assets/da248187-c15b-4cdb-99e9-7d477c7b36c0" />
<img width="974" height="1261" alt="image" src="https://github.com/user-attachments/assets/985692a6-c3de-431c-adf4-af3c7ca63f18" />


I designed an elevated motor mount using a square plate. This arrangement provides space for the coupler above the frame and leaves an opening for access to its retaining screws.

The plate began as a centered sketch. I examined the motor CAD model and measured the shaft location relative to the mounting-hole pattern. Since the shaft is offset from the pattern center, I positioned the plate's clearance opening approximately 15.00 mm from its center.

I measured the raised side around the shaft and selected a 29 mm opening to provide clearance.

The mounting specifications are:
- Clearance opening: 29 mm
- Opening offset from plate center: 15.00 mm
- Mounting holes: 4 x 5.2 mm
- Mounting pattern: 67.183 mm x 40.00 mm
- Plate thickness: 8 mm

<img width="975" height="706" alt="image" src="https://github.com/user-attachments/assets/d2b249ca-0c09-43ea-be87-6ea442eab27a" />

I inserted the plate into the assembly and aligned its mounting holes with the motor. After positioning the motor and coupler, I measured the space between the motor mounting face and the frame.

I evaluated mounting-hole bearing stress and performed a plate-bending check. These calculations supported retaining the 8 mm plate under the stated assumptions.

I then used Interference Detection to inspect the motor, plate, and coupler. The mount provides a layout for maintaining shaft alignment and accessing the coupling.

---

## 3. Coupler Design & Torsional Shear Analysis (Brayan)

<img width="974" height="755" alt="image" src="https://github.com/user-attachments/assets/8d558cb5-9024-4607-96f8-ff0687f80f01" />
<img width="974" height="1261" alt="image" src="https://github.com/user-attachments/assets/016f34a8-5c69-4326-954d-84c7c78e1952" />
<img width="974" height="1261" alt="image" src="https://github.com/user-attachments/assets/08d15d0a-3636-41fc-98a3-8f536cc9c739" />
<img width="974" height="884" alt="image" src="https://github.com/user-attachments/assets/f3eff804-a58e-419d-8da3-49f8230e6d77" />

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

<img width="975" height="738" alt="image" src="https://github.com/user-attachments/assets/f964bb83-4d2a-49c7-b3dc-89c36ce73290" />
<img width="975" height="712" alt="image" src="https://github.com/user-attachments/assets/32b536d7-8f2f-428c-af81-8bc92cd3a148" />

I added a cosmetic thread identifying a half-inch, 10-thread-per-inch, right-hand Acme connection with 25.4 mm of full engagement. This kept the CAD model manageable while communicating the intended thread.

<img width="975" height="728" alt="image" src="https://github.com/user-attachments/assets/a30d7a72-ea92-4e21-80d9-ed3c91b2bef2" />

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

<img width="854" height="1105" alt="image" src="https://github.com/user-attachments/assets/42d62a2e-05f9-4c43-a21c-68ca54d77a89" />
<img width="879" height="504" alt="image" src="https://github.com/user-attachments/assets/ef65db89-ffe9-499d-ae69-066bfad32af9" />


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
    <img width="488" height="159" alt="image" src="https://github.com/user-attachments/assets/776530d7-7822-4957-90c4-9a86a65a9bce" />

- Motor / Thrust Mount Footprints:
  - Split two mounting pads matching the motor mount footprint, e.g., 110 mm x 110 mm for the #4855N17 motor base.
<img width="585" height="166" alt="image" src="https://github.com/user-attachments/assets/92ade9e8-e13d-4f2d-8d3c-e69879ac906b" />

#### 3. Boundary Conditions (Fixtures)

Apply Fixed Geometry to the two 40 mm x 40 mm end bracket contact pads (or specifically to the 4 M8 bolt-pad regions per end) where the #5537T6 corner brackets clamp the top beam to the vertical standoffs.
<img width="598" height="353" alt="image" src="https://github.com/user-attachments/assets/8f809e92-10ef-4a6c-8dca-5f4497abb41e" />
<img width="530" height="125" alt="image" src="https://github.com/user-attachments/assets/ea2387a5-65ad-4a03-aef8-f7a8d20f09a0" />

#### 4. Applied Loads

**Leadscrew Axial Reactions:**

Apply Fy = -1000 N (downward) on each of the two motor/thrust bearing split pads (2000 N total axial tension path).
<img width="655" height="260" alt="image" src="https://github.com/user-attachments/assets/9995fd90-ad69-470f-8103-b686ab34c433" />

**Motor Reaction Torques:**

Apply a torque of T = 8.816 N*m (SF = 4 design torque per motor; or 2.204 N*m operating torque) about the vertical axis (y-axis) on each motor mount pad, both acting in the same rotational direction (CCW/CW).
<img width="578" height="301" alt="image" src="https://github.com/user-attachments/assets/cec58a3c-8298-4039-a27e-e3c62c4333ab" />

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

<img width="619" height="330" alt="image" src="https://github.com/user-attachments/assets/9a59d9d0-b6ac-44f4-96d0-70d7400e744b" />
<img width="647" height="319" alt="image" src="https://github.com/user-attachments/assets/12216285-02b7-4cc4-a783-c86b4c7a0922" />
<img width="609" height="297" alt="image" src="https://github.com/user-attachments/assets/06791a84-3f3d-442a-a590-e988edb5a385" />


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

<img width="676" height="285" alt="image" src="https://github.com/user-attachments/assets/6b654bf9-c353-421c-9515-832908e5a228" />


**Optimization Results:**

| Parameter | Original Fine Mesh | Optimized Fine Mesh | Change |
|---|---:|---:|---:|
| Maximum von Mises Stress (MPa) | 98.7234 | 87.7194 | 11.15% decrease |
| Maximum Deflection (mm) | 0.017779 | 0.021894 | 23.15% increase |
| Factor of Safety | 0.56 | 0.63 | 12.50% increase |

<img width="505" height="275" alt="image" src="https://github.com/user-attachments/assets/65e56015-d8e9-4af7-9acb-5b8f638534b8" />
<img width="482" height="260" alt="image" src="https://github.com/user-attachments/assets/05403703-5c6a-4e14-bbfc-9e08bcfd508b" />
<img width="504" height="274" alt="image" src="https://github.com/user-attachments/assets/d9e65334-45b3-467c-aedb-5cc7c5a33c6a" />

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

<img width="432" height="529" alt="image" src="https://github.com/user-attachments/assets/00964a5c-3ba9-4e4a-9764-0b7aab1163ff" />

#### 2. Split Lines (Isolating Bracket Interfaces in SOLIDWORKS)

Use Insert > Curve > Split Line to create realistic contact footprints.

**Top Corner Bracket Interface (Inner Face):**

On the upper inner 80 mm face, split two 40 mm x 40 mm pads spaced 40 mm apart (located 40 mm down from the top edge, directly beneath the top horizontal crossbeam) where the two #5537T665 gusset brackets attach.

<img width="244" height="293" alt="image" src="https://github.com/user-attachments/assets/a62a9337-26e6-4bf8-942f-7257537d1556" />

#### 3. Boundary Conditions (Fixtures)

**Bottom Base Face:**

Apply Fixed Geometry to the bottom end face (and base bracket mounting pads) to anchor the column to the baseplate/frame.

<img width="416" height="366" alt="image" src="https://github.com/user-attachments/assets/747f6843-344d-4e50-9095-cee3af4d6bce" />

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

<img width="546" height="473" alt="image" src="https://github.com/user-attachments/assets/144040c2-8b57-44b9-a71a-55c80f681ee8" />
<img width="547" height="347" alt="image" src="https://github.com/user-attachments/assets/647f95d0-457d-4e39-a9c0-7eebf1e45f06" />

### b.) Meshing & Verification (Mesh Convergence Study)

**Mesh Type:**

Curvature-based Solid Tetrahedral Mesh with Local Mesh Control (1.5 mm - 2.0 mm element size) applied to the inner T-slot neck fillets along the #5537T665 bracket split pads and the fixed base transition.

**Mesh Convergence Table:**

| Mesh Pass | Global Element Size | Local Control Size | Max von Mises Stress (MPa) | % Change (Stress) | Max Deflection (mm) | % Change (Deflection) | Min Factor of Safety |
|---|---:|---:|---:|---:|---:|---:|---:|
| Coarse | 12.0 mm | 5.0 mm | 76.5020 | - | - | - | - |
| Medium | 8.0 mm | 3.0 mm | 81.6757 | +6.77% | 21.1284 | -0.059% | 0.73 |
| Fine | 5.0 mm | 1.5 mm | 88.1300 | +7.90% | 21.1403 | +0.115% | 0.63 |

<img width="353" height="432" alt="image" src="https://github.com/user-attachments/assets/73fdce8c-3db5-4662-a1f9-83f913c6717e" /> <img width="301" height="436" alt="image" src="https://github.com/user-attachments/assets/9f66814f-82d1-4865-9a4b-f8db454155b7" /> <img width="294" height="393" alt="image" src="https://github.com/user-attachments/assets/60eeac8f-d564-47e3-956f-284ae6c82d9b" />



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

<img width="401" height="281" alt="image" src="https://github.com/user-attachments/assets/15ac40b0-8321-4a77-810b-9e08ae84c4a0" />
<img width="483" height="577" alt="image" src="https://github.com/user-attachments/assets/502ec76b-faf9-443a-983d-7398148b1651" /> <img width="418" height="549" alt="image" src="https://github.com/user-attachments/assets/2a7277a2-9395-4408-8349-954f8e3ee5d3" />
<img width="439" height="430" alt="image" src="https://github.com/user-attachments/assets/ed0c6659-c27c-4d24-96cc-9d1b5dcce659" />

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
<img width="974" height="709" alt="image" src="https://github.com/user-attachments/assets/bdea9326-9ad7-49e3-97b5-0cf8b5d06aad" />

**2. Bearing Hub (Boss-Extrude2)**

Sketched concentric circles of 35.0 mm outside diameter and 12.718 mm inside diameter on the top face, then extruded 25.0 mm with Merge Result checked.
<img width="973" height="777" alt="image" src="https://github.com/user-attachments/assets/5759a7ba-25e9-423c-908d-bde8f3ee8afe" />

---
### Final Assembly

**Assembly Isometric View:**
<img width="794" height="1349" alt="image" src="https://github.com/user-attachments/assets/2121dca9-65ce-4f07-b0c8-5ece16c879bf" />

**Entire Assembly Cross-Section:**
<img width="696" height="1348" alt="image" src="https://github.com/user-attachments/assets/fb392856-6cf9-4c93-a5d9-5d7bc4d9e653" />

**Motor Shaft–Coupler–Leadscrew Cross-Section:**
<img width="974" height="445" alt="image" src="https://github.com/user-attachments/assets/8e40cefa-355c-4781-a2ee-33f384977b89" />

**Crosshead–Lead Screw–Flange–Threaded Nut Cross-Section:**
<img width="974" height="368" alt="image" src="https://github.com/user-attachments/assets/80fef450-f91f-479e-a58b-904c18f71f0d" />

**Floating Bearing Mount–Lead Screw Cross-Section:**
<img width="974" height="453" alt="image" src="https://github.com/user-attachments/assets/05edcf3e-703c-4675-b9c5-7389f96612b3" />

--------

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

## For 2157 Students 

<img width="3919" height="3024" alt="IMG_3186" src="https://github.com/user-attachments/assets/a76062d7-4d03-47db-9711-282cfca667f2" />
<img width="3808" height="2986" alt="IMG_3185" src="https://github.com/user-attachments/assets/f8d78a17-d516-4d93-9f73-d64279c0d846" />
<img width="3646" height="2844" alt="IMG_3184" src="https://github.com/user-attachments/assets/3f32bc4a-3f6f-4b3b-8157-961ce29ab9eb" />
<img width="3683" height="2922" alt="IMG_3183" src="https://github.com/user-attachments/assets/d33d283d-ad8a-4db4-8898-e29c75691032" />
<img width="3903" height="3024" alt="IMG_3181" src="https://github.com/user-attachments/assets/d48493b5-f559-4a28-bd9c-7299c2e156ef" />
<img width="3903" height="3024" alt="IMG_3173" src="https://github.com/user-attachments/assets/7a0e886a-73b7-4969-9ed8-70de05887db8" />
<img width="3619" height="2750" alt="IMG_3172" src="https://github.com/user-attachments/assets/a9283353-0382-4a0b-b3da-5f91e0d27797" />


## CAD Files & Bill of Materials Downloads

* [1329K102_Precision Acme Flange.SLDPRT](1329K102_Precision%20Acme%20Flange.SLDPRT){ download }
* [4855N17_DC Gearmotor.SLDPRT](4855N17_DC%20Gearmotor.SLDPRT){ download }
* [5537T038_T-Slotted Framing Bottom Frame.SLDPRT](5537T038_T-Slotted%20Framing%20Bottom%20Frame.SLDPRT){ download }
* [5537T038_T-Slotted Framing.SLDPRT](5537T038_T-Slotted%20Framing.SLDPRT){ download }
* [5537T46_T-Slotted Framing.SLDPRT](5537T46_T-Slotted%20Framing.SLDPRT){ download }
* [5537T586_T-Slotted Framing.SLDPRT](5537T586_T-Slotted%20Framing.SLDPRT){ download }
* [5537T665_T-Slotted Framing(1).SLDPRT](5537T665_T-Slotted%20Framing(1).SLDPRT){ download }
* [5537T665_T-Slotted Framing.SLDPRT](5537T665_T-Slotted%20Framing.SLDPRT){ download }
* [95072A209_Precision Acme Externally Threaded Nut.SLDPRT](95072A209_Precision%20Acme%20Externally%20Threaded%20Nut.SLDPRT){ download }
* [99030A005_1018 Carbon Steel Precision Acme Lead Screw(2).SLDPRT](99030A005_1018%20Carbon%20Steel%20Precision%20Acme%20Lead%20Screw(2).SLDPRT){ download }
* [A11 Assemble Final Assembly.SLDASM](A11%20Assemble%20Final%20Assembly.SLDASM){ download }
* [BOM cost for Assignment #11.xlsx](BOM%20cost%20for%20Assignment%20%2311.xlsx){ download }
* [Coupling.SLDPRT](Coupling.SLDPRT){ download }
* [Crosshead.SLDPRT](Crosshead.SLDPRT){ download }
* [Floating Bearing Mount.SLDPRT](Floating%20Bearing%20Mount.SLDPRT){ download }
* [Motor Mount Plate.SLDPRT](Motor%20Mount%20Plate.SLDPRT){ download }

  ---

## Resources

### Open Source Tensile Testers
1. [Design, Manufacture, and Testing of an Open Source Tensile Testing Machine for Hands on Learning](https://www.google.com/url?q=https://repositum.tuwien.at/bitstream/20.500.12708/200949/1/Demmel%2520Stella%2520-%25202024%2520-%2520Design%2520manufacturing%2520and%2520testing%2520of%2520an%2520open-source...pdf&sa=D&source=editors&ust=1795053478262061&usg=AOvVaw1JqWhBIf7GtXMMAKCFx4lX)
2. [Low Cost Universal Testing Machine](https://www.google.com/url?q=https://hackaday.io/project/192166-low-cost-universal-tensile-testing-machine&sa=D&source=editors&ust=1795053478262161&usg=AOvVaw0l4grJGxTiQl_J7ZoQn7UN)
3. [Free Loader](https://www.google.com/url?q=https://www.creativemachineslab.com/freeloader.html&sa=D&source=editors&ust=1795053478262235&usg=AOvVaw1kqqqd_-upsxZ26OUj4Y4t)

### Frame & Other Components
4. [Metric Profiles for T-Slot Framing](https://www.google.com/url?q=https://www.grainger.com/category/material-handling/structural-framing-systems/t-slot-framing-systems/profiles-for-t-slot-framing/metric-profiles-for-t-slot-framing?attrs%3DRelative%2BProfile%2BWeight%257CHeavy~~Series%257C40%2BSeries%26filters%3Dattrs&sa=D&source=editors&ust=1795053478262439&usg=AOvVaw2wpWTqmsErInxuIXOFdplK)
5. [Connectors for T-Slot Framing](https://www.google.com/url?q=https://www.grainger.com/category/material-handling/structural-framing-systems/t-slot-framing-systems/connectors-for-t-slot-framing?categoryIndex%3D3&sa=D&source=editors&ust=1795053478262565&usg=AOvVaw1tuMhwu7scbuSn7wNsGChd)
6. [Load Cell](https://www.google.com/url?q=https://assets.dwyeromega.com/spec/DS-LC103B.pdf&sa=D&source=editors&ust=1795053478262641&usg=AOvVaw1cRHRqQ1LfErGN4BHe4BuJ)
7. [Leadscrew and Nut/Flange](https://www.google.com/url?q=https://www.mcmaster.com/products/acme-lead-screws/precision-lead-screws-and-nuts-1~/precision-acme-lead-screws-and-nuts-6/nut-type~externally-threaded/nut-type~flange/material~bronze-1/&sa=D&source=editors&ust=1795053478262773&usg=AOvVaw1kV47_oEjfioRiMjJis_Bq)
8. [Lead Screw](https://www.google.com/url?q=https://www.roton.com/products/acme-lead-screws-nuts/engineering-data/?utm_source%3Dchatgpt.com&sa=D&source=editors&ust=1795053478262864&usg=AOvVaw3n5HrATS-cUOmncFwXis1D)

### Engineering Theory
9. [Column Buckling](https://www.google.com/url?q=https://mechanicalc.com/reference/column-buckling&sa=D&source=editors&ust=1795053478263004&usg=AOvVaw1eo1vOQReIZxHn1bgV6FCJ)
