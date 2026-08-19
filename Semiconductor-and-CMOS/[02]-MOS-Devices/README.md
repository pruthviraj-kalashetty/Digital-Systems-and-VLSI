# ◈ MOS Devices & Transistor Physics

[![Stage](https://img.shields.io/badge/Stage-Semiconductor_Basics_&_CMOS-blue.svg?style=flat-square)](#)
[![Focus](https://img.shields.io/badge/Focus-MOSFET_Physics_&_Operation-green.svg?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](#)

This module introduces Metal-Oxide-Semiconductor Field-Effect Transistors (MOSFETs), the core switching elements of modern CMOS digital logic and integrated circuits. It covers device structure, $N$-channel and $P$-channel operation, $I\text{--}V$ characteristics, operating region equations (Cutoff, Linear, Saturation), and threshold voltage ($V_{th}$) formulation.

Understanding MOS devices provides the foundational device physics needed for CMOS gate synthesis, transistor-level timing analysis, and VLSI circuit layout.

---

## ⚡ MOS Devices Quick Reference

| Device / Parameter | Terminal Threshold Conditions | Drain Current ($I_D$) Characteristic Equation | Core Digital Role |
| :--- | :--- | :--- | :--- |
| **NMOS Transistor** | $V_{GS} < V_{thn}$ | $I_D = 0$ (Cutoff Region) | Pull-down switch; conducts strong logic '0', weak logic '1'. |
| **NMOS Linear** | $V_{GS} \ge V_{thn}, \quad V_{DS} < V_{GS} - V_{thn}$ | $I_D = \mu_n C_{ox} \frac{W}{L} \left[(V_{GS} - V_{thn})V_{DS} - \frac{V_{DS}^2}{2}\right]$ | Acts as a voltage-controlled variable resistor. |
| **NMOS Saturation** | $V_{GS} \ge V_{thn}, \quad V_{DS} \ge V_{GS} - V_{thn}$ | $I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{thn})^2 (1 + \lambda V_{DS})$ | Pinched-off channel; operates as a current source. |
| **PMOS Transistor** | $V_{SG} \ge \vert{}V_{thp}\vert{}$ | Complementary conduction dynamics | Pull-up switch; conducts strong logic '1', weak logic '0'. |

---

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the structure and working principle of MOSFETs.
- Differentiate between NMOS and PMOS transistors.
- Analyze the operating regions of MOS devices.
- Understand threshold voltage and its significance in transistor operation.
- Build a strong foundation for CMOS logic design and transistor-level digital circuits.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-What is MOSFET.md`](./What%20is%20MOSFET.md)** | Introduction to MOSFETs, device structure, terminals, working principle, and applications in digital electronics. |
| **[`02-NMOS.md`](./02-NMOS.md)** | Structure, operation, characteristics, and switching behavior of NMOS transistors. |
| **[`03-PMOS.md`](./03-PMOS.md)** | Structure, operation, characteristics, and switching behavior of PMOS transistors. |
| **[`04-MOS-Operation.md`](./04-MOS-Operation.md)** | MOSFET operating regions including Cutoff, Triode (Linear), and Saturation modes. |
| **[`05-Threshold-Voltage.md`](./05-Threshold-Voltage.md)** | Threshold voltage, gate control, channel formation, and its importance in MOSFET switching. |

---

## 🌲 Directory Structure

```text
02-MOS-Devices/
├── README.md
├── 01-What is MOSFET.md
├── 02-NMOS.md
├── 03-PMOS.md
├── 04-MOS-Operation.md
└── 05-Threshold-Voltage.md
```

---

## 🛠️ Core Concepts Covered

### 1. MOSFET Fundamentals

Understand the physical structure of MOSFETs, including the Gate, Source, Drain, and Body terminals, and learn how electric fields control current flow within the device.

### 2. NMOS and PMOS Transistors

Study the characteristics and operation of NMOS and PMOS transistors, their carrier types, switching behavior, and complementary operation in CMOS technology.

### 3. MOSFET Operating Regions

Learn the three primary operating regions of a MOSFET:

- **Cutoff Region** – Device is OFF and no conduction occurs.
- **Triode (Linear) Region** – Device behaves as a voltage-controlled resistor.
- **Saturation Region** – Device operates as an active switch or amplifier.

### 4. Threshold Voltage

Understand threshold voltage (V<sub>TH</sub>), channel formation, gate voltage requirements, and its impact on transistor switching speed, power consumption, and CMOS circuit performance.

### 5. CMOS Foundation

Learn how NMOS and PMOS transistors work together to form CMOS logic gates, providing high noise immunity and low static power consumption in modern VLSI systems.

---

## 📚 Reference Literature

- Neso Academy – CMOS & VLSI
- All About Electronics – MOSFET & CMOS Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
