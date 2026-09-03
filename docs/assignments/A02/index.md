# MEGR 2156 — Assignment 2: Truss Stress Design

##  Introduction

The objective of this project is to design a lightweight planar truss that can support the applied loads while maintaining the required safety factor. The truss will be analyzed using free-body diagrams and static equilibrium equations to determine the internal forces in each member. AISI 1020 steel will be used in the SolidWorks model because A500 structural steel is not available in the standard SolidWorks material library.

---

##  Material Selection

The assignment specifies A500 structural steel for the truss. However, A500 was not available as a default material option in SolidWorks. Per the assignment guidelines allowing an alternative steel type when A500 is unavailable, AISI 1020 steel was selected as the substitute material.

The mechanical properties of AISI 1020 provided by SolidWorks will be used for all stress calculations. The same material will be assigned to the 3D CAD model to ensure an accurate comparison between the analytical weight and SolidWorks mass properties.






##  CAD Model and Mass Comparison

The entire truss was modeled as a single part in SolidWorks using $15\text{ mm} \times 15\text{ mm}$ square bars. Pins were modeled as $6\text{ mm}$ diameter cylinders, and **AISI 1020** material was assigned.

### SolidWorks Mass Properties
* **Mass:** $\approx 8.1\text{ kg}$ *(Note: Original uncorrected density yielded $8.1\text{ kg}$; applying the corrected density brings it closer to the analytical value)*
* **Difference Explanation:** The variance is caused by extra material overlapping at the joints and minor geometric differences between the idealized line lengths and the actual 3D model geometry.

### Comparison Statement
The hand calculation predicted a mass of $5.52\text{ kg}$, whereas SolidWorks reported a higher mass due to joint material overlaps and modeling details. Both values are within the same order of magnitude, confirming that the analytical sizing method is reasonable.

### SimulationXpress Note
An initial SimulationXpress run showed stresses exceeding yield because the applied loads and cross-section initially defined in the study did not match the final design values. After correcting the applied load to $20\text{ kN}$ and confirming the $15\text{ mm} \times 15\text{ mm}$ section, the maximum stress fell well below the allowable stress threshold of approximately $100.5\text{ MPa}$.

---

##  Engineering Lessons Learned

* **Governing Member Sizing:** The member experiencing the highest axial force dictates the cross-sectional area for all other members since the design requirements specify identical profiles throughout the structure.
* **Structural Determinacy:** Zero-force members still contribute to geometric stability and structural rigidity, making their inclusion necessary to maintain determinacy.
* **Impact of Safety Factors:** Applying a safety factor of $3.5$ on yield strength significantly increases the required cross-sectional area compared to sizing purely for static load capacity.
* **Analytical vs. CAD Mass:** CAD-calculated mass is typically higher than simple theoretical predictions ($\text{Volume} = \text{Length} \times \text{Area}$) due to material overlaps at intersecting joints and additional connection features.
* **Material Substitutions:** When a specified material is omitted from the CAD software library, a comparable alloy (such as AISI 1020) can be substituted provided the yield strength and density values are accurately documented.
* **FEA Verification:** Simulation results must be cross-checked against analytical allowable stresses to prevent false failure indications resulting from improper boundary conditions or setup errors.

---

##  Time and Process Notes

| Task Phase | Estimated Duration |
| :--- | :--- |
| **Geometry Selection & Force Analysis** | ~2.0 hours |
| **Cross-Section & Pin Sizing** | ~1.0 hour |
| **SolidWorks Modeling & Mass Properties** | ~2.0 hours |
| **SimulationXpress Setup & Corrections** | ~1.5 hours |
| **Portfolio Documentation** | ~2.0 hours |
| **Total Estimated Time** | **8–9 hours** |

> **AI Assistance Disclosure:** Generative AI assistance was utilized solely to structure the Markdown format for GitHub and guide SolidWorks modeling procedures. 
