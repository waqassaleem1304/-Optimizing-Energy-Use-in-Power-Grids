# ⚡ Optimizing Energy Use in Power Grids

**Authors:** Muhammad Waqas Saleem, Riccardo D’Alessandro, Jean Tabet

## 📖 Project Overview
This project performs a techno-economic optimization of a power network integrating **Solar PV**, **Wind Turbines**, and **Battery Energy Storage Systems (BESS)**. The goal is to minimize total grid costs while satisfying technical constraints (line limits, power balance) and environmental goals (CO2 caps).

The solution utilizes **Linear Programming (LP)** to determine the optimal generator dispatch and battery sizing for 24 hours.

## 📸 Project Snapshot & Visuals

 Optimization Heatmap
To understand the trade-offs between cost and sustainability, we simulated various combinations of **Battery Costs** and **CO2 Limits**. The heatmap below visualizes the feasible regions for high renewable integration.

<img width="1176" height="590" alt="image" src="https://github.com/user-attachments/assets/8a860c33-1486-4f40-9909-763564a47df1" />

**Figure:** Heatmap illustrating how stricter CO2 limits and lower battery costs drive the system towards higher renewable energy shares.*

## 📊 Key Results Summary

| Scenario | Battery Cost | Line Constraints | RE Share | Total Cost |
| :--- | :--- | :--- | :--- | :--- |
| **Base Case** | N/A | None | 0% | €7,986 |
| **Renewables Only** | N/A | None | 77.2% | €1,792 |
| **High-Cost Battery** | €1,500/kWh | 1.3 MW | 77.2% | €1,918 |
| **Future Tech** | **€100/kWh** | **1.3 MW** | **98.0%** | **€1,380** |

*> As shown in the table, the "Future Tech" scenario (Case 4) yields the lowest cost and highest renewable share.*

## ⚙️ Methodology
The project uses the **PuLP** library in Python to solve the optimization problem:

1.  **Objective:** Minimize $Cost_{gen} + Cost_{battery}$.
2.  **Constraints:**
    * **Nodal Balance:** Supply must equal demand at every node.
    * **Line Limits:** Power flow cannot exceed physical line capacity.
    * **Battery Logic:** Storage level depends on previous state, charge/discharge efficiency, and max capacity.
3.  **Data:** Real-world profiles for Load, PV, and Wind generation.

---
