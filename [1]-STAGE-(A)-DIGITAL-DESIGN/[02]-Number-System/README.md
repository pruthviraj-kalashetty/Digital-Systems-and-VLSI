# Number Systems & Conversions

[![Stage](https://img.shields.io/badge/Stage-A--Digital--Design-blue.svg)](#)
[![Focus](https://img.shields.io/badge/Focus-Hardware%20Fundamentals-orange.svg)](#)

This module establishes the core mathematical foundations required for RTL design and digital logic. While hardware fundamentally operates on binary logic levels, hardware engineers switch between different radix (base) representations to optimize memory layout, address decoding, and code readability.

---

## 🔌 Hardware-Level System Overview

### 1. Binary System (Base-2)
In digital circuits, binary digits (`0` and `1`) do not just mean "OFF" or "ON." They represent physical **electrical voltage ranges** (Logic Levels):
*   **Logic 0:** Represents Logic Low ($V_{OL}$ / Ground).
*   **Logic 1:** Represents Logic High ($V_{OH}$ / $V_{DD}$).
*   *Hardware Context:* Hardware tracks these values using positional weights based on powers of two ($2^n$).

### 2. Hexadecimal System (Base-16)
Reading a raw 32-bit or 64-bit binary bus in a simulation waveform is highly prone to human error. Hexadecimal solves this by grouping bits.
*   **The Math:** Since $16 = 2^4$, exactly **one hexadecimal digit maps to a 4-bit binary nibble**.
*   **Digits:** `0-9` for values 0-9, and `A-F` for values 10-15 (`A`=10, `B`=11, `C`=12, `D`=13, `E`=14, `F`=15).

### 3. Octal System (Base-8)
An older computing representation where **one octal digit maps to a 3-bit binary group** ($8 = 2^3$). 
*   **Digits:** `0` through `7`.
*   *Application:* Used historically in 12-bit or 36-bit architectures, and still seen in system permissions.

---

## 🔄 Practical Conversion Procedures

### 🔹 1. Binary $\leftrightarrow$ Hexadecimal Fast Mapping
Because Hex maps perfectly to 4-bit boundaries, you do not need to convert to decimal first. Simply group bits by 4, starting from the radix point and moving outward.

*   **Binary to Hex Example:** `0100 1111 0111 . 1101 0101`
    *   `0100` $\rightarrow$ **4**
    *   `1111` $\rightarrow$ **F**
    *   `0111` $\rightarrow$ **7**
    *   `1101` $\rightarrow$ **D**
    *   `0101` $\rightarrow$ **5**
    *   *Result:* $(010011110111.11010101)_2 = (4F7.D5)_{16}$

*   **Hex to Binary Example:** $(F37A.B2)_{16}$
    *   Expand each digit to its exact 4-bit equivalent: `F` $\rightarrow$ 1111, `3` $\rightarrow$ 0011, `7` $\rightarrow$ 0111, `A` $\rightarrow$ 1010, `B` $\rightarrow$ 1011, `2` $\rightarrow$ 0010.
    *   *Result:* $(F37A.B2)_{16} = (111100110111.10110010)_2$

---

### 🔹 2. Binary to Decimal (Weighted Sum)
To find the decimal value of a binary string, calculate the sum of the positional weights for every active (`1`) bit.

*   **Example:** $(111000)_2$
    *   Identify the active powers of 2: $2^5$ (32), $2^4$ (16), and $2^3$ (8).
    *   Ignore positions with `0`.
    *   *Calculation:* $32 + 16 + 8 = 56$
    *   *Result:* $(111000)_2 = (56)_{10}$

---

### 🔹 3. Decimal to Binary (Successive Radix Division)
To convert a base-10 integer to base-2, repeatedly divide the integer by 2. Record the remainder at each step, and use the new quotient for the next division. Read the remainders from **bottom to top** (Most Significant Bit to Least Significant Bit).

*   **Example:** Convert $(119)_{10}$ to Binary
    1. $119 \div 2 = 59$ | Remainder = **1** (LSB)
    2. $59 \div 2 = 29$  | Remainder = **1**
    3. $29 \div 2 = 14$  | Remainder = **1**
    4. $14 \div 2 = 7$   | Remainder = **0**
    5. $7 \div 2 = 3$    | Remainder = **1**
    6. $3 \div 2 = 1$    | Remainder = **1**
    7. $1 \div 2 = 0$    | Remainder = **1** (MSB)
    *   *Result:* Reading bottom-to-top yields $(1110111)_2$
