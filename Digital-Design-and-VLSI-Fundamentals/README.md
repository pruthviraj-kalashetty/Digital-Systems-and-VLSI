# ◈ Digital Design Fundamentals Suite

[![Stage](https://img.shields.io/badge/Stage-Digital_Design_&_VLSI_Fundamentals-blue.svg?style=flat-square)](#)
[![Focus](https://img.shields.io/badge/Focus-Gate_Level_&_Sequential_Logic-orange.svg?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](#)

This repository establishes a structured foundation in digital hardware design, progressing from fundamental number systems and Boolean algebra to complex combinational datapaths, sequential elements, registers, counters, and finite-state machines (FSMs). 

It emphasizes **hardware-first architectural thinking** to build the necessary prerequisite knowledge for Verilog HDL coding, ASIC front-end design, and FPGA system development.

---

## ⚡ Digital Design Architecture Quick Reference

| Domain | Key Concepts | Hardware Primitives / Target Modules |
| :--- | :--- | :--- |
| **Boolean Logic** | DeMorgan's Theorems, SOP/POS, K-Map Minimization | Universal Gates (NAND/NOR), Prime Implicants |
| **Combinational Datapaths** | Binary Arithmetic, Decoding, Multiplexing | Ripple Carry Adders, Priority Encoders, MUX Trees |
| **Sequential Storage** | Edge-Triggering, Bistability, Metastability | D/JK/T Flip-Flops, Shift Registers (SISO/SIPO/PISO/PIPO) |
| **Control Logic** | Next-State Logic, State Encoding, Sequence Detection | Mealy and Moore Finite-State Machines (FSMs) |

---

## 🎯 Core Technical Competencies

By exploring this repository, you will build proficiency in:

- **Logic Optimization:** Boolean reduction, Karnaugh Mapping (3 & 4 variable), and don't-care optimization.
- **Combinational Design:** Adders, subtractors, MUX/DEMUX trees, priority encoders, decoders, and magnitude comparators.
- **Sequential Systems:** Clocked flip-flop mechanics, characteristic/excitation tables, shift registers (SISO, SIPO, PISO, PIPO), and counters.
- **FSM Architecture:** Mealy and Moore state machine synthesis, state transition tables, state reduction, and sequence detection logic.
- **RTL Readiness:** Understanding cycle-accurate timing and state mechanics prior to SystemVerilog/Verilog hardware description.

---

## 📂 Module Breakdown

| Module | Directory | Core Technical Focus |
| :---: | :--- | :--- |
| **`01`** | **[`[01]-Digital-Basics`](./[01]-Digital-Basics/)** | Digital vs. analog paradigms, voltage thresholds, and digital abstraction. |
| **`02`** | **[`[02]-Number-Systems`](./[02]-Number-Systems/)** | Radix conversions (Binary, Octal, Hex, Decimal) and fixed-point representation. |
| **`03`** | **[`[03]-Binary-Arithmetic`](./[03]-Binary-Arithmetic/)** | Binary math, 2's complement arithmetic, signed overflow, multiplication, and division. |
| **`04`** | **[`[04]-Binary-Codes`](./[04]-Binary-Codes/)** | Gray Code encoding/decoding, BCD, Excess-3, and ASCII representations. |
| **`05`** | **[`[05]-Boolean-Algebra`](./[05]-Boolean-Algebra/)** | Axiomatic laws, canonical forms (SOP/POS), and DeMorgan's dualities. |
| **`06`** | **[`[06]-Logic-Gates`](./[06]-Logic-Gates/)** | Primitive gates, universal logic gate synthesis (NAND/NOR), and propagation delay. |
| **`07`** | **[`[07]-Combinational-Logic`](./[07]-Combinational-Logic/)** | Truth tables, minterms/maxterms, and memoryless circuit properties. |
| **`08`** | **[`[08]-Karnaugh-Map`](./[08]-Karnaugh-Map/)** | Visual logic minimization, prime implicants, and essential prime implicants. |
| **`09`** | **[`[09]-Combinational-Circuits`](./[09]-Combinational-Circuits/)** | Modular blocks: Adders, Subtractors, MUX/DEMUX, Encoders, Decoders, Comparators. |
| **`10`** | **[`[10]-Flip-Flops`](./[10]-Flip-Flops/)** | Latches vs. Flip-Flops, SR/D/JK/T excitation profiles, and metastable behavior. |
| **`11`** | **[`[11]-Registers`](./[11]-Registers/)** | Multi-bit storage, shift registers (SISO/SIPO/PISO/PIPO), and universal shift logic. |
| **`12`** | **[`[12]-Counters`](./[12]-Counters/)** | Synchronous vs. Asynchronous ripple counters, Mod-N, Up/Down, and Ring configurations. |
| **`13`** | **[`[13]-Finite-State-Machines`](./[13]-Finite-State-Machines/)** | Mealy & Moore architectures, state diagrams, transition matrices, sequence detectors. |

---





# ◈ Digital Design Fundamentals

[![Stage](https://img.shields.io/badge/Digital--Design--and--VLSI--Fundamentals-blue.svg)](#)

This repository develops a structured foundation in digital design, progressing from fundamental digital concepts and number systems to Boolean algebra, logic gates, combinational circuits, sequential logic, counters, registers, and finite-state machines.

The learning path is designed to build the core knowledge required for Verilog HDL, RTL design, computer architecture, VLSI, FPGA, and ASIC design. Each topic focuses on understanding the underlying digital concepts before moving toward hardware description and practical RTL implementation.

---

## 📌 Repository Overview

This repository provides a rigorous, structured foundation in **digital hardware design**, serving as the prerequisite for Verilog HDL coding, ASIC Front-End design, and FPGA development. 

It spans fundamental Boolean mathematics through complex sequential finite-state machines, emphasizing **hardware-first thinking** before writing synthesizable code.

> **Primary Goal:** Master underlying gate-level and state-machine behavior to write clean, predictable, and synthesizable RTL for ASIC and FPGA targets.

---

## 🎯 Core Technical Competencies

By exploring this repository, you will build proficiency in:

- **Logic Optimization:** Boolean reduction, Karnaugh Mapping (3 & 4 variable), and don't-care optimization.
- **Combinational Design:** Adders, subtractors, MUX/DEMUX trees, priority encoders, decoders, and magnitude comparators.
- **Sequential Systems:** Clocked flip-flop mechanics, characteristic/excitation tables, shift registers (SISO, SIPO, PISO, PIPO), and counters.
- **FSM Architecture:** Mealy and Moore state machine synthesis, state transition tables, state reduction, and sequence detection logic.
- **RTL Readiness:** Understanding cycle-accurate timing and state mechanics prior to SystemVerilog/Verilog hardware description.

---

## 📂 Module Breakdown

| Module | Module Name | Core Technical Focus |
| :---: | :--- | :--- |
| **`01`** | **[`[01]-Digital-Basics`](./[01]-Digital-Basics/)** | Digital vs. analog paradigms, voltage thresholds, and digital system abstraction. |
| **`02`** | **[`[02]-Number-Systems`](./[02]-Number-Systems/)** | Radix conversions (Binary, Octal, Hex, Decimal) and fixed-point representation. |
| **`03`** | **[`[03]-Binary-Arithmetic`](./[03]-Binary-Arithmetic/)** | Binary math, 2's complement representation, multiplication, and non-restoring division. |
| **`04`** | **[`[04]-Binary-Codes`](./[04]-Binary-Codes/)** | Gray Code encoding/decoding, BCD, Excess-3, and ASCII representations. |
| **`05`** | **[`[05]-Boolean-Algebra`](./[05]-Boolean-Algebra/)** | Axiomatic laws, canonical forms (SOP/POS), and DeMorgan's dualities. |
| **`06`** | **[`[06]-Logic-Gates`](./[06]-Logic-Gates/)** | Primitive gates, universal logic gate synthesis (NAND/NOR), and propagation delay basics. |
| **`07`** | **[`[07]-Combinational-Logic`](./[07]-Combinational-Logic/)** | Truth table derivation, minterms/maxterms, and memoryless circuit properties. |
| **`08`** | **[`[08]-Karnaugh-Map`](./[08]-Karnaugh-Map/)** | Visual logic minimization, prime implicants, and essential prime implicants. |
| **`09`** | **[`[09]-Combinational-Circuits`](./[09]-Combinational-Circuits/)** | Modular building blocks: Adders, MUX, DEMUX, Encoders, Decoders, and Ripple-Carry logic. |
| **`10`** | **[`[10]-Flip-Flops`](./[10]-Flip-Flops/)** | Latches vs. Flip-Flops, SR/D/JK/T excitation profiles, and metastable behavior. |
| **`11`** | **[`[11]-Registers`](./[11]-Registers/)** | Multi-bit storage, shift registers (SISO/SIPO/PISO/PIPO), and universal shift logic. |
| **`12`** | **[`[12]-Counters`](./[12]-Counters/)** | Synchronous vs. Asynchronous ripple counters, Mod-N, Up/Down, and Ring configurations. |
| **`13`** | **[`[13]-Finite-State-Machines`](./[13]-Finite-State-Machines/)** | Mealy & Moore architectures, state diagrams, transition matrices, and sequence detectors. |

---

## 📚 Detailed Concept Syllabus

<details open>
<summary><b>1️⃣ Number Systems, Codes & Arithmetic</b></summary>

* **Base Systems:** Binary ($Radix-2$), Octal ($Radix-8$), Decimal ($Radix-10$), Hexadecimal ($Radix-16$).
* **Arithmetic Operations:** 1's & 2's Complement subtraction, overflow detection, signed arithmetic.
* **Code Conversions:** Binary-to-Gray, Gray-to-Binary, BCD-to-Excess-3, Error Detection concepts.
</details>

<details>
<summary><b>2️⃣ Boolean Minimization & Combinational Hardware</b></summary>

* **Boolean Reduction:** Canonical SOP/POS expressions, Consensus theorem, Universal gate realization.
* **K-Map Optimization:** 3-variable & 4-variable grids, Don't-Care conditions, Hazard mitigation.
* **Arithmetic & Data Path Modules:** Half/Full Adders & Subtractors, Ripple-Carry Adders, Magnitude Comparators.
* **Control Modules:** 2:1/4:1/8:1 Multiplexers, Demultiplexers, 3:8 Decoders, Priority Encoders.
</details>

<details>
<summary><b>3️⃣ Sequential Logic, Storage & State Machines</b></summary>

* **Bistable Multivibrators:** SR Latches, Level vs Edge Sensitivity, D, JK, T Flip-Flop excitation logic.
* **Storage Elements:** Serial & Parallel Shift Registers (SISO, SIPO, PISO, PIPO), Barrel Shifters.
* **Counting Circuits:** Asynchronous Ripple Counters, Synchronous Mod-N Counters, Johnson & Ring Counters.
* **State Machine Engineering:** State minimization, state assignment (One-Hot, Binary), Mealy vs. Moore timing comparisons, Overlapping/Non-overlapping Sequence Detectors.
</details>


---

## 🌲 Directory Structure

```text
Digital-Design-Fundamentals/
│
├── README.md
│
├── [01]-Digital-Basics/
│   ├── 01-Digital-vs-Analog.md
│   └── 02-Digital-System-Overview.md
│
├── [02]-Number-Systems/
│   ├── 01-Binary-System.md
│   ├── 02-Decimal-System.md
│   ├── 03-Octal-System.md
│   ├── 04-Hexadecimal-System.md
│   └── 05-Number-System-Conversion.md
│
├── [03]-Binary-Arithmetic/
│   ├── 01-Binary-Addition.md
│   ├── 02-Binary-Subtraction.md
│   ├── 03-Binary-Multiplication.md
│   └── 04-Binary-Division.md
│
├── [04]-Binary-Codes/
│   ├── 01-BCD-Code.md
│   ├── 02-Gray-Code.md
│   ├── 03-ASCII-Code.md
│   ├── 04-Excess-3-Code.md
│   ├── 05-Binary-to-Gray.md
│   └── 06-Gray-to-Binary.md
│
├── [05]-Boolean-Algebra/
│   ├── 01-Boolean-Basics.md
│   ├── 02-Boolean-Laws.md
│   ├── 03-DeMorgan-Theorem.md
│   └── 04-Boolean-Expression.md
│
├── [06]-Logic-Gates/
│   ├── 01-AND-Gate.md
│   ├── 02-OR-Gate.md
│   ├── 03-NOT-Gate.md
│   ├── 04-NAND-Gate.md
│   ├── 05-NOR-Gate.md
│   ├── 06-XOR-Gate.md
│   └── 07-XNOR-Gate.md
│
├── [07]-Combinational-Logic/
│   ├── 01-Introduction.md
│   ├── 02-Truth-Tables.md
│   ├── 03-Minterms-Maxterms.md
│   └── 04-Combinational-vs-Sequential.md
│
├── [08]-Karnaugh-Map/
│   ├── 01-KMap-3-Variable.md
│   ├── 02-KMap-4-Variable.md
│   └── 03-Dont-Care-Conditions.md
│
├── [09]-Combinational-Circuits/
│   ├── [01]-Adders/
│   │   ├── 01-Half-Adder.md
│   │   ├── 02-Full-Adder.md
│   │   └── 03-Full-Adder-Using-Two-Half-Adder.md
│   │
│   ├── [02]-Subtractor/
│   │   ├── 01-Half-Subtractor.md
│   │   ├── 02-Full-Subtractor.md
│   │   └── 03-Full-Subtractor-Using-Two-Half-Subtractor.md
│   │
│   ├── [03]-Multiplexer/
│   │   ├── 01-2x1.md
│   │   ├── 02-4x1.md
│   │   └── 03-8x1.md
│   │
│   ├── [04]-Demultiplexer/
│   │   ├── 01-1x2.md
│   │   ├── 02-1x4.md
│   │   └── 03-1x8.md
│   │
│   ├── [05]-Decoder/
│   │   ├── 01-2x4.md
│   │   └── 02-3x8.md
│   │
│   ├── [06]-Encoder/
│   │   ├── 01-4x2.md
│   │   └── 02-8x3.md
│   │
│   ├── [07]-Comparator/
│   │   ├── 1-bit.md
│   │   ├── 2-bit.md
│   │   └── 3-bit.md
│   │
│   └── [08]-Ripple-Carry-Adder.md
│
├── [10]-Flip-Flops/
│   ├── SR-FlipFlop.md
│   ├── D-FlipFlop.md
│   ├── JK-FlipFlop.md
│   ├── T-FlipFlop.md
│   ├── Characteristic-Table.md
│   └── Excitation-Table.md
│
├── [11]-Registers/
│   ├── 01-Register-Basics.md
│   ├── 02-Shift-Registers.md
│   ├── 03-SISO-Register.md
│   ├── 04-SIPO-Register.md
│   ├── 05-PISO-Register.md
│   └── 06-PIPO-Register.md
│
├── [12]-Counters/
│   ├── Asynchronous-Counters/
│   │   ├── 3-Bit-Asynchronous-Up-Counter.md
│   │   ├── 3-Bit-Asynchronous-Down-Counter.md
│   │   ├── 4-Bit-Asynchronous-Up-Counter.md
│   │   └── 4-Bit-Asynchronous-Down-Counter.md
│   │
│   ├── Synchronous-Counters/
│   │   ├── 3-Bit-Synchronous-Up-Counter.md
│   │   ├── 3-Bit-Synchronous-Down-Counter.md
│   │   ├── 4-Bit-Synchronous-Up-Counter.md
│   │   └── 4-Bit-Synchronous-Down-Counter.md
│   │
│   └── Ring-Counter.md
│
└── [13]-Finite-State-Machines/
    ├── 01-FSM-Introduction.md
    ├── 02-Why-FSM.md
    ├── 03-State-Diagram.md
    ├── 04-State-Table.md
    ├── 05-Moore-Machine.md
    ├── 06-Mealy-Machine.md
    ├── 07-FSM-Design-Procedure.md
    └── 08-Sequence-Detector.md
```
---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
