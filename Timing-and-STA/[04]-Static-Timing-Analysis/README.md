# ◈ Static Timing Analysis

[![Stage](https://img.shields.io/badge/Timing--and--STA-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Static%20Timing%20Analysis-orange.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Static%20Timing%20Analysis-orange.svg)](#)

This module introduces the fundamental concepts of Static Timing Analysis (STA), a method used to analyze the timing behavior of digital designs without requiring functional simulation. It covers timing graphs and paths, setup and hold analysis, arrival time, required time, slack, and timing violations.

These concepts are essential for understanding timing verification of synchronous digital systems and form a critical foundation for timing constraints, timing closure, and ASIC front-end design.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the fundamental concept of Static Timing Analysis (STA).
- Differentiate between STA and simulation-based timing analysis.
- Understand timing graphs and timing paths.
- Analyze setup and hold timing requirements.
- Understand arrival time and required time.
- Calculate and interpret timing slack.
- Identify setup and hold timing violations.
- Build a strong foundation for timing closure and timing analysis.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-Introduction-to-STA.md`](./01-Introduction-to-STA.md)** | Introduction to Static Timing Analysis and its role in digital design timing verification. |
| **[`02-STA-vs-Simulation.md`](./02-STA-vs-Simulation.md)** | Comparison between Static Timing Analysis and simulation-based timing verification. |
| **[`03-Timing-Graph-and-Paths.md`](./03-Timing-Graph-and-Paths.md)** | Timing graphs, timing points, and timing paths used during STA. |
| **[`04-Setup-Analysis.md`](./04-Setup-Analysis.md)** | Setup timing analysis and verification of data arrival before the capture edge. |
| **[`05-Hold-Analysis.md`](./05-Hold-Analysis.md)** | Hold timing analysis and verification of data stability after the capture edge. |
| **[`06-Arrival-Time.md`](./06-Arrival-Time.md)** | Arrival time and the time at which data reaches a timing point. |
| **[`07-Required-Time.md`](./07-Required-Time.md)** | Required time and the latest or earliest allowable data arrival for correct operation. |
| **[`08-Slack-Analysis.md`](./08-Slack-Analysis.md)** | Timing slack, its interpretation, and its relationship to timing requirements. |
| **[`09-Timing-Violations.md`](./09-Timing-Violations.md)** | Setup and hold violations, their causes, and their impact on timing closure. |

---

## 🌲 Directory Structure

04-Static-Timing-Analysis/
├── 01-Introduction-to-STA.md
├── 02-STA-vs-Simulation.md
├── 03-Timing-Graph-and-Paths.md
├── 04-Setup-Analysis.md
├── 05-Hold-Analysis.md
├── 06-Arrival-Time.md
├── 07-Required-Time.md
├── 08-Slack-Analysis.md
└── 09-Timing-Violations.md

---

## 🛠️ Core Concepts Covered

### 1. Introduction to STA

Understand Static Timing Analysis as a method of verifying whether a digital design satisfies its timing requirements by analyzing signal propagation through defined timing paths.

STA is primarily used to identify timing problems without applying functional input patterns.

### 2. STA vs Simulation

Understand the difference between STA and simulation-based verification.

Key concepts include:

- Functional simulation
- Timing simulation
- Static timing analysis
- Timing coverage
- Timing verification

### 3. Timing Graph and Paths

Understand how a digital design can be represented using a timing graph containing timing points and timing paths.

A timing path represents the propagation of a signal between defined start and end points.

### 4. Setup Analysis

Understand setup analysis as the verification that data arrives sufficiently early before the active capture clock edge.

Setup analysis is used to determine whether the data has enough time to propagate through the data path.

### 5. Hold Analysis

Understand hold analysis as the verification that data remains stable for the required period after the active capture clock edge.

Hold analysis ensures that newly launched data does not reach the capture element too early.

### 6. Arrival Time

Understand arrival time as the time at which a data signal reaches a specific timing point.

Arrival time depends on factors such as:

- Launch clock
- Clock path delay
- Data path delay
- Combinational logic
- Interconnect delay

### 7. Required Time

Understand required time as the timing limit by which data must arrive at the destination to satisfy the timing requirement.

Required time is used together with arrival time to determine timing slack.

### 8. Slack Analysis

Understand slack as the difference between the required time and the actual arrival time of a signal.

A basic relationship is:

**Slack = Required Time − Arrival Time**

Slack is used to determine whether a timing path satisfies its timing requirement.

### 9. Timing Violations

Understand setup and hold violations and their impact on synchronous digital systems.

Potential effects include:

- Incorrect data capture
- Timing failures
- Reduced operating frequency
- Functional failures
- Timing closure challenges

### 10. Foundation for Timing Closure

These concepts provide the foundation for studying:

- Timing Constraints
- Setup Analysis
- Hold Analysis
- Clock Skew
- Clock Jitter
- Clock Uncertainty
- Critical Paths
- Static Timing Analysis
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
