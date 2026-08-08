# **Hexadecimal System**

* **Overview**

The **Hexadecimal System** is a base-16 number system that uses sixteen symbols, **0 to 9 and A to F**, to represent numerical values. It is widely used in digital electronics and computer systems because one hexadecimal digit represents exactly **4 binary bits**, making long binary numbers shorter and easier to read.

---

* **Definition**

The **Hexadecimal System** is a positional number system with a base of **16**, in which each digit has a positional value based on powers of 16.

---

* **Purpose**
  - To represent binary information in a compact and readable form.
  - To simplify the representation of long binary numbers.
  - To make binary-to-hexadecimal and hexadecimal-to-binary conversion easier.
  - To represent memory addresses and digital data efficiently.
  - To provide a convenient number representation for computer and digital systems.

---

* **Importance**
  - It provides a compact representation of binary data.
  - Each hexadecimal digit directly represents **4 binary bits**.
  - It is commonly used in computer architecture and digital systems.
  - It makes memory addresses and machine-level data easier to read.
  - It is important for understanding digital electronics, processors, RTL, FPGA, ASIC, and VLSI systems.

---

* **Working Principle**
  - The Hexadecimal System uses **base 16**.
  - It has sixteen symbols:

**0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F**

  - The letters represent values greater than 9:

**A = 10**

**B = 11**

**C = 12**

**D = 13**

**E = 14**

**F = 15**

  - Each position represents a power of 16.
  - The positional weights increase from right to left.

For example:

**2A7₁₆**

The positional weights are:

**16²  16¹  16⁰**

**256  16  1**

Therefore:

**2A7₁₆ = (2 × 256) + (A × 16) + (7 × 1)**

Since:

**A = 10**

**= 512 + 160 + 7**

**= 679₁₀**

---

* **Number Representation**

A hexadecimal number can be written as:

**(dₙdₙ₋₁...d₂d₁d₀)₁₆**

Its decimal value is:

**dₙ × 16ⁿ + dₙ₋₁ × 16ⁿ⁻¹ + ... + d₂ × 16² + d₁ × 16¹ + d₀ × 16⁰**

Where each digit can have a value from **0 to 15**.

---

* **Hexadecimal Digits**

| Hexadecimal | Decimal | Binary |
|---|---:|---|
| 0 | 0 | 0000 |
| 1 | 1 | 0001 |
| 2 | 2 | 0010 |
| 3 | 3 | 0011 |
| 4 | 4 | 0100 |
| 5 | 5 | 0101 |
| 6 | 6 | 0110 |
| 7 | 7 | 0111 |
| 8 | 8 | 1000 |
| 9 | 9 | 1001 |
| A | 10 | 1010 |
| B | 11 | 1011 |
| C | 12 | 1100 |
| D | 13 | 1101 |
| E | 14 | 1110 |
| F | 15 | 1111 |

---

* **Hexadecimal Place Values**

| Position | Power of 16 | Value |
|---|---:|---:|
| 16⁰ | 0 | 1 |
| 16¹ | 1 | 16 |
| 16² | 2 | 256 |
| 16³ | 3 | 4096 |
| 16⁴ | 4 | 65536 |
| 16⁵ | 5 | 1048576 |
| 16⁶ | 6 | 16777216 |

---

* **Hexadecimal and Binary Relationship**

The most important relationship is:

**1 Hexadecimal Digit = 4 Binary Bits**

For example:

**A₁₆ = 1010₂**

**F₁₆ = 1111₂**

Consider:

**3F7₁₆**

Convert each hexadecimal digit separately:

**3 → 0011**

**F → 1111**

**7 → 0111**

Therefore:

**3F7₁₆ = 001111110111₂**

Leading zeros may be removed when they do not affect the value:

**3F7₁₆ = 1111110111₂**

---

* **Truth Table**

The Hexadecimal System does not have a conventional truth table because it is a number system rather than a logic operation.

The hexadecimal digits and their binary equivalents are:

| Hexadecimal | Binary |
|---|---|
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
| 8 | 1000 |
| 9 | 1001 |
| A | 1010 |
| B | 1011 |
| C | 1100 |
| D | 1101 |
| E | 1110 |
| F | 1111 |

---

* **Boolean Expression**

The Hexadecimal System itself does not use a Boolean expression.

Boolean expressions are used to describe digital logic operations. For example:

**Y = A.B**

The inputs and output of this operation are represented using binary logic values.

---

