# Subtractors

[![Stage](https://img.shields.io/badge/Combinational--Circuits-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Subtractors-orange.svg)](#)

This module introduces subtractors, the fundamental combinational circuits used to perform binary subtraction in digital systems. It covers the Half Subtractor, Full Subtractor, and the implementation of a Full Subtractor using two Half Subtractors. These circuits form the foundation of arithmetic units, processors, digital systems, and RTL design.

Understanding subtractor circuits is essential before studying arithmetic logic units (ALUs), binary arithmetic, and advanced digital arithmetic architectures.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the fundamentals of binary subtraction.
- Analyze the operation of Half Subtractors and Full Subtractors.
- Understand borrow generation and propagation.
- Implement a Full Subtractor using two Half Subtractors.
- Build the foundation for arithmetic circuit and RTL design.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-Half-Subctractor.md`](./01-Half-Subctractor.md)** | Introduction to the Half Subtractor, binary subtraction of two single-bit inputs, truth table, Boolean expressions, and logic implementation. |
| **[`02-Full-Subctractor.md`](./02-Full-Subctractor.md)** | Design and operation of the Full Subtractor, including borrow input, truth table, Boolean expressions, and logic implementation. |
| **[`03-Full-Subctractor-Using-Two-Half-Sucbtractor.md`](./03-Full-Subctractor-Using-Two-Half-Subctractor.md)** | Construction of a Full Subtractor using two Half Subtractors and an OR gate, with complete circuit analysis. |

---

## 🌲 Directory Structure

```text
Subtractors/
├── README.md
├── 01-Half-Subtractor.md
├── 02-Full-Subtractor.md
└── 03-Full-Subtractor-Using-Two-Half-Subtractors.md
```

---

## 🛠️ Core Concepts Covered

### 1. Binary Subtraction

Understand the rules of binary subtraction and how digital circuits perform subtraction using logic gates.

### 2. Half Subtractor

Study the Half Subtractor, which subtracts one single-bit binary input from another and produces Difference and Borrow outputs.

### 3. Full Subtractor

Learn the operation of the Full Subtractor, which subtracts three binary inputs (A, B, and Borrow-In) to generate Difference and Borrow-Out outputs.

### 4. Full Subtractor Using Two Half Subtractors

Understand how two Half Subtractors and one OR gate can be combined to implement a Full Subtractor, demonstrating hierarchical digital circuit design.

### 5. Practical Applications

Explore the use of subtractors in Arithmetic Logic Units (ALUs), processors, digital signal processors (DSPs), microcontrollers, comparator circuits, and FPGA/ASIC designs.

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
