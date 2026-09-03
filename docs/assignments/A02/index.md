# MEGR 2156 — Assignment 2: Truss Stress Design

##  Introduction

The objective of this project is to design a lightweight planar truss that can support the applied loads while maintaining the required safety factor. The truss will be analyzed using free-body diagrams and static equilibrium equations to determine the internal forces in each member. AISI 1020 steel will be used in the SolidWorks model because A500 structural steel is not available in the standard SolidWorks material library.

---

##  Material Selection

The assignment specifies A500 structural steel for the truss. However, A500 was not available as a default material option in SolidWorks. Per the assignment guidelines allowing an alternative steel type when A500 is unavailable, AISI 1020 steel was selected as the substitute material.

The mechanical properties of AISI 1020 provided by SolidWorks will be used for all stress calculations. The same material will be assigned to the 3D CAD model to ensure an accurate comparison between the analytical weight and SolidWorks mass properties.

##  Design and Solution Section

<iframe src="./A 2.pdf" width="100%" height="600px" style="border: none;">
    This browser does not support PDFs. Please download the PDF to view it: <a href="./A 2.pdf">Download PDF</a>.
</iframe>



##  3D CAD Model and Mass Comparison

We built the truss in SolidWorks using $15\text{ mm} \times 15\text{ mm}$ square bars and $6\text{ mm}$ round steel pins.

* **Hand Calculated Mass:** 5.52 kg
* **SolidWorks Mass:** 8.1 kg

**Why the difference?**
The 3D model in SolidWorks adds extra steel where the bars overlap at the corners and joints, making it heavier than simple line math.

---

##  Lessons Learned

* **Design for the Worst Case:** The single bar with the highest force decides the thickness for all bars in the frame.
* **Safety Factors Add Bulk:** Using a 3.5 safety factor makes the frame significantly thicker and heavier.
* **Real Models Weigh More:** 3D CAD models weigh more than quick hand estimates because joints use extra material.
* **Check Simulation Settings:** Always verify load values in FEA tests to ensure the software does not show false structural failures.

---

##  Time Spent

| Work Done | Time |
| :--- | :--- |
| **Force Math & Geometry Setup** | 2.0 hours |
| **Bar & Pin Sizing** | 1.0 hour |
| **SolidWorks 3D Modeling** | 2.0 hours |
| **Stress Simulation Checks** | 1.5 hours |
| **Writing Documentation** | 2.0 hours |
| **Total Time** | **8.5 hours** |
> **AI Assistance Disclosure:** Generative AI assistance was utilized solely to structure the Markdown format for GitHub and guide SolidWorks modeling procedures. 