* **Input and Output Description**
  - Input:-
    - Hexadecimal digits from **0 to 9 and A to F**.
  - Output:-
    - Hexadecimal numbers formed using combinations of these sixteen symbols.

  - Hexadecimal numbers can represent:
    - Memory addresses.
    - Machine-level data.
    - Binary values.
    - Register contents.
    - Digital data.
    - Color codes in computing applications.

---

* **Working Example**

  - Consider the hexadecimal number:

**4B2₁₆**

  - Positional weights:

**16²  16¹  16⁰**

**256  16  1**

  - Calculation:

**4B2₁₆ = (4 × 256) + (B × 16) + (2 × 1)**

Since:

**B = 11**

**= 1024 + 176 + 2**

**= 1202₁₀**

Therefore:

**4B2₁₆ = 1202₁₀**

---

* **Hexadecimal to Binary Conversion**

To convert hexadecimal to binary:

  - Replace every hexadecimal digit with its corresponding 4-bit binary value.

Example:

**5A3₁₆**

**5 → 0101**

**A → 1010**

**3 → 0011**

Therefore:

**5A3₁₆ = 010110100011₂**

---

* **Binary to Hexadecimal Conversion**

To convert binary to hexadecimal:

  - Start grouping the binary number from the **right side**.
  - Divide the binary digits into groups of **4 bits**.
  - Add leading zeros to the left if required.
  - Convert each 4-bit group into its corresponding hexadecimal digit.

Example:

**110101101₂**

Group from the right:

**1 | 1010 | 1101**

Add leading zeros:

**0001 | 1010 | 1101**

Convert:

**0001 → 1**

**1010 → A**

**1101 → D**

Therefore:

**110101101₂ = 1AD₁₆**

---

* **Hexadecimal to Decimal Conversion**

To convert hexadecimal to decimal:

  - Multiply each digit by its corresponding power of 16.
  - Replace A–F with their decimal values.
  - Add all the resulting values.

Example:

**2C5₁₆**

**= (2 × 16²) + (C × 16¹) + (5 × 16⁰)**

Since:

**C = 12**

**= (2 × 256) + (12 × 16) + (5 × 1)**

**= 512 + 192 + 5**

**= 709₁₀**

Therefore:

**2C5₁₆ = 709₁₀**

---

* **Decimal to Hexadecimal Conversion**

To convert a decimal integer into hexadecimal:

  - Repeatedly divide the decimal number by **16**.
  - Record the remainder after each division.
  - Convert remainders from 10 to 15 into A to F.
  - Continue until the quotient becomes 0.
  - Read the remainders from bottom to top.

Example:

Convert **254₁₀** to hexadecimal.

| Division | Quotient | Remainder |
|---|---:|---:|
| 254 ÷ 16 | 15 | 14 |
| 15 ÷ 16 | 0 | 15 |

Convert the remainders:

**14 → E**

**15 → F**

Read from bottom to top:

**FE₁₆**

Therefore:

**254₁₀ = FE₁₆**

---

* **Applications**

  *The Hexadecimal System is used in:*

  - Computer Architecture.
  - Digital Electronics.
  - Memory Address Representation.
  - Register Representation.
  - Machine Code.
  - Assembly Programming.
  - Debugging.
  - Microprocessors.
  - Microcontrollers.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.
  - HTML and CSS Color Codes.

---

* **Advantages**
  - Very compact compared with binary.
  - One hexadecimal digit represents exactly 4 binary bits.
  - Easy conversion between binary and hexadecimal.
  - Easier for humans to read than long binary numbers.
  - Convenient for representing memory addresses and machine-level data.
  - Aligns naturally with 8-bit bytes because two hexadecimal digits represent one byte.

---

* **Limitations**
  - Less familiar to beginners than decimal.
  - Requires understanding of A–F symbols.
  - Digital hardware still processes the underlying information primarily in binary.
  - Manual calculations can be more difficult than decimal calculations for beginners.

---

* **Real-World Example**

  - A computer memory address may be represented in hexadecimal because hexadecimal provides a compact representation of binary addresses.

For example:

**0x7FFF**

The prefix **0x** commonly indicates that the following value is hexadecimal.

  - Hexadecimal is also widely used for representing binary data during debugging and low-level programming.
  - In web development, colors are commonly represented using hexadecimal notation.

For example:

**#FF0000**

represents a red color using hexadecimal values.

---

