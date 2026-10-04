# ◈ RTL to GDSII Flow

[![Stage](https://img.shields.io/badge/VLSI--Fundamentals-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-RTL%20to%20GDSII%20Flow-orange.svg)](#)

This module introduces the complete RTL-to-GDSII flow used in digital ASIC design. It covers the major stages required to transform a design specification into a physical layout suitable for semiconductor manufacturing.

The flow connects front-end design activities such as specification, RTL coding, functional verification, and logic synthesis with back-end implementation activities such as floorplanning, placement, clock-tree synthesis, routing, Static Timing Analysis (STA), physical verification, and GDSII generation.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the complete RTL-to-GDSII design flow.
- Understand the purpose of design specification.
- Explain the role of RTL coding in ASIC design.
- Understand functional verification before physical implementation.
- Understand logic synthesis and gate-level netlist generation.
- Understand floorplanning and placement.
- Understand Clock Tree Synthesis (CTS).
- Understand routing and physical interconnect implementation.
- Understand the role of Static Timing Analysis (STA).
- Understand physical verification before manufacturing.
- Understand GDSII as the final physical layout representation.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-Specification.md`](./01-Specification.md)** | Definition of design requirements, functionality, interfaces, performance targets, and implementation constraints. |
| **[`02-RTL-Coding.md`](./02-RTL-Coding.md)** | Description of digital hardware behavior and structure using synthesizable RTL code. |
| **[`03-Functional-Verification.md`](./03-Functional-Verification.md)** | Verification of RTL functionality through simulation, testbenches, and functional checks. |
| **[`04-Logic-Synthesis.md`](./04-Logic-Synthesis.md)** | Conversion of RTL into an optimized gate-level netlist using technology libraries and design constraints. |
| **[`05-Floor-planning.md`](./05-Floor-planning.md)** | Initial physical organization of the design including die/core area, major blocks, I/O, and power considerations. |
| **[`06-Placement.md`](./06-Placement.md)** | Placement of standard cells within the physical design area while considering timing, congestion, and area. |
| **[`07-Clock-Tree-Synthesis.md`](./07-Clock-Tree-Synthesis.md)** | Construction and optimization of the clock distribution network to deliver clock signals to sequential elements. |
| **[`08-Routing.md`](./08-Routing.md)** | Creation of physical connections between placed cells and blocks while satisfying design constraints. |
| **[`09-STA.md`](./09-STA.md)** | Timing analysis used to verify setup, hold, and other timing requirements across the implemented design. |
| **[`10-Physical-Verification.md`](./10-Physical-Verification.md)** | Verification of the physical layout against design rules and intended circuit connectivity. |
| **[`11-GDSII.md`](./11-GDSII.md)** | Generation of the final GDSII layout database representing the physical design for manufacturing. |

---

## 🌲 Directory Structure

[04]-RTL-to-GDSII-Flow/
├── 01-Specification.md
├── 02-RTL-Coding.md
├── 03-Functional-Verification.md
├── 04-Logic-Synthesis.md
├── 05-Floor-planning.md
├── 06-Placement.md
├── 07-Clock-Tree-Synthesis.md
├── 08-Routing.md
├── 09-STA.md
├── 10-Physical-Verification.md
└── 11-GDSII.md

---

## 🛠️ Core Concepts Covered

### 1. Design Specification

Understand the starting point of the ASIC design flow, where the required functionality and design constraints are defined.

Key concepts include:

- Functional requirements
- Interfaces
- Performance targets
- Power requirements
- Area requirements
- Design constraints

### 2. RTL Coding

Understand how the specified functionality is translated into synthesizable RTL.

Important concepts include:

- Verilog/SystemVerilog
- Combinational logic
- Sequential logic
- FSMs
- Datapaths
- Control logic
- Synthesizable RTL

### 3. Functional Verification

Understand how the RTL implementation is verified before synthesis and physical implementation.

Major activities include:

- Testbench development
- Stimulus generation
- Simulation
- Functional checking
- Debugging
- Coverage

### 4. Logic Synthesis

Understand how RTL is transformed into a gate-level netlist using standard-cell libraries and design constraints.

Key concepts include:

- RTL elaboration
- Logic optimization
- Technology mapping
- Standard cells
- Gate-level netlist
- Timing constraints

### 5. Floorplanning

Understand the initial physical organization of the synthesized design.

Important considerations include:

- Die and core area
- Standard-cell regions
- Macro placement
- I/O placement
- Power distribution
- Routing resources

### 6. Placement

Understand how standard cells are physically positioned within the design area.

Placement aims to achieve a suitable balance between:

- Timing
- Area
- Routing congestion
- Wirelength
- Power

### 7. Clock Tree Synthesis

Understand how the clock distribution network is created and optimized for sequential elements.

Key concepts include:

- Clock sources
- Clock buffers
- Clock latency
- Clock skew
- Clock insertion delay
- Clock-tree balancing

### 8. Routing

Understand how physical metal connections are created between cells and blocks after placement.

Routing includes:

- Global routing
- Detailed routing
- Metal layers
- Signal connections
- Congestion management
- Design-rule considerations

### 9. Static Timing Analysis

Understand how timing is analyzed after implementation to verify that the design satisfies its timing requirements.

Important concepts include:

- Timing paths
- Setup analysis
- Hold analysis
- Arrival time
- Required time
- Slack
- Timing violations

### 10. Physical Verification

Understand how the physical layout is checked before final layout generation and manufacturing.

Important checks include:

- Design Rule Check (DRC)
- Layout Versus Schematic (LVS)
- Connectivity verification
- Physical design-rule compliance

### 11. GDSII Generation

Understand GDSII as the final physical layout database generated from the completed ASIC implementation.

The overall flow can be summarized as:

**Specification → RTL Coding → Functional Verification → Logic Synthesis → Floorplanning → Placement → CTS → Routing → STA → Physical Verification → GDSII**

This flow represents the transition from functional hardware description to physical chip layout.

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics and Timing Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
