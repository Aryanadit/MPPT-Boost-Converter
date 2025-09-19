# Project Description: MPPT Control of 3 MW Solar PV using Boost Converter

## 1. Introduction

This project focuses on the design and simulation of a **3 MW Solar Photovoltaic (PV) system** integrated with a **DC-DC boost converter**. The system employs the **Perturb & Observe (P\&O) Maximum Power Point Tracking (MPPT) algorithm** to maximize power extraction from the PV array, with a **PID controller** ensuring voltage stability. The complete system is modeled and validated in **MATLAB/Simulink**.

---

## 2. Objectives

- Develop a **Simulink model** of a 3 MW PV system with boost converter.
- Implement **P\&O MPPT** for tracking the maximum power point.
- Design a **PID controller** to regulate converter output voltage.
- Validate the performance of the system through simulation results.

---

## 3. Methodology

### 3.1 PV System Modeling

- A **3 MW PV array** was modeled using MATLAB/Simulink PV block parameters (irradiance, temperature, Voc, Isc, Vmp, Imp).
- The output of the PV system is nonlinear and varies with irradiance and load.

### 3.2 DC-DC Boost Converter Design

- The boost converter was chosen to step up the PV voltage to the required DC bus level.
- Key equations used:

  - **Duty Cycle (D):**
    ```
    D = 1 - (Vin / Vout)
    ```
  - **Inductor Selection (L):**
    ```
    L = (Vin * D) / (ΔIL * fs)
    ```
  - **Capacitor Selection (C):**
    ```
    C = (Iout * D) / (ΔVout * fs)
    ```

### 3.3 MPPT Algorithm (P\&O)

- **Principle:** Incrementally perturb the PV voltage and observe power changes.
- **Steps:**
  1. Measure PV voltage (V) and current (I).
  2. Calculate power: `P = V × I`.
  3. Perturb voltage by small step and check change in power.
  4. If ΔP > 0, continue in the same direction. If ΔP < 0, reverse direction.
- **Advantage:** Simple and low-cost.
- **Limitation:** Oscillations around MPP.

### 3.4 PID Controller

- Used to regulate output voltage of boost converter.
- **Control law:**
$$
u(t) = K_p \cdot e(t) + K_i \int e(t) \, dt + K_d \frac{de(t)}{dt}
$$

- Ensures:
- Reduced oscillations
- Faster dynamic response
- Stable output voltage

---

## 4. Simulation Setup

- **Software:** MATLAB/Simulink
- **PV Capacity:** 3 MW
- **Converter:** Boost Converter with PWM switching
- **Control:** P\&O MPPT + PID voltage regulation
- **Inputs:** Irradiance fixed at standard test condition (STC = 1000 W/m²)

---

## 5. Results

- The P\&O MPPT algorithm successfully tracked the maximum power point.
- PID controller stabilized the output voltage, minimizing oscillations.
- The boost converter stepped up the voltage efficiently to the desired DC bus level.
- Overall system efficiency improved, ensuring near-maximum extraction of solar energy.

---

## 6. Conclusion

This project demonstrates a practical and efficient **MPPT control strategy** for large-scale PV systems. By combining **P\&O MPPT** with a **PID-controlled boost converter**, the system achieves stable voltage regulation and efficient power tracking.

**Future Scope:**
- Extend to **ANN/ANFIS-based MPPT** for faster convergence and better performance under partial shading.
- Validate performance under **dynamic irradiance and temperature conditions**.
- Comparative analysis between P\&O and AI-based MPPT algorithms.

---

## 7. Skills Demonstrated

- MATLAB/Simulink (modeling & simulation)
- Power Electronics (DC-DC converters)
- MPPT Algorithms (Perturb & Observe)
- Control Systems (PID design & tuning)
- Renewable Energy Optimization
- Algorithm Development
