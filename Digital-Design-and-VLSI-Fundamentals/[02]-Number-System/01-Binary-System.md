# **Binary System**

* **Overview**

The **Binary System** is a number system that uses only two digits, **0 and 1**, to represent numerical values and information. It is the fundamental number system used by digital electronic circuits, computers, processors, memory, FPGA, ASIC, and VLSI systems.

---

* **Definition**

The **Binary System** is a base-2 number system in which every number is represented using only two digits, **0 and 1**.

---

* **Purpose**
  - To represent digital information using two distinct states.
  - To provide a simple numerical system for digital electronic circuits.
  - To represent data and instructions inside computers.
  - To perform arithmetic and logical operations in digital systems.
  - To form the foundation of digital electronics and computer architecture.

---

* **Importance**
  - It is the fundamental number system used in digital electronics.
  - Digital circuits naturally operate using two logic states.
  - It is used to represent data inside processors and memory.
  - It forms the foundation for Boolean logic and digital circuit design.
  - It is essential for understanding Verilog, RTL design, FPGA, ASIC, and VLSI.

---

* **Working Principle**
  - The Binary System uses **base 2**.
  - It has only two digits:
    - **0**
    - **1**
  - Each position in a binary number represents a power of 2.
  - The position values increase from right to left.

For example:

**1011₂**

The positional weights are:

**2³  2²  2¹  2⁰**

**8   4   2   1**

Therefore:

**1011₂ = (1 × 8) + (0 × 4) + (1 × 2) + (1 × 1)**

**1011₂ = 8 + 0 + 2 + 1**

**1011₂ = 11₁₀**

---

* **Number Representation**

A binary number can be written as:

**(bₙbₙ₋₁...b₂b₁b₀)₂**

Its decimal value is:

**bₙ × 2ⁿ + bₙ₋₁ × 2ⁿ⁻¹ + ... + b₂ × 2² + b₁ × 2¹ + b₀ × 2⁰**

Where each binary digit **b** can have a value of either **0 or 1**.

---

* **Common Binary Terms**

  - **Bit:** A single binary digit, either 0 or 1.
  - **Nibble:** A group of 4 bits.
  - **Byte:** A group of 8 bits.
  - **Word:** A group of bits processed as a unit by a processor. Its size depends on the architecture.
  - **MSB:** Most Significant Bit, the leftmost bit.
  - **LSB:** Least Significant Bit, the rightmost bit.

Example:

**10110110**

- MSB → **1**
- LSB → **0**
- Number of bits → **8**
- Size → **1 Byte**

---

* **Binary Place Values**

| Position | Power of 2 | Value |
|---|---:|---:|
| 2⁰ | 0 | 1 |
| 2¹ | 1 | 2 |
| 2² | 2 | 4 |
| 2³ | 3 | 8 |
| 2⁴ | 4 | 16 |
| 2⁵ | 5 | 32 |
| 2⁶ | 6 | 64 |
| 2⁷ | 7 | 128 |
| 2⁸ | 8 | 256 |

---

* **Truth Table**

The binary system has two possible values:

| Binary Digit | Meaning |
|---|---|
| 0 | LOW / OFF |
| 1 | HIGH / ON |

The exact electrical voltage represented by 0 and 1 depends on the digital logic technology.

---

* **Boolean Expression**

Binary values are also used in Boolean algebra.

For example:

**A = 0**

or

**A = 1**

A simple AND operation is:

**Y = A.B**

Example:

**A = 1**

**B = 1**

Therefore:

**Y = 1 × 1 = 1**

---

* **Input and Output Description**
  - Input:-
    - Binary digits **0 and 1**.
  - Output:-
    - A binary number represented using combinations of **0 and 1**.

  - A binary number can represent:
    - Numerical values.
    - Characters.
    - Instructions.
    - Control information.
    - Digital data.

---

* **Working Example**

  - Convert the binary number **1101₂** into decimal.

  - Binary number:

**1101₂**

  - Positional weights:

**2³  2²  2¹  2⁰**

**8   4   2   1**

  - Calculation:

**1101₂ = (1 × 8) + (1 × 4) + (0 × 2) + (1 × 1)**

**= 8 + 4 + 0 + 1**

**= 13₁₀**

Therefore:

**1101₂ = 13₁₀**

---

* **Binary to Decimal Conversion**

To convert a binary number to decimal:

  - Write the powers of 2 from right to left.
  - Multiply each binary digit by its corresponding power of 2.
  - Add all the resulting values.

Example:

**10110₂**

**= (1 × 16) + (0 × 8) + (1 × 4) + (1 × 2) + (0 × 1)**

**= 16 + 0 + 4 + 2 + 0**

**= 22₁₀**

Therefore:

**10110₂ = 22₁₀**

---

* **Decimal to Binary Conversion**

To convert a decimal number to binary, repeatedly divide the number by **2** and record the remainders.

Example:

Convert **13₁₀** to binary.

| Division | Quotient | Remainder |
|---|---:|---:|
| 13 ÷ 2 | 6 | 1 |
| 6 ÷ 2 | 3 | 0 |
| 3 ÷ 2 | 1 | 1 |
| 1 ÷ 2 | 0 | 1 |

Read the remainders from bottom to top:

**1101₂**

Therefore:

**13₁₀ = 1101₂**

