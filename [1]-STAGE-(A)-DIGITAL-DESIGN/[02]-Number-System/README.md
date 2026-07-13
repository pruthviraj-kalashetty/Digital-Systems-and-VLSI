# 🔢 My Number Systems & Conversion Guide

Welcome! I put this repository together as a clean, practical reference guide to master foundational digital number systems. It maps out how Binary, Octal, Hexadecimal, and Decimal systems work under the hood, along with the exact step-by-step methods I use to convert between them.

---

## 🧠 Core Systems at a Glance

### 1. Binary (Base-2)
The absolute foundation of computer architecture. It represents data using just two states:
* **Digits:** `0` (OFF / Low Voltage) and `1` (ON / High Voltage)
* **How it scales:** Every position represents a power of 2 ($2^n$).

### 2. Hexadecimal (Base-16)
Because reading long strings of 0s and 1s gives humans a headache, we use Hex as a compact shortcut. 
* **Digits:** `0-9` for standard numbers, and letters `A-F` for values 10 through 15:
    * `A`=10, `B`=11, `C`=12, `D`=13, `E`=14, `F`=15

### 3. Octal (Base-8)
A legacy base system that groups binary digits into sets of three.
* **Digits:** `0` through `7`

---

## 🔄 Step-by-Step Conversion Workflows

### 📊 1. Binary to Hexadecimal
To turn binary into hex, I split the bits into **groups of four** starting from the radix point. (Go left for whole numbers, right for decimals). If a group is short, just pad it with zeros.

**Example:** Convert $(010011110111.11010101)_2$ to Hex

1. **Group into 4-bit chunks:** `0100` | `1111` | `0111` **.** `1101` | `0101` | `0000`
2. **Translate each chunk:**
   * `0100` $\rightarrow$ **4**
   * `1111` $\rightarrow$ **F**
   * `0111` $\rightarrow$ **7**
   * `1101` $\rightarrow$ **D**
   * `0101` $\rightarrow$ **5**
   * `0000` $\rightarrow$ **0**

> **Result:** $(010011110111.11010101)_2 = (4F7.D50)_{16}$

---

### 📊 2. Hexadecimal to Binary
This is the reverse process. I take each individual Hex digit and expand it into its unique **4-bit binary equivalent**.

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
For this, I line up the binary string against a positional weight table, grab every active bit (`1`), and sum their values up.

**Example:** Convert $(111000)_2$ to Decimal

| Bit Position | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Weight Value** | 32 | 16 | 8 | 4 | 2 | 1 |
| **My Bit String** | **1** | **1** | **1** | **0** | **0** | **0** |

$$\text{Calculation: } 32 + 16 + 8 = 56$$

> **Result:** $(111000)_2 = (56)_{10}$

---

### 📊 4. Decimal to Binary (Successive Division)
To bring a normal decimal number down to base-2, I repeatedly divide the number by 2 and track the remainders. Once I hit 0, I read the remainders from **bottom to top** (Most Significant Bit to Least Significant Bit).

**Example:** Convert $(119)_{10}$ to Binary

1. $119 \div 2 = 59$ (Remainder **1** - LSB)
2. $59 \div 2 = 29$ (Remainder **1**)
3. $29 \div 2 = 14$ (Remainder **1**)
4. $14 \div 2 = 7$ (Remainder **0**)
5. $7 \div 2 = 3$ (Remainder **1**)
6. $3 \div 2 = 1$ (Remainder **1**)
7. $1 \div 2 = 0$ (Remainder **1** - MSB)

> **Result:** $(119)_{10} = (1110111)_2$
