# Number System Conversion & Reference Guide

[![Digital Logic](https://img.shields.io/badge/Logic-Digital%20Design-blue.svg)](#)
[![Stage](https://img.shields.io/badge/Stage-A-brightgreen.svg)](#)

This document serves as a comprehensive reference guide for understanding foundational digital number systems (Binary, Octal, Hexadecimal, and Decimal) along with exact procedural workflows for converting numbers between these bases.

---

## 🔢 Core Number Systems Reference

### 1. Binary Number System (Base-2)
The fundamental language of digital electronics and computer systems, representing states using two characters.
* **Digits:** `0` (OFF / Low Voltage) and `1` (ON / High Voltage)
* **Weights:** Expressed as powers of 2 ($2^n$).

### 2. Hexadecimal Number System (Base-16)
Used extensively in computing to provide a human-readable, compact representation of long binary strings.
* **Digits:** `0-9` and letters `A-F` to represent values from 10 to 15:
    * `A` = 10, `B` = 11, `C` = 12, `D` = 13, `E` = 14, `F` = 15

### 3. Octal Number System (Base-8)
An older computing base representation that groups binary digits into clusters of three.
* **Digits:** `0, 1, 2, 3, 4, 5, 6, 7`
* **Example:** $(231.25)_8$

---

## 🔄 Conversion Methodologies & Examples

### 📊 1. Binary to Hexadecimal
To convert a binary number to hexadecimal, split the digits into **groups of four bits** starting from the binary point (moving left for integers, right for fractional parts). Pad with leading or trailing zeros if necessary.

**Example String:** $(010011110111.11010101)_2$

1. **Group into 4-bit clusters:** `0100`, `1111`, `0111` **.** `1101`, `0101`, `0000`
2. **Convert each cluster to its Hex equivalent:**
   * `0100` $\rightarrow$ **4**
   * `1111` $\rightarrow$ **F**
   * `0111` $\rightarrow$ **7**
   * `1101` $\rightarrow$ **D**
   * `0101` $\rightarrow$ **5**
   * `0000` $\rightarrow$ **0**

> **Result:** $(010011110111.11010101)_2 = (4F7.D50)_{16}$

---

### 📊 2. Hexadecimal to Binary
Convert each individual hexadecimal digit directly into its equivalent **4-bit binary representation**.

**Example String:** $(F37A.B2)_{16}$

* **F** $\rightarrow$ `1111`
* **3** $\rightarrow$ `0011`
* **7** $\rightarrow$ `0111`
* **A** $\rightarrow$ `1010`
* **.**
* **B** $\rightarrow$ `1011`
* **2** $\rightarrow$ `0010`

> **Result:** $(F37A.B2)_{16} = (111100111010.10110010)_2$

---

### 📊 3. Binary to Decimal
Multiply each active bit (`1`) by its positional weight ($2^n$) and sum the results.

**Example String:** $(111000)_2$

| Bit Position | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Weight** | 32 | 16 | 8 | 4 | 2 | 1 |
| **Bit Value** | **1** | **1** | **1** | **0** | **0** | **0** |

$$\text{Calculation: } 32 + 16 + 8 = 56$$

> **Result:** $(111000)_2 = (56)_{10}$

---

### 📊 4. Decimal to Binary (Successive Division Radix Conversion)
To convert an integer from Decimal to a target base, repeatedly divide the quotient by the target radix (Base 2) and record the remainder. Read the final remainders from **bottom to top** (MSB to LSB).

**Example:** Convert $(119)_{10}$ to Binary

1. $119 \div 2 = 59$ with a Remainder of **1** (LSB)
2. $59 \div 2 = 29$ with a Remainder of **1**
3. $29 \div 2 = 14$ with a Remainder of **1**
4. $14 \div 2 = 7$ with a Remainder of **0**
5. $7 \div 2 = 3$ with a Remainder of **1**
6. $3 \div 2 = 1$ with a Remainder of **1**
7. $1 \div 2 = 0$ with a Remainder of **1** (MSB)

> **Result:** $(119)_{10} = (1110111)_2$