* **Key Points**
  - Hexadecimal is a **base-16 number system**.
  - It uses **16 symbols: 0–9 and A–F**.
  - **A = 10**, **B = 11**, **C = 12**, **D = 13**, **E = 14**, **F = 15**.
  - Each position represents a power of **16**.
  - **1 hexadecimal digit = 4 binary bits**.
  - **2 hexadecimal digits = 8 bits = 1 byte**.
  - Binary-to-hexadecimal conversion is performed by grouping bits into groups of 4.
  - Hexadecimal is widely used in computer architecture and low-level digital systems.
  - Hexadecimal makes long binary values compact and easier to read.

---

* **Interview Questions**

**1. What is the Hexadecimal System?**

**Answer:**

The Hexadecimal System is a base-16 positional number system that uses the symbols 0–9 and A–F to represent numerical values.

---

**2. What is the base of the Hexadecimal System?**

**Answer:**

The base of the Hexadecimal System is **16**.

---

**3. Which symbols are used in hexadecimal?**

**Answer:**

Hexadecimal uses:

**0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F**

---

**4. What do A to F represent in hexadecimal?**

**Answer:**

They represent decimal values from 10 to 15:

**A = 10**

**B = 11**

**C = 12**

**D = 13**

**E = 14**

**F = 15**

---

**5. How many binary bits are represented by one hexadecimal digit?**

**Answer:**

One hexadecimal digit represents **4 binary bits** because:

**16 = 2⁴**

---

**6. Convert A₁₆ to binary.**

**Answer:**

**A₁₆ = 1010₂**

---

**7. Convert F₁₆ to binary.**

**Answer:**

**F₁₆ = 1111₂**

---

**8. Convert 3A₁₆ to decimal.**

**Answer:**

**3A₁₆ = (3 × 16¹) + (A × 16⁰)**

**= (3 × 16) + (10 × 1)**

**= 48 + 10**

**= 58₁₀**

Therefore:

**3A₁₆ = 58₁₀**

---

**9. Convert 10101111₂ to hexadecimal.**

**Answer:**

Group into 4 bits:

**1010 | 1111**

**1010 → A**

**1111 → F**

Therefore:

**10101111₂ = AF₁₆**

---

**10. Why is hexadecimal preferred over binary for representing digital data?**

**Answer:**

Hexadecimal provides a much more compact representation. One hexadecimal digit represents four binary bits, making long binary values easier to read and write.

---

**11. Why is hexadecimal useful in computer architecture?**

**Answer:**

Hexadecimal is useful because memory addresses, register values, machine instructions, and binary data can be represented much more compactly than using binary notation.

---

**12. What does the prefix 0x mean?**

**Answer:**

The prefix **0x** is commonly used in programming and computer systems to indicate that the following number is written in hexadecimal notation.

Example:

**0xFF = FF₁₆**

---

**13. How many hexadecimal digits represent one byte?**

**Answer:**

Two hexadecimal digits represent one byte because:

**1 hexadecimal digit = 4 bits**

Therefore:

**2 × 4 = 8 bits = 1 byte**

---

**14. What is the difference between octal and hexadecimal?**

**Answer:**

Octal is a base-8 system where one digit represents **3 binary bits**, while hexadecimal is a base-16 system where one digit represents **4 binary bits**.

---

**15. Why is hexadecimal important in VLSI and RTL design?**

**Answer:**

Hexadecimal provides a compact way to represent binary values such as register contents, memory data, addresses, masks, and simulation values, making RTL development and debugging easier.

---

* **Quick Revision**
  - Number System → **Hexadecimal**
  - Base → **16**
  - Digits → **0–9, A–F**
  - A–F Values → **10–15**
  - Positional Weights → Powers of **16**
  - 1 Hex Digit → **4 Binary Bits**
  - 2 Hex Digits → **8 Bits / 1 Byte**
  - Binary → Hexadecimal → Group into **4 bits**
  - Hexadecimal → Binary → Replace each digit with **4 bits**
  - Common Prefix → **0x**
  - Main Use → Computer and Digital System Representation

---

* **Summary**

The **Hexadecimal System** is a base-16 positional number system that uses the digits **0–9** and letters **A–F**. Its most important feature is its direct relationship with binary, where each hexadecimal digit represents exactly four binary bits. This makes hexadecimal an efficient and readable representation of binary data. It is widely used in computer architecture, memory addresses, registers, machine-level programming, debugging, FPGA, ASIC, RTL, and VLSI systems.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
