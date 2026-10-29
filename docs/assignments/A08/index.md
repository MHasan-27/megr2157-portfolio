# Engineering Design Report: Shaft Analysis

## 1. Design of the Shafts

### a. Input Shaft (Power-Transmission)

#### i. Knowns and Unknowns

* **Knowns:**
* Output Torque ($T_{out}$): $1.25\text{ in-lbf}$
* Output Speed ($N_{out}$): $1100\text{ RPM}$
* Gear Ratio ($N_{gear}:N_{pinion}$): $24:9$ ($48\text{ teeth}:18\text{ teeth}$)
* Input Speed ($N_{in}$): $1100 \times (24/9) \approx 2933.33\text{ RPM}$
* Input Torque ($T_{in}$): $1.25 \times (9/24) = 0.46875\text{ in-lbf}$
* Input Shaft Diameter ($d_{in}$): $0.125\text{ in}$
* Input Shaft Length ($L_{in}$): $1.0\text{ in}$
* Pinion Material: Brass (McMaster-Carr 7880K19)


* **Unknowns:**
* Transmitted Horsepower ($P_{in}$)
* Allowable Horsepower capacity ($P_{allow,in}$)
* Minimum required diameter ($D_{req,in}$)
* Maximum torsional shear stress ($\tau_{in}$)
* Adequacy of $d_{in} = 0.125\text{ in}$



#### ii. Free-Body Diagram (FBD) of Input Shaft



```

#### iii. Equations & Algebraic Modeling

* **Transmitted Power ($P_{in}$):**

$$P_{in} = \frac{T_{in} \cdot N_{in}}{63025}$$


* **Maximum Torsional Shear Stress ($\tau_{in}$):**

$$\tau_{in} = \frac{16 T_{in}}{\pi d_{in}^3}$$


* **Minimum Required Diameter ($D_{req,in}$):**

$$D_{req,in} = \left( \frac{16 T_{in}}{\pi \tau_{allow}} \right)^{1/3}$$



#### v. Conclusion & Recommendation

* **Verdict:** Sufficient.
* **Explanation:** The minimum required diameter ($D_{req,in} \approx 0.065\text{ in}$) is significantly smaller than the provided shaft diameter ($d_{in} = 0.125\text{ in}$). Furthermore, the power transmitted ($0.022\text{ hp}$) is well within the shaft's allowable power capacity ($0.1508\text{ hp}$).
* **Recommendation:** $d_{in} = 0.125\text{ in}$ is fully adequate; no diameter increase is required.

---

### b. Output Shaft (Short Shaft)

#### i. Knowns and Unknowns

* **Knowns:**
* Output Torque ($T_{out}$): $1.25\text{ in-lbf}$
* Output Speed ($N_{out}$): $1100\text{ RPM}$
* Output Shaft Diameter ($d_{out}$): $0.250\text{ in}$
* Output Shaft Length ($L_{out}$): $1.0\text{ in}$
* Output Gear Material: Brass (McMaster-Carr 7880K24)


* **Unknowns:**
* Transmitted Horsepower ($P_{out}$)
* Allowable Horsepower capacity ($P_{allow,out}$)
* Minimum required diameter ($D_{req,out}$)
* Maximum torsional shear stress ($\tau_{out}$)
* Adequacy of $d_{out} = 0.250\text{ in}$



#### ii. Free-Body Diagram (FBD) of Output Shaft

```text
╱
         └─────────┘
         |<-- d -->| (d = 0.250 in)

```

#### iii. Equations & Algebraic Modeling

* **Transmitted Power ($P_{out}$):**

$$P_{out} = \frac{T_{out} \cdot N_{out}}{63025}$$


* **Maximum Torsional Shear Stress ($\tau_{out}$):**

$$\tau_{out} = \frac{16 T_{out}}{\pi d_{out}^3}$$


* **Minimum Required Diameter ($D_{req,out}$):**

$$D_{req,out} = \left( \frac{16 T_{out}}{\pi \tau_{allow}} \right)^{1/3}$$



#### v. Conclusion & Recommendation

* **Verdict:** Sufficient.
* **Explanation:** The required minimum diameter ($D_{req,out} \approx 0.09125\text{ in}$) is far below the actual shaft diameter ($d_{out} = 0.250\text{ in}$). The allowable power capacity ($0.4523\text{ hp}$) also easily exceeds the transmitted power ($0.022\text{ hp}$).
* **Recommendation:** $d_{out} = 0.250\text{ in}$ is fully adequate; no diameter change is required.
