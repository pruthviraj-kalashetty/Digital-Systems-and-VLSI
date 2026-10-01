# ◈ Timing Paths

[![Stage](https://img.shields.io/badge/Timing--and--STA-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Timing%20Paths-orange.svg)](#)

This module introduces the fundamental concepts of timing paths in synchronous digital systems. It covers timing path structure, launch and capture elements, data paths, clock paths, and common timing path types.

These concepts are essential for understanding how data propagates between timing points and form a critical foundation for Static Timing Analysis (STA), timing constraints, setup and hold analysis, and timing closure.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the fundamental concept of a timing path.
- Identify launch and capture elements in a timing path.
- Understand the difference between data paths and clock paths.
- Analyze register-to-register timing paths.
- Understand input-to-register timing paths.
- Understand register-to-output timing paths.
- Understand input-to-output timing paths.
- Build a strong foundation for Static Timing Analysis (STA).

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-Timing-Path-Introduction.md`](./01-Timing-Path-Introduction.md)** | Introduction to timing paths and the basic elements involved in timing analysis. |
| **[`02-Launch-and-Capture-Elements.md`](./02-Launch-and-Capture-Elements.md)** | Launch and capture elements and their role in transferring data between timing points. |
| **[`03-Data-Path.md`](./03-Data-Path.md)** | Data propagation path between source and destination timing elements. |
| **[`04-Clock-Path.md`](./04-Clock-Path.md)** | Clock propagation path and clock arrival at sequential elements. |
| **[`05-Register-to-Register-Path.md`](./05-Register-to-Register-Path.md)** | Timing path between a launch register and a capture register. |
| **[`06-Input-to-Register-Path.md`](./06-Input-to-Register-Path.md)** | Timing path from an external input to a sequential capture element. |
| **[`07-Register-to-Output-Path.md`](./07-Register-to-Output-Path.md)** | Timing path from a sequential launch element to an external output. |
| **[`08-Input-to-Output-Path.md`](./08-Input-to-Output-Path.md)** | Timing path between an external input and an external output. |

---

## 🌲 Directory Structure
```
03-Timing-Paths/
├── 01-Timing-Path-Introduction.md
├── 02-Launch-and-Capture-Elements.md
├── 03-Data-Path.md
├── 04-Clock-Path.md
├── 05-Register-to-Register-Path.md
├── 06-Input-to-Register-Path.md
├── 07-Register-to-Output-Path.md
└── 08-Input-to-Output-Path.md
```
---

## 🛠️ Core Concepts Covered

### 1. Timing Path Introduction

Understand a timing path as the complete path through which a signal travels between defined timing points.

A typical synchronous timing path contains:

**Launch Element → Data Path → Capture Element**


### 2. Launch and Capture Elements

Understand the roles of launch and capture elements in synchronous timing analysis.

The **launch element** starts data propagation, while the **capture element** receives the data at the destination timing point.


### 3. Data Path

Understand the path followed by data from its source to its destination.

A data path may contain:

- Sequential elements
- Combinational logic
- Logic gates
- Interconnects


### 4. Clock Path

Understand how the clock signal propagates from its source through the clock distribution network to the sequential elements.

Clock paths are important for analyzing:

- Clock arrival time
- Clock skew
- Clock latency
- Setup timing
- Hold timing


### 5. Register-to-Register Path

Understand the common synchronous timing path between two registers.

The basic structure is:

**Launch Register → Combinational Logic → Capture Register**

This is one of the primary path types analyzed during STA.


### 6. Input-to-Register Path

Understand timing paths that begin at an external input and terminate at a sequential element.

The basic structure is:

**Input → Combinational Logic → Register**

This path type is analyzed using appropriate input timing constraints.


### 7. Register-to-Output Path

Understand timing paths that begin at a sequential element and terminate at an external output.

The basic structure is:

**Register → Combinational Logic → Output**

This path type is analyzed using appropriate output timing constraints.


### 8. Input-to-Output Path

Understand timing paths that begin at an external input and terminate at an external output.

The basic structure is:

**Input → Combinational Logic → Output**

This represents a combinational timing path without a sequential launch or capture element.


### 9. Timing Paths and STA

These timing path concepts provide the foundation for studying:

- Static Timing Analysis (STA)
- Setup Analysis
- Hold Analysis
- Arrival Time
- Required Time
- Slack
- Critical Paths
- Timing Constraints
- Timing Closure

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics and Timing Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
