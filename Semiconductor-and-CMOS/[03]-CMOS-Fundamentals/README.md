# ◈ CMOS Fundamentals & Transistor Logic

[![Stage](https://img.shields.io/badge/Stage-Semiconductor_Basics_&_CMOS-blue.svg?style=flat-square)](#)
[![Focus](https://img.shields.io/badge/Focus-CMOS_Logic_&_Circuit_Characteristics-orange.svg?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](#)

This module provides a comprehensive guide to Complementary Metal-Oxide-Semiconductor (CMOS) technology and transistor-level digital logic design. It details the operation of complementary $N$-channel and $P$-channel network topologies, static CMOS gate synthesis, transfer characteristics, voltage noise margins ($NM_H, NM_L$), dynamic switching delays, and capacitive loading constraints.

Mastering these concepts establishes the essential foundation for cell library characterization, static timing analysis (STA), ASIC standard-cell design, and sub-nanometer VLSI implementation.

---

## ⚡ CMOS Technology & Dynamics Quick Reference

| Domain / Metric | Core Formula / Rule | Physical & Circuit Description |
| :--- | :--- | :--- |
| **Pull-Up Network (PUN)** | PMOS Transistors (Parallel for NAND, Series for NOR) | Connects output $V_{out}$ to $V_{DD}$; passes strong logic '1', weak logic '0'. |
| **Pull-Down Network (PDN)** | NMOS Transistors (Series for NAND, Parallel for NOR) | Connects output $V_{out}$ to $GND$; passes strong logic '0', weak logic '1'. |
| **Noise Margins** | $NM_L = V_{IL} - V_{OL}, \quad NM_H = V_{OH} - V_{IH}$ | Quantifies circuit immunity against signal degradation and voltage noise. |
| **Propagation Delay** | $t_{pd} = \frac{t_{pHL} + t_{pLH}}{2} \approx 0.69 \cdot R_{eq} \cdot C_L$ | Average latency required for output signal to cross $50\%$ $V_{DD}$ switching threshold. |

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the fundamental principles of CMOS technology.
- Explain the complementary operation of NMOS and PMOS transistors.
- Understand the structure and operation of a CMOS inverter.
- Analyze CMOS logic gates at the transistor level.
- Understand important CMOS characteristics such as noise margin, propagation delay, rise time, and fall time.
- Explain fan-in, fan-out, and load capacitance.
- Relate CMOS device characteristics to digital circuit performance.
- Build a strong foundation for transistor-level VLSI and ASIC design.

---

## 📂 Module Contents

| Module | Core Technical Focus |
| :--- | :--- |
| **[`[01]-CMOS-Introductions`](./[01]-CMOS-Introductions/)** | CMOS fundamentals, complementary NMOS and PMOS operation, CMOS inverter, CMOS logic operation, and pull-up/pull-down networks. |
| **[`[02]-CMOS Logic-Gates`](./[02]-CMOS-Logic-Gates/)** | Transistor-level implementation of CMOS NOT, AND, NAND, OR, NOR, XOR, and XNOR gates. |
| **[`[03]-CMOS Characteristics`](./[03]-CMOS-Characteristics/)** | Noise margin, propagation delay, rise time, and fall time used to evaluate CMOS circuit performance. |
| **[`[04]-CMOS-Design-Concepts`](./[04]-CMOS-Design-Concepts/)** | Fan-in, fan-out, load capacitance, and their effects on CMOS circuit operation and performance. |

---

## 🌲 Directory Structure

```text
03-CMOS-Fundamentals/
│
├── README.md
│
├── [01]-CMOS-Introductions/
│   ├── 01-What-is-CMOS.md
│   ├── 02-Complementary-NMOS-PMOS.md
│   ├── 03-CMOS-Inverter.md
│   ├── 04-CMOS-Logic-Operation.md
│   └── 05-Pull-Up-and-Pull-Down-Networks.md
│
├── [02]-CMOS-Logic-Gates/
│   ├── 01-CMOS-NOT-Gate.md
│   ├── 02-CMOS-AND-Gate.md
│   ├── 03-CMOS-NAND-Gate.md
│   ├── 04-CMOS-OR-Gate.md
│   ├── 05-CMOS-NOR-Gate.md
│   └── 06-CMOS-XOR-XNOR-Gate.md
│
├── [03]-CMOS-Characteristics/
│   ├── 01-Noise-Margin.md
│   ├── 02-Propagation-Delay.md
│   ├── 03-Rise-Time.md
│   └── 04-Fall-Time.md
│
└── [04]-CMOS-Design-Concepts/
    ├── 01-Fan-In.md
    ├── 02-Fan-Out.md
    └── 03-Load-Capacitance.md
```

---

## 🛠️ Core Concepts Covered

### 1. CMOS Introduction

Understand Complementary Metal-Oxide-Semiconductor (CMOS) technology and its role in modern digital integrated circuits.

Key concepts include:

- CMOS fundamentals
- Complementary NMOS and PMOS operation
- CMOS inverter
- CMOS logic operation
- Pull-up network
- Pull-down network

### 2. CMOS Logic Gates

Understand how complementary PMOS and NMOS transistor networks implement fundamental Boolean logic functions.

The module covers:

- CMOS NOT Gate
- CMOS AND Gate
- CMOS NAND Gate
- CMOS OR Gate
- CMOS NOR Gate
- CMOS XOR/XNOR Gate

### 3. CMOS Characteristics

Understand the electrical and timing parameters that influence CMOS circuit reliability and performance.

Key characteristics include:

- Noise margin
- Propagation delay
- Rise time
- Fall time

### 4. CMOS Design Concepts

Understand important CMOS design parameters related to input count, output drive capability, and electrical loading.

Key concepts include:

- Fan-in
- Fan-out
- Load capacitance

### 5. CMOS Performance

Understand how transistor configuration, circuit loading, and signal transitions affect important digital circuit parameters such as:

- Switching speed
- Propagation delay
- Signal integrity
- Drive capability
- Circuit reliability

### 6. Foundation for VLSI Design

These concepts provide the foundation for studying:

- Transistor-level digital design
- CMOS standard cells
- Static CMOS logic
- ASIC design
- VLSI circuit design
- Gate-level implementation
- Digital IC performance analysis

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics and CMOS Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
