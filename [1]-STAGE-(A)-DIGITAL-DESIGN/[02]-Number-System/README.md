# 🔢 Number Systems & Conversions

A clean, practical reference guide for understanding foundational digital number systems (Binary, Octal, Hexadecimal, and Decimal) and the exact workflows used to convert between them.

---

## 📂 Core Systems Overview

### 1. Binary (Base-2)
The foundation of digital computing. Data is represented using two logical states:
* **Digits:** `0` (OFF) and `1` (ON)
* **Progression:** Each position represents an increasing power of 2 ($2^n$).

### 2. Hexadecimal (Base-16)
Used in computing as a compact, human-readable way to represent long binary sequences.
* **Digits:** `0-9` and letters `A-F` (representing values 10 to 15):
  * `A` = 10, `B` = 11, `C` = 12, `D` = 13, `E` = 14, `F` = 15

### 3. Octal (Base-8)
A legacy system that groups binary digits into clusters of three.
* **Digits:** `0` through `7`

---

## 🔄 Step-by-Step Conversions

### 📊 1. Binary to Hexadecimal
Split the binary digits into **groups of four bits** starting from the radix point (moving left for whole numbers, right for fractions). Pad with zeros if a group is incomplete.

**Example:** Convert $(010011110111.11010101)_2$ to Hex

1. **Group into 4-bit sets:** `0100` | `1111` | `0111` **.** `1101` | `0101` | `0000`
2. **Convert each set:**
   * `0100` $\rightarrow$ **4**
   * `1111` $\rightarrow$ **F**
   * `0111` $\rightarrow$ **7**
   * `1101` $\rightarrow$ **D**
   * `0101` $\rightarrow$ **5**
   * `0000` $\rightarrow$ **0**

> **Result:** $(010011110111.11010101)_2 = (4F7.D50)_{16}$

---

### 📊 2. Hexadecimal to Binary
Expand each individual Hexadecimal digit directly into its equivalent **4-bit binary sequence**.

**Example:** Convert $(F37A.B2)_{16}$ to Binary

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
Multiply each active bit (`1`) by its corresponding positional weight ($2^n$) and calculate the sum.

**Example:** Convert $(111000)_2$ to Decimal

| Bit Position | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Weight** | 32 | 16 | 8 | 4 | 2 | 1 |
| **Bit Value** | **1** | **1** | **1** | **0** | **0** | **0** |

$$\text{Calculation: } 32 + 16 + 8 = 56$$

> **Result:** $(111000)_2 = (56)_{10}$

---

### 📊 4. Decimal to Binary (Successive Division)
Repeatedly divide the decimal integer by the target radix (2) and record the remainders. Read the final remainders from **bottom to top** (Most Significant Bit to Least Significant Bit).

**Example:** Convert $(119)_{10}$ to Binary

1. $119 \div 2 = 59$ (Remainder **1** - LSB)
2. $59 \div 2 = 29$ (Remainder **1**)
3. $29 \div 2 = 14$ (Remainder **1**)
4. $14 \div 2 = 7$ (Remainder **0**)
5. $7 \div 2 = 3$ (Remainder **1**)
6. $3 \div 2 = 1$ (Remainder **1**)
7. $1 \div 2 = 0$ (Remainder **1** - MSB)

> **Result:** $(119)_{10} = (1110111)_2$
