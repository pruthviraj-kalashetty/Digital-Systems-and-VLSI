# ◈ Binary Codes

[![Stage](https://img.shields.io/badge/Digital--Design--and--VLSI--Fundamentals--Design-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Binary%20Codes-orange.svg)](#)

This module introduces binary codes used to represent, process, store, and communicate digital information. It covers BCD, Gray Code, ASCII, Excess-3 Code, and binary code conversion techniques, providing a foundation for data representation and digital logic design.

These concepts are important for understanding digital systems, data encoding, error reduction, communication interfaces, and code-conversion circuits used in digital electronics and VLSI design.

---

## 🎯 Learning Objectives

By working through this module, you will be able to:

- Understand the purpose and classification of binary codes.
- Analyze BCD, Gray, ASCII, and Excess-3 code representations.
- Convert binary values between different code formats.
- Understand the advantages and applications of different binary codes.
- Build a foundation for code-conversion and digital data representation circuits.

---

## 📂 Module Contents

| File | Core Technical Focus |
| :--- | :--- |
| **[`01-BCD-Code.md`](./01-BCD-Code.md)** | Binary-Coded Decimal representation, encoding rules, decimal digit representation, and applications. |
| **[`02-Gray-Code.md`](./02-Gray-Code.md)** | Gray Code representation, characteristics, and its ability to minimize bit changes between consecutive values. |
| **[`03-ASCII-Code.md`](./03-ASCII-Code.md)** | ASCII character encoding, binary representation of characters, and digital communication applications. |
| **[`04-Excess-3-Code.md`](./04-Excess-3-Code.md)** | Excess-3 code representation, encoding procedure, characteristics, and applications. |
| **[`05-Binary-to-Gray.md`](./05-Binary-to-Gray.md)** | Conversion procedure from Binary Code to Gray Code using bitwise relationships. |
| **[`06-Gray-to-Binary.md`](./06-Gray-to-Binary.md)** | Conversion procedure from Gray Code to Binary using cumulative XOR relationships. |

---

## 🌲 Directory Structure

```text
04-Binary-Codes/
├── README.md
├── 01-BCD-Code.md
├── 02-Gray-Code.md
├── 03-ASCII-Code.md
├── 04-Excess-3-Code.md
├── 05-Binary-to-Gray.md
└── 06-Gray-to-Binary.md
```

---

## 🛠️ Core Concepts Covered

### 1. Binary Code Fundamentals

Understand how binary codes represent numerical values, characters, and other forms of information using combinations of binary digits.

### 2. BCD Code

Study Binary-Coded Decimal (BCD), where each decimal digit is represented independently using a four-bit binary pattern.

### 3. Gray Code

Understand Gray Code, in which consecutive code values differ by only one bit. This property helps reduce transition errors in applications such as position encoders.

### 4. ASCII Code

Learn how ASCII represents characters using binary code and understand its role in digital systems and communication interfaces.

### 5. Excess-3 Code

Understand Excess-3 as a non-weighted, self-complementing decimal code and learn how decimal digits are represented using this coding scheme.

### 6. Binary-to-Gray Conversion

Learn how to convert a binary number into its corresponding Gray Code using XOR-based relationships between adjacent bits.

### 7. Gray-to-Binary Conversion

Understand how Gray Code can be converted back to Binary by applying cumulative XOR operations from the most significant bit toward the least significant bit.

### 8. Applications of Binary Codes

Binary codes are used in:

- Digital data representation
- Digital communication
- Rotary and position encoders
- Character encoding
- Code-conversion circuits
- Error-reduction techniques
- Digital control systems
- VLSI and digital logic design

---

## 📚 Reference Literature

- Neso Academy – Digital Electronics
- All About Electronics – Digital Electronics Tutorials

---

## 👤 Author

**Pruthviraj Kalashetty**

*Electronics & Communication Engineering Student*

**VLSI & RTL Design Learner**
