# ◈ Combinational Circuits

[![Stage](https://img.shields.io/badge/Digital--Design--and--VLSI--Fundamentals-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Combinational%20Circuits-green.svg)](#)

This module covers the design and operation of fundamental combinational circuits used in digital electronics. It includes arithmetic circuits such as adders and subtractors, data selection and routing circuits such as multiplexers and demultiplexers, code conversion circuits such as encoders and decoders, and digital comparators.

These circuits form the foundation for designing larger digital systems, arithmetic logic units (ALUs), processors, and RTL-based hardware using Verilog HDL.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the operation and design of fundamental combinational circuits.
- Analyze and design half and full adders and subtractors.
- Understand the construction of multi-bit arithmetic circuits such as Ripple Carry Adders.
- Design multiplexers and demultiplexers for digital data selection and routing.
- Understand encoder and decoder architectures and their applications.
- Analyze priority encoder operation.
- Design digital comparators for determining equality and magnitude relationships.
- Build a strong foundation for combinational RTL design using Verilog HDL.

---

## 📂 Module Contents

### 1. Adders

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-Half-Adder.md`](./[01]-Adders/01-Half-Adder.md)** | Design and operation of a Half Adder using Sum and Carry outputs. |
| **[`02-Full-Adder.md`](./[01]-Adders/02-Full-Adder.md)** | Design and operation of a Full Adder with two input bits and a carry input. |
| **[`03-Full-Adder-Using-Two-Half-Adder.md`](./[01]-Adders/03-Full-Adder-Using-Two-Half-Adder.md)** | Implementation of a Full Adder using two Half Adders and an OR gate. |

---

### 2. Subtractors

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-Half-Subctractor.md`](./[02]-Subctractors/01-Half-Subctractor.md)** | Design and operation of a Half Subtractor using Difference and Borrow outputs. |
| **[`02-Full-Subctractor.md`](./[02]-Subctractors/02-Full-Subctractor.md)** | Design and operation of a Full Subtractor with borrow input and borrow output. |
| **[`03-Full-Subctractor-Using-Two-Half-Subctractor.md`](./[02]-Subtractors/02-Full-Subctractor-using--Two-Half-Subctractor.md)** | Implementation of a Full Subtractor using two Half Subtractors and an OR gate. |

---

### 3. Multiplexers

| File / Design | Core Technical Focus |
| :--- | :--- |
| **[`01-MUX-2-to-1.md`](./[03]-Multiplexer/01-MUX-2-to-1.md)** | Selection of one input from two available data inputs. |
| **4×1 Multiplexer** | Selection of one input from four available data inputs. |
| **8×1 Multiplexer** | Selection of one input from eight available data inputs. |

---

### 4. Demultiplexers

| File / Design | Core Technical Focus |
| :--- | :--- |
| **[`Demultiplexer.md`](./Demultiplexer/Demultiplexer.md)** | Fundamentals and operation of demultiplexers for digital data distribution. |
| **1×2 Demultiplexer** | Routing one input signal to one of two outputs. |
| **1×4 Demultiplexer** | Routing one input signal to one of four outputs. |
| **1×8 Demultiplexer** | Routing one input signal to one of eight outputs. |

---

### 5. Decoders

| File / Design | Core Technical Focus |
| :--- | :--- |
| **[`Decoder.md`](./Decoder/Decoder.md)** | Fundamentals and operation of binary decoders. |
| **2×4 Decoder** | Decoding 2-bit input combinations into four unique outputs. |
| **3×8 Decoder** | Decoding 3-bit input combinations into eight unique outputs. |

---

### 6. Encoders

| File / Design | Core Technical Focus |
| :--- | :--- |
| **[`Encoder.md`](./Encoder/Encoder.md)** | Fundamentals and operation of binary encoders. |
| **4×2 Encoder** | Encoding four input lines into a 2-bit binary output. |
| **8×3 Encoder** | Encoding eight input lines into a 3-bit binary output. |
| **[`Priority-Encoder.md`](./Encoder/Priority-Encoder.md)** | Encoding the highest-priority active input when multiple inputs are asserted simultaneously. |

---

### 7. Comparators

| File / Design | Core Technical Focus |
| :--- | :--- |
| **[`Comparator.md`](./Comparator/Comparator.md)** | Fundamentals of digital magnitude comparison. |
| **1-Bit Comparator** | Comparison of two 1-bit binary values. |
| **2-Bit Comparator** | Comparison of two 2-bit binary numbers. |
| **3-Bit Comparator** | Comparison of two 3-bit binary numbers. |

---

## 🌲 Directory Structure

```text
09-Combinational-Circuits/
├── README.md
│
├── Adders/
│   ├── Half-Adder.md
│   ├── Full-Adder.md
│   ├── Full-Adder-using-Half-Adder.md
│   ├── Ripple-Carry-Adder.md
│   └── 4-Bit-Ripple-Carry-Adder.md
│
├── Subtractors/
│   ├── Half-Subtractor.md
│   ├── Full-Subtractor.md
│   └── Full-Subtractor-using-Half-Subtractor.md
│
├── Multiplexer/
│   ├── Multiplexer.md
│   ├── 2x1/
│   ├── 4x1/
│   └── 8x1/
│
├── Demultiplexer/
│   ├── Demultiplexer.md
│   ├── 1x2/
│   ├── 1x4/
│   └── 1x8/
│
├── Decoder/
│   ├── Decoder.md
│   ├── 2x4/
│   └── 3x8/
│
├── Encoder/
│   ├── Encoder.md
│   ├── 4x2/
│   ├── 8x3/
│   └── Priority-Encoder.md
│
└── Comparator/
    ├── Comparator.md
    ├── 1-Bit/
    ├── 2-Bit/
    └── 3-Bit/
```

---

## 🛠️ Core Concepts Covered

### 1. Arithmetic Circuits

Study adders and subtractors used to perform binary arithmetic operations, including Half Adders, Full Adders, Half Subtractors, Full Subtractors, and multi-bit Ripple Carry Adders.

### 2. Data Selection and Routing

Understand Multiplexers and Demultiplexers used to select, route, and distribute digital data between multiple inputs and outputs.

### 3. Code Conversion

Learn the operation of Encoders and Decoders for converting between binary input and output representations in digital systems.

### 4. Priority Encoding

Understand how Priority Encoders resolve situations where multiple input lines are active by assigning priority to the highest-priority input.

### 5. Magnitude Comparison

Study digital Comparators used to determine whether one binary number is greater than, less than, or equal to another.

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