---

* **Applications**

  *The Binary System is used in:*

  - Digital Electronics.
  - Computers.
  - Microprocessors.
  - Microcontrollers.
  - Memory Systems.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - Digital Communication.
  - Computer Architecture.
  - VLSI Systems.
  - Embedded Systems.

---

* **Advantages**
  - Simple representation using only two digits.
  - Matches the two-state nature of digital circuits.
  - Easy to implement using electronic switching devices.
  - Provides reliable digital data representation.
  - Suitable for Boolean logic operations.
  - Easy to store and process electronically.

---

* **Limitations**
  - Binary numbers can become long compared with decimal representation.
  - Manual calculations can be difficult for large binary values.
  - Binary representation is less convenient for humans to read directly.
  - Conversion may be required when interacting with decimal-based systems.

---

* **Real-World Example**

  - A computer stores and processes information using binary values.
  - For example, the decimal number **5** is represented as:

**5₁₀ = 101₂**

  - A processor can perform operations on these binary values using digital logic circuits such as:
    - Adders.
    - Subtractors.
    - Multiplexers.
    - ALUs.
    - Registers.
    - Memory.

  - At the hardware level, transistors and logic gates implement the operations required to process these binary states.

---

* **Key Points**
  - Binary is a **base-2 number system**.
  - It uses only **0 and 1**.
  - Each position represents a power of **2**.
  - The rightmost position has a weight of **2⁰**.
  - The leftmost bit is called the **MSB**.
  - The rightmost bit is called the **LSB**.
  - 4 bits = **1 Nibble**.
  - 8 bits = **1 Byte**.
  - Binary is the fundamental number system of digital electronics.
  - Binary arithmetic is essential for digital circuit and VLSI design.

---

* **Interview Questions**

**1. What is the Binary System?**

**Answer:**

The Binary System is a base-2 number system that uses only two digits, 0 and 1, to represent numerical values and digital information.

---

**2. Why is binary used in digital electronics?**

**Answer:**

Binary is used because digital electronic circuits can reliably represent two distinct logic states, commonly called logic 0 and logic 1.

---

**3. What is the base of the Binary System?**

**Answer:**

The base of the Binary System is **2**.

---

**4. How many digits are used in binary?**

**Answer:**

Binary uses two digits:

**0 and 1**

---

**5. What is a bit?**

**Answer:**

A bit is the smallest unit of digital information and can have one of two values, **0 or 1**.

---

**6. What is an MSB?**

**Answer:**

MSB stands for **Most Significant Bit**. It is the leftmost bit of a binary number and generally has the highest positional weight.

---

**7. What is an LSB?**

**Answer:**

LSB stands for **Least Significant Bit**. It is the rightmost bit of a binary number and has the lowest positional weight, which is **2⁰**.

---

**8. What is a nibble?**

**Answer:**

A nibble is a group of **4 bits**.

Example:

**1010₂**

---

**9. What is a byte?**

**Answer:**

A byte is a group of **8 bits**.

Example:

**10110110₂**

---

**10. Convert 1010₂ to decimal.**

**Answer:**

**1010₂ = (1 × 8) + (0 × 4) + (1 × 2) + (0 × 1)**

**= 8 + 0 + 2 + 0**

**= 10₁₀**

Therefore:

**1010₂ = 10₁₀**

---

**11. Convert 15₁₀ to binary.**

**Answer:**

**15₁₀ = 1111₂**

Because:

**15 = 8 + 4 + 2 + 1**

---

**12. What is the positional weight of the rightmost bit?**

**Answer:**

The rightmost bit has a positional weight of:

**2⁰ = 1**

---

**13. What is the maximum unsigned value represented by n bits?**

**Answer:**

The maximum unsigned value represented by **n bits** is:

**2ⁿ − 1**

For example, for 4 bits:

**2⁴ − 1 = 15**

Therefore, 4-bit unsigned numbers range from:

**0 to 15**

---

**14. How many different values can be represented using n bits?**

**Answer:**

**2ⁿ** different values can be represented using n bits.

For example:

**4 bits → 2⁴ = 16 values**

---

**15. Why is binary important in VLSI?**

**Answer:**

Binary is fundamental to VLSI because digital VLSI circuits process information using binary logic states implemented through transistors, logic gates, registers, memory, and other digital circuit structures.

---

* **Quick Revision**
  - Number System → **Binary**
  - Base → **2**
  - Digits → **0, 1**
  - Smallest Unit → **Bit**
  - 4 Bits → **Nibble**
  - 8 Bits → **Byte**
  - Leftmost Bit → **MSB**
  - Rightmost Bit → **LSB**
  - Positional Weights → Powers of **2**
  - n Bits → **2ⁿ Values**
  - Maximum Unsigned Value → **2ⁿ − 1**
  - Main Use → Digital Electronics and Computing

---

* **Summary**

The **Binary System** is the fundamental number system used in digital electronics and computing. It is a base-2 system that uses only **0 and 1**, with each position representing a power of 2. Binary numbers are used to represent data, perform arithmetic and logical operations, and control digital circuits. Understanding binary representation, positional weights, bits, nibbles, bytes, MSB, LSB, and binary conversion is essential for learning digital electronics, computer architecture, Verilog, RTL design, FPGA, ASIC, and VLSI.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
