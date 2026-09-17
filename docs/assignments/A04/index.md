# A4: Motor Mount Assignment

## CAD Files
[Download SolidWorks Model (SLDPRT)](https://github.com/MHasan-27/megr2157-portfolio/raw/main/docs/assignments/A04/A%204%20Motor%20Mount.SLDPRT)
[Download SolidWorks Drawing (SLDDRW)](https://github.com/MHasan-27/megr2157-portfolio/raw/main/docs/assignments/A04/A%204%20Motor%20Mount.SLDDRW)

---

## Objective
The objective of this project is to design a 3D-printable motor mount that attaches a Brushed 24V DC Gear Motor with a 99.5:1 Planetary Gearbox to a rigid wall (Wall A). The design must meet two structural constraints: holding an applied shaft load of P = 300 N with a Safety Factor of 3 against yield strength, and limiting maximum deflection at the free end to 0.30 mm.

---

## Analyze

### Feature 1: Motor Attachment

#### All Knowns and Unknowns
* **Knowns:**
  * Shaft Load: P = 300 N
  * Maximum allowable deflection: delta_max = 0.30 mm = 0.0003 m
  * Safety Factor: SF = 3
  * Feature length: L1 = 50 mm = 0.050 m
  * Material (PLA): Yield Strength sigma_y = 60 MPa, Young's Modulus E = 3.5 GPa
* **Unknowns:**
  * Allowable Bending Stress: sigma_allow
  * Cross-sectional geometry: Width (b1) and Height (h1)

#### Feature 1 FBD
Model Feature 1 as a horizontal cantilever beam of length L1 = 50 mm fixed at x = 0 and free at x = L1. A downward transverse load P = 300 N acts at x = L1. At x = 0, the reaction force is R_y1 = 300 N and the reaction moment is M1 = P * L1 = 15 N*m.

#### Symbolically Solving for Equations to find b1 and h1
* Allowable Stress:
  sigma_allow = sigma_y / SF = 60 MPa / 3 = 20 MPa = 20,000,000 Pa
* Yield Strength Criterion:
  sigma_max = (6 * P * L1) / (b1 * h1^2) <= sigma_allow
  b1 * h1^2 >= (6 * P * L1) / sigma_allow
* Deflection Limit Criterion:
  delta_max = (4 * P * L1^3) / (E * b1 * h1^3) <= 0.0003 m
  b1 * h1^3 >= (4 * P * L1^3) / (E * delta_max)

#### Numerically Solving for Equations to find b1 and h1
Assuming a square cross-section (b1 = h1):
* Based on Yield Stress:
  h1^3 >= (6 * 300 * 0.050) / 20,000,000 = 0.0000045 m^3
  h1 >= 0.01651 m = 16.51 mm
* Based on Deflection Limit:
  h1^4 >= (4 * 300 * 0.050^3) / (3,500,000,000 * 0.0003) = 0.00000014286 m^4
  h1 >= 0.01943 m = 19.43 mm
* Governing Dimension: Deflection governs (19.43 mm > 16.51 mm). Selected baseline b1 = h1 = 20.0 mm.

---

### Feature 2: Wall Attachment

#### All Knowns and Unknowns
* **Knowns:**
  * Transferred shaft load: P = 300 N
  * Maximum allowable deflection: delta_max = 0.30 mm = 0.0003 m
  * Safety Factor: SF = 3
  * Feature length: L2 = 44 mm = 0.044 m
  * Material (PLA): sigma_y = 60 MPa, E = 3.5 GPa
* **Unknowns:**
  * Allowable Stress: sigma_allow
  * Cross-section dimensions: Width (b2) and Height (h2)

#### Feature 2 FBD
Model Feature 2 as a vertical cantilever extending from rigid Wall A at x = 0 to Feature 1 at x = L2. Transferred load P = 300 N acts at x = L2. At Wall A (x = 0), vertical reaction force R_y2 = 300 N and reaction moment M2 = P * L2 = 13.2 N*m.

#### Symbolically Solving for b2 and h2 With Respect to Yield Strength
* sigma_max = (6 * P * L2) / (b2 * h2^2) <= sigma_allow
* b2 * h2^2 >= (6 * P * L2) / sigma_allow

#### Symbolically Solving for b2 and h2 With Respect to Deflection
* delta_max = (4 * P * L2^3) / (E * b2 * h2^3) <= 0.0003 m
* b2 * h2^3 >= (4 * P * L2^3) / (E * delta_max)

#### Numerically Solving for b2 and h2 With Respect to Yield Strength
Assuming a square cross-section (b2 = h2):
* h2^3 >= (6 * 300 * 0.044) / 20,000,000 = 0.00000396 m^3
* h2 >= 0.01582 m = 15.82 mm

#### Numerically Solving for b2 and h2 With Respect to Deflection
* h2^4 >= (4 * 300 * 0.044^3) / (3,500,000,000 * 0.0003) = 0.00000009736 m^4
* h2 >= 0.01766 m = 17.66 mm
* Governing Dimension: Deflection governs (17.66 mm > 15.82 mm). Selected baseline b2 = h2 = 20.0 mm.

---

## Free Body Diagram & Concepts

![A4 Free Body Diagram](A%204%20FBD.png)

*Figure 1: Free Body Diagram (FBD) showing load transfer and boundary conditions for Feature 1 and Feature 2.*

---

## CAD Model (Parametric)

The 3D CAD model features a main plate thickness of 10.0 mm, a width of 50.0 mm, Feature 1 length of 50.0 mm, and Feature 2 length of 50.0 mm. Stiffening side gussets were designed at the 90-degree corner joint to increase stiffness and keep the total deflection below 0.30 mm.

* Clearance Holes: 3.4 mm clearance holes for M3 mounting bolts on Feature 2, and central motor output shaft/bolt mounting pattern on Feature 1.


![3D Motor Mount CAD Model](Front%20View.JPG)

*Figure 2: Parametric 3D CAD model of the motor mount with gussets and mounting clearance holes.*

---

## 2157 Drawings

An ASME-compliant engineering drawing was generated directly from the 3D CAD model.

* **Views:** Front View, Right Side View, Top View, and an un-dimensioned Isometric View in the upper-right corner.
* **Standards:** Third-angle projection with proper centerlines, hidden lines, and fully dimensioned features.
* **Title Block:** Complete with Name, Date, Part Title ("A4 Motor Mount"), Scale (1:1), and Material (PLA).

![2157 Multiview Drawing Sheet](A%204%20Motor%20Mount%20Panel%20View.JPG)

*Figure 3: ASME multiview drawing layout including Front, Right Side, Top, and Isometric views.*

---

## Appendix: Research Links

1. [Spur Gear Motor Mount Design Guidelines - McMaster-Carr](https://www.mcmaster.com)
2. [Design for Additive Manufacturing & Cantilever Brackets - Hubs](https://www.hubs.com)
3. [Beam Bending Deflection & Stress Equations - Engineering Toolbox](https://www.engineeringtoolbox.com)
4. AI used to format Markdown, embed images, and link CAD files.
5. https://instructure.charlotte.edu/courses/272052/assignments/2902671?module_item_id=7950956
6. https://uncc.instructure.com/eportfolios/2995/Home/Design_a_Simple_Machine

---

## Lessons Learned & Process Notes

* **Time Spent:** About 8 hours total (3 hours for FBDs and hand calculations, 2.5 hours for parametric CAD modeling and gusset revisions, 2.5 hours for 2157 drawing sheet setup and portfolio setup).
* **Mistakes & Insights:** Initial calculations showed that a flat 10 mm plate alone would deflect over 0.70 mm under the 300 N load. Adding 6 mm side gussets provided the necessary structural stiffness to satisfy the 0.30 mm deflection limit without making the entire body excessively bulky.
