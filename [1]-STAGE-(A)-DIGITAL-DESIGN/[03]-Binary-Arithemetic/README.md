# 03. Binary Arithmetic

This module introduces the arithmetic operations used in digital electronics and computer systems. It covers binary addition and binary subtraction configurations, providing the foundation for digital logic design, computer architecture, and Verilog HDL.

---

## 🎯 Learning Objectives

By working through these modules, you will be able to:
* **Understand binary, octal, decimal, and hexadecimal number systems.**
* Analyze bit-level arithmetic operations including addition, subtraction, carries, and borrows.
* Execute exact manual calculations for multi-bit binary strings.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`Binary-Addition.md`](./Binary-Addition.md)** | Core rules of binary addition, truth tables for sum/carry tracking, and multi-bit integer addition. |
| **[`Binary-Subtraction.md`](./Binary-Subtraction.md)** | Core rules of binary subtraction, truth tables for difference/borrow tracking, and multi-bit integer subtraction. |

---

## 🛠️ Core Concepts Covered

### 1. Binary Addition Fundamentals
Binary addition processes binary digits based on combinations of logic values. When a calculation column evaluates beyond a single bit value, a carry bit ($C_{out}$) is generated to propagate the value to the next higher-order bit position.
* **Basic Rules:** * $0 + 0 = 0$
  * $0 + 1 = 1$
  * $1 + 0 = 1$
  * $1 + 1 = 0$ (with a Carry of $1$)
  * $1 + 1 + 1 = 1$ (with a Carry of $1$)

### 2. Binary Subtraction Fundamentals
Binary subtraction evaluates the exact difference between a minuend and a subtrahend. When subtracting a higher logic state from a lower logic state (e.g., $0 - 1$), a borrow bit ($B_{out}$) must be extracted from the adjacent higher-order column.
* **Basic Rules:**
  * $0 - 0 = 0$
  * $1 - 0 = 1$
  * $1 - 1 = 0$
  * $0 - 1 = 1$ (with a Borrow of $1$)

---

## 📚 Reference Literature

* M. Morris Mano & Michael D. Ciletti – *Digital Design with RTL Design, VHDL, and Verilog*
* Thomas L. Floyd – *Digital Fundamentals*
* David Money Harris & Sarah L. Harris – *Digital Design and Computer Architecture*

---

## 👤 Author

**Pruthviraj Kalashetty** *Electronics & Communication Engineering* **Aspiring RTL Design & VLSI Engineer**
