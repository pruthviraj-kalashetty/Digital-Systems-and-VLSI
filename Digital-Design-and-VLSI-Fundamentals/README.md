# ◈ Digital Design Fundamentals

[![Stage](https://img.shields.io/badge/Digital--Design--and--VLSI--Fundamentals-blue.svg)](#)

This repository develops a structured foundation in digital design, progressing from fundamental digital concepts and number systems to Boolean algebra, logic gates, combinational circuits, sequential logic, counters, registers, and finite-state machines.

The learning path is designed to build the core knowledge required for Verilog HDL, RTL design, computer architecture, VLSI, FPGA, and ASIC design. Each topic focuses on understanding the underlying digital concepts before moving toward hardware description and practical RTL implementation.

---

## 🎯 Learning Objectives

By working through this repository, you will be able to:

- Understand the fundamental principles of digital electronics and digital systems.
- Work confidently with binary, decimal, octal, and hexadecimal number systems.
- Perform binary arithmetic and understand commonly used binary codes.
- Apply Boolean algebra, Boolean laws, and DeMorgan's theorem to simplify logic expressions.
- Understand and analyze fundamental logic gates and digital logic functions.
- Use truth tables, minterms, maxterms, and Karnaugh maps for logic analysis and simplification.
- Design and analyze fundamental combinational circuits such as adders, subtractors, multiplexers, decoders, encoders, and comparators.
- Understand sequential logic, flip-flops, registers, and counters.
- Analyze and design finite-state machines using Moore and Mealy models.
- Build a strong foundation for Verilog HDL, RTL design, VLSI, FPGA, and ASIC development.

---

## 📂 Module Contents

| Module | Core Technical Focus |
| :--- | :--- |
| **[`[01]-Digital-Basics`](./[01]-Digital-Basics/)** | Digital vs. analog concepts and the overview of digital systems. |
| **[`[02]-Number-Systems`](./[02]-Number-Systems/)** | Binary, decimal, octal, hexadecimal number systems and base conversion techniques. |
| **[`[03]-Binary-Arithmetic`](./[03]-Binary-Arithmetic/)** | Binary addition, subtraction, multiplication, and division. |
| **[`[04]-Binary-Codes`](./[04]-Binary-Codes/)** | BCD, Gray Code, ASCII, Excess-3, and binary/Gray code conversions. |
| **[`[05]-Boolean-Algebra`](./[05]-Boolean-Algebra/)** | Boolean fundamentals, Boolean laws, DeMorgan's theorem, and Boolean expressions. |
| **[`[06]-Logic-Gates`](./[06]-Logic-Gates/)** | AND, OR, NOT, NAND, NOR, XOR, and XNOR logic gates. |
| **[`[07]-Combinational-Logic`](./[07]-Combinational-Logic/)** | Combinational logic fundamentals, truth tables, minterms, maxterms, and combinational vs. sequential logic. |
| **[`[08]-Karnaugh-Map`](./[08]-Karnaugh-Map/)** | 3-variable and 4-variable Karnaugh maps and don't-care conditions. |
| **[`[09]-Combinational-Circuits`](./[09]-Combinational-Circuits/)** | Adders, subtractors, multiplexers, demultiplexers, decoders, encoders, comparators, and ripple-carry adders. |
| **[`[10]-Flip-Flops`](./[10]-Flip-Flops/)** | SR, D, JK, and T flip-flops, characteristic tables, and excitation tables. |
| **[`[11]-Registers`](./[11]-Registers/)** | Register fundamentals and SISO, SIPO, PISO, and PIPO shift registers. |
| **[`[12]-Counters`](./[12]-Counters/)** | Asynchronous, synchronous, and ring counters with up/down counting configurations. |
| **[`[13]-Finite-State-Machines`](./[13]-Finite-State-Machines/)** | FSM fundamentals, state diagrams, state tables, Moore and Mealy machines, FSM design procedure, and sequence detectors. |

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

## 🛠️ Core Concepts Covered

### 1. Digital Design Fundamentals

Build an understanding of how physical signals are represented as digital information and how digital systems process binary data.

Key concepts include:

- Digital vs. analog signals
- Digital system architecture
- Binary representation
- Logic states

### 2. Number Systems and Binary Arithmetic

Develop the mathematical foundation required for digital hardware design.

Topics include:

- Binary
- Decimal
- Octal
- Hexadecimal
- Number system conversion
- Binary addition
- Binary subtraction
- Binary multiplication
- Binary division

### 3. Binary Codes

Understand different methods of representing digital information using binary codes.

Topics include:

- BCD
- Gray Code
- ASCII
- Excess-3
- Binary-to-Gray conversion
- Gray-to-Binary conversion

### 4. Boolean Algebra and Logic Gates

Understand Boolean mathematics and its application to digital logic design.

Topics include:

- Boolean variables and expressions
- Boolean laws
- DeMorgan's theorem
- Logic simplification
- AND
- OR
- NOT
- NAND
- NOR
- XOR
- XNOR

### 5. Combinational Logic

Understand circuits whose outputs depend only on their present inputs.

Key concepts include:

- Truth tables
- Minterms
- Maxterms
- Combinational vs. sequential logic
- Karnaugh maps
- Don't-care conditions

### 6. Combinational Circuits

Develop an understanding of commonly used combinational building blocks.

Topics include:

- Half Adder
- Full Adder
- Full Adder using two Half Adders
- Half Subtractor
- Full Subtractor
- Full Subtractor using two Half Subtractors
- Multiplexers
- Demultiplexers
- Decoders
- Encoders
- Comparators
- Ripple-Carry Adder

### 7. Sequential Logic

Understand digital circuits that use memory elements and whose behavior depends on previous states.

Topics include:

- SR Flip-Flop
- D Flip-Flop
- JK Flip-Flop
- T Flip-Flop
- Characteristic tables
- Excitation tables
- Registers
- Shift registers
- Counters

### 8. Registers and Counters

Understand how flip-flops are combined to store, shift, and sequence binary information.

Topics include:

- Register basics
- SISO
- SIPO
- PISO
- PIPO
- Asynchronous counters
- Synchronous counters
- Up counters
- Down counters
- Ring counter

### 9. Finite-State Machines

Understand FSMs as sequential models used to represent systems that transition between defined states according to inputs and clock events.

Topics include:

- FSM fundamentals
- Purpose of FSMs
- State diagrams
- State tables
- Moore machines
- Mealy machines
- FSM design procedure
- Sequence detectors

### 10. Foundation for RTL and VLSI Design

The concepts developed throughout this repository provide the digital design foundation required for further study of:

- Verilog HDL
- RTL Design
- Digital System Design
- Computer Architecture
- FPGA Design
- ASIC Design
- VLSI Design
- Digital Verification

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
