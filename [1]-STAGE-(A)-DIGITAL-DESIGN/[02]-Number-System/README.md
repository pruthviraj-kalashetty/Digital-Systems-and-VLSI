# Number System

[![Digital Logic](https://img.shields.io/badge/Logic-Digital%20Design-blue.svg)](#)
[![Stage](https://img.shields.io/badge/Stage-A-brightgreen.svg)](#)

## Overview

A **Number System** is a method of representing numerical values using a fixed set of symbols (digits) and a **base (radix)**. Number systems form the foundation of Digital Electronics because all digital circuits store, process, and transmit information in binary form.

Understanding number systems is essential before learning Binary Arithmetic, Boolean Algebra, Logic Gates, Combinational Logic, Sequential Logic, RTL Design, FPGA Design, and ASIC Design.

---

## Topics Covered

- Binary Number System
- Decimal Number System
- Octal Number System
- Hexadecimal Number System
- Binary to Decimal Conversion
- Decimal to Binary Conversion
- Binary to Octal Conversion
- Octal to Binary Conversion
- Binary to Hexadecimal Conversion
- Hexadecimal to Binary Conversion
- Successive Division (Radix Conversion)

---

# Number Systems

## 1. Binary Number System (Base-2)

The **Binary Number System** is the fundamental language of digital electronics and computer systems. It represents data using only two digits.

### Digits

- **0** → LOW / OFF
- **1** → HIGH / ON

### Base

**Base = 2**

### Positional Weights

| Bit Position | 5 | 4 | 3 | 2 | 1 | 0 |
|:------------:|:-:|:-:|:-:|:-:|:-:|:-:|
| Weight | 2⁵ | 2⁴ | 2³ | 2² | 2¹ | 2⁰ |

### Example

```
111000₂

= (1 × 2⁵) + (1 × 2⁴) + (1 × 2³)

= 32 + 16 + 8

= 56₁₀
```

---

## 2. Decimal Number System (Base-10)

The **Decimal Number System** is the standard numbering system used in everyday life.

### Digits

```
0, 1, 2, 3, 4, 5, 6, 7, 8, 9
```

### Base

**Base = 10**

### Example

```
(459)₁₀

= (4 × 10²)

+ (5 × 10¹)

+ (9 × 10⁰)

= 400 + 50 + 9

= 459
```

---

## 3. Octal Number System (Base-8)

The **Octal Number System** uses eight digits and is commonly used as a compact representation of binary numbers.

### Digits

```
0, 1, 2, 3, 4, 5, 6, 7
```

### Base

**Base = 8**

### Example

```
(231.25)₈
```

---

## 4. Hexadecimal Number System (Base-16)

The **Hexadecimal Number System** provides a compact representation of binary numbers and is widely used in digital electronics and computer systems.

### Digits

```
0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F
```

### Base

**Base = 16**

### Hexadecimal Values

| Hex | Decimal |
|:---:|:-------:|
| A | 10 |
| B | 11 |
| C | 12 |
| D | 13 |
| E | 14 |
| F | 15 |

### Example

```
(A3F)₁₆
```

---

# Number System Conversions

## 1. Binary to Hexadecimal

To convert a binary number into hexadecimal:

- Divide the binary digits into groups of **4 bits**.
- Start grouping from the binary point.
- Add leading or trailing zeros if required.
- Convert each 4-bit group into its hexadecimal equivalent.

### Example

```
(010011110111.11010101)₂
```

Group into 4-bit blocks

```
0100 1111 0111 . 1101 0101 0000
```

Convert each group

| Binary | Hex |
|:------:|:---:|
|0100|4|
|1111|F|
|0111|7|
|1101|D|
|0101|5|
|0000|0|

### Result

```
(010011110111.11010101)₂ = (4F7.D50)₁₆
```

---

## 2. Hexadecimal to Binary

Each hexadecimal digit is represented by **4 binary bits**.

### Example

```
(F37A.B2)₁₆
```

| Hex | Binary |
|:---:|:------:|
|F|1111|
|3|0011|
|7|0111|
|A|1010|
|B|1011|
|2|0010|

### Result

```
(F37A.B2)₁₆

=

(1111001101111010.10110010)₂
```

---

## 3. Binary to Decimal

Multiply each binary digit by its positional weight (2ⁿ) and add the values corresponding to bits that are **1**.

### Example

```
(111000)₂
```

| Bit | Weight |
|:---:|:------:|
|1|2⁵ = 32|
|1|2⁴ = 16|
|1|2³ = 8|
|0|2² = 4|
|0|2¹ = 2|
|0|2⁰ = 1|

Calculation

```
32 + 16 + 8 = 56
```

### Result

```
(111000)₂ = (56)₁₀
```

---

## 4. Decimal to Binary (Successive Division Method)

The **Successive Division Method** converts a decimal integer into binary by repeatedly dividing the number by **2** and recording the remainder.

The binary number is obtained by reading the remainders from **bottom to top**.

### Example

Convert

```
(119)₁₀
```

| Division | Quotient | Remainder |
|:---------|:--------:|:---------:|
|119 ÷ 2|59|1|
|59 ÷ 2|29|1|
|29 ÷ 2|14|1|
|14 ÷ 2|7|0|
|7 ÷ 2|3|1|
|3 ÷ 2|1|1|
|1 ÷ 2|0|1|

Read the remainders from bottom to top

```
1110111
```

### Result

```
(119)₁₀ = (1110111)₂
```

---

# Applications

Number systems are widely used in:

- Digital Electronics
- Computer Architecture
- Microprocessors
- Embedded Systems
- RTL Design
- FPGA Design
- ASIC Design
- Memory Addressing
- Digital Communication

---

# Learning Outcomes

After completing this section, you will be able to:

- Understand Binary, Decimal, Octal, and Hexadecimal number systems.
- Identify the radix (base) of each number system.
- Perform manual number system conversions.
- Convert between Binary, Decimal, Octal, and Hexadecimal.
- Apply number system concepts in Digital Logic Design and RTL Design.

---

# Summary

Number systems are one of the most important foundations of Digital Electronics. Every digital circuit internally stores and processes data using binary values. Understanding Binary, Decimal, Octal, and Hexadecimal number systems, along with their conversion techniques, provides the necessary foundation for studying Binary Arithmetic, Boolean Algebra, Logic Gates, Digital Circuit Design, RTL Design, FPGA Design, and ASIC Design.
