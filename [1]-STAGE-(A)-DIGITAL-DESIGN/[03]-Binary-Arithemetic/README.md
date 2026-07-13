# 03. Binary Arithmetic

[![Stage](https://img.shields.io/badge/Stage-A--Digital--Design-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Binary%20Arithmetic-orange.svg)](#)

This module introduces the fundamental arithmetic operations used in digital electronics and computer systems. It covers binary addition and binary subtraction, providing the mathematical foundation for combinational logic design, arithmetic circuits, Verilog HDL, and RTL Design.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

* Perform binary addition and binary subtraction accurately.
* Understand carry and borrow generation in binary arithmetic.
* Analyze multi-bit binary arithmetic operations.
* Build the mathematical foundation for designing adders and subtractors.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`Binary-Addition.md`](./Binary-Addition.md)** | Rules of binary addition, carry generation, truth tables, and multi-bit addition. |
| **[`Binary-Subtraction.md`](./Binary-Subtraction.md)** | Rules of binary subtraction, borrow generation, truth tables, and multi-bit subtraction. |

---

## 🛠️ Core Concepts Covered

### 1. Binary Addition

Binary addition follows the fundamental rules of arithmetic using binary digits (0 and 1). When the sum of two or more bits exceeds a single-bit value, a carry is generated and propagated to the next higher-order bit.

**Basic Rules**

- 0 + 0 = 0
- 0 + 1 = 1
- 1 + 0 = 1
- 1 + 1 = 10 (Sum = 0, Carry = 1)
- 1 + 1 + 1 = 11 (Sum = 1, Carry = 1)

### 2. Binary Subtraction

Binary subtraction determines the difference between two binary numbers. When a larger bit is subtracted from a smaller bit, a borrow is taken from the next higher-order bit.

**Basic Rules**

- 0 − 0 = 0
- 1 − 0 = 1
- 1 − 1 = 0
- 0 − 1 = 1 (Borrow = 1)

---

## 📚 Reference Literature

- M. Morris Mano & Michael D. Ciletti – *Digital Design with RTL Design, VHDL, and Verilog*
- Thomas L. Floyd – *Digital Fundamentals*
- David Money Harris & Sarah L. Harris – *Digital Design and Computer Architecture*

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
