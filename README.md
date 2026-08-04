# 🚀 Digital Design & VLSI Fundamentals

### Digital Electronics • Semiconductor Fundamentals • CMOS • Timing • VLSI Concepts • RTL Design Foundation

<p>
  <img src="https://img.shields.io/badge/Domain-VLSI%20Engineering-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Focus-Digital%20Design%20%26%20CMOS-00C8FF?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Semiconductor-CMOS-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Timing-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Concepts-STA%20Basics-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Purpose-RTL%20Design%20Foundation-success?style=for-the-badge"/>
</p>

---
<p align="center">
  <img src="https://img.shields.io/badge/Domain-VLSI%20Engineering-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Focus-Digital%20Design-00C8FF?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Semiconductor-CMOS-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Timing-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Foundation-RTL%20Design-purple?style=for-the-badge"/>
</p>

## 📌 About This Repository

This repository contains structured notes, concepts, and design fundamentals required for **RTL Design and VLSI Engineering**.

It covers the journey from:
- Semiconductor fundamentals
- MOS and CMOS concepts
- Digital logic design
- Timing concepts
- VLSI design fundamentals

The objective is to build a strong foundation before moving into **Verilog RTL Design and ASIC/FPGA implementation**.

---

# 📚 Concepts Covered

## Semiconductor & VLSI Fundamentals
- Semiconductor Basics
- PN Junction
- MOS Devices
- NMOS & PMOS
- CMOS Fundamentals
- CMOS Inverter
- CMOS Logic Gates
- VLSI Design Flow

## Digital Design Fundamentals
- Number Systems
- Binary Arithmetic
- Binary Codes
- Boolean Algebra
- Logic Gates
- Karnaugh Maps

## Combinational Logic
- Adders
- Subtractors
- Multiplexers
- Demultiplexers
- Encoders
- Decoders
- Comparators
- ALU Basics

## Sequential Logic
- Latches
- Flip-Flops
- Registers
- Counters
- Shift Registers

## Advanced Digital Concepts
- Finite State Machines (FSM)
- Clock & Reset Concepts
- Timing Parameters
  - Setup Time
  - Hold Time
  - Propagation Delay
- Static Timing Analysis (STA Basics)

---

# 🏗️ Directory Structure

```text
Digital-System-and-VLSI
│
├──Digital-Design-and-VLSI-fundamentals
│
├── 01-Digital-Basics
│   ├── Digital-vs-Analog.md
│   └── Digital-System-Overview.md
│
├── 02-Number-Systems
│   ├── Binary-System.md
│   ├── Octal-System.md
│   ├── Hexadecimal-System.md
│   └── 1-Number-System-Conversion.md
│
├── 03-Binary-Arithmetic
│   ├── Binary-Addition.md
│   └── Binary-Subtraction.md
│
├── 04-Binary-Codes
│   ├── BCD-Code.md
│   ├── Gray-Code.md
│   └── ASCII-Code.md 
│
├── 05-Boolean-Algebra
│   ├── 1-Boolean-Basics.md
│   ├── 2-Boolean-Expression.md
│   ├── 3-Boolean-Laws.md
│   └── 4-De-Morgans-Theorem.md
│
├── 06-Logic-Gates
│   ├── AND-Gate.md
│   ├── OR-Gate.md
│   ├── NOT-Gate.md
│   ├── NAND-Gate.md
│   ├── NOR-Gate.md
│   ├── XOR-Gate.md
│   └── XNOR-Gate.md
│
├── 07-Combinational-Logic
│   ├── Introduction.md
│   ├── Truth-Tables.md
│   ├── Minterms-Maxterms.md
│   └── Combinational-vs-Sequential.md
│
├── 08-Karnaugh-Map
│   ├── Kmap-3-Variable.md
│   ├── Kmap-4-Variable.md
│   └── Dont-Care-Conditions.md
│
├── 09-Combinational-Circuits
│   ├── Half-Adder.md
│   ├── Full-Adder.md
│   ├── Half-Subtractor.md
│   ├── Full-Subtractor.md
│   ├── Full-Adder-using-Half-Adder.md
│   ├── Full-Subtractor-using-Half-Subtractor.md
│   ├── Ripple-Carry-Adder.md
│   ├── Multiplexer.md
│   │   ├── 2x1
│   │   ├── 4x1
│   │   └── 8x1
│   ├── Demultiplexer.md
│   │   ├── 1x2
│   │   ├── 1x4
│   │   └── 1x8
│   ├── Decoder.md
│   │   ├── 2x4
│   │   └── 3x8
│   ├── Encoder.md
│   │   ├── 4x2
│   │   ├── 8x3
│   │   └── Priority-Encoder.md
│   └── Comparator.md
│       ├── 1-bit
│       ├── 2-bit
│       └── 4-bit
│
├── 10-Flip-Flops
│   ├── SR-FlipFlop.md
│   ├── D-FlipFlop.md
│   ├── JK-FlipFlop.md
│   ├── T-FlipFlop.md
│   ├── Characteristic-Table.md
│   └── Excitation-Table.md
│
├── 11-Registers
│   ├── Register-Basics.md
│   ├── Shift-Registers.md
│   ├── SISO-Register.md
│   ├── SIPO-Register.md
│   ├── PISO-Register.md
│   └── PIPO-Register.md
│
├── 12-Counters
│
├── Asynchronous-Counters
│   ├── Ripple-Counter
│   ├── Up-Counter
│   └── Down-Counter
│
├── Synchronous-Counters
│   ├── Up-Counter
│   ├── Down-Counter
│   ├── Up-Down-Counter (optional)
│   └── Mod-N-Counter
│
└── Special-Counters
│   ├── Ring-Counter
│    └── Johnson-Counter
│
├── 13-Finite-State-Machines
│   ├── FSM-Introduction.md
│   ├── State-Diagram.md
│   ├── State-Table.md
│   ├── Moore-Machine.md
│   ├── Mealy-Machine.md
│   └── Sequence-Detector.md
│
├── 14-Timing-Concepts
│   ├── Setup-Time.md
│   ├── Hold-Time.md
│   ├── Clock-to-Q-Delay.md
│   ├── Propagation-Delay.md
│   └── Timing-Diagrams.md
│
├── 15-Semiconductor-Basics
│   ├── Semiconductor-Concept.md
│   ├── Intrinsic-vs-Extrinsic-Semiconductor.md
│   ├── PN-Junction.md
│   └── Diode-Operation.md
│
├── 16-MOS-Devices
│   ├── MOS-Capacitor.md
│   ├── MOSFET-Structure.md
│   ├── MOSFET-Working.md
│   ├── NMOS.md
│   ├── PMOS.md
│   └── CMOS-Inverter.md
│
└── 17-VLSI-Fundamentals
    ├── CMOS-Delay-and-Sizing.md
    ├── Parasitic-RC.md
    ├── Power-Static-vs-Dynamic.md
    └── Logical-Effort.md
```
---


---

# 🎯 Skills Developed

✔ Digital Circuit Analysis  
✔ CMOS Logic Understanding  
✔ RTL Design Foundation  
✔ Hardware Problem Solving  
✔ VLSI Design Flow Understanding  
✔ Interview Preparation

---

# 🛠️ Tools Used

<p>
<img src="https://skillicons.dev/icons?i=github,git,vscode,linux"/>
</p>

---

# 🔗 Next Learning Stage

This repository builds the foundation for:

➡ Verilog RTL Design  
➡ SystemVerilog Verification  
➡ FPGA Implementation  
➡ ASIC Design Flow

