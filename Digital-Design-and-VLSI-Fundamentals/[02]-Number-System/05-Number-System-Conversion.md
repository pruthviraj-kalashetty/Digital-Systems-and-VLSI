# **Number System Conversion**

* **Overview**

**Number System Conversion** is the process of converting a numerical value from one number system to another without changing its actual value. It is an important concept in digital electronics because humans commonly use decimal numbers, while digital systems primarily process binary data.

---

* **Definition**

**Number System Conversion** is the mathematical process of changing a number from one base to another, such as binary, decimal, octal, or hexadecimal, while preserving the same numerical value.

---

* **Purpose**
  - To represent the same numerical value in different number systems.
  - To convert human-readable decimal values into binary values used by digital circuits.
  - To simplify the representation of long binary numbers using octal or hexadecimal.
  - To support communication between humans and digital systems.
  - To perform calculations and analysis in the most suitable number system.

---

* **Importance**
  - Essential for understanding digital electronics.
  - Helps convert decimal values into binary for digital circuit design.
  - Makes binary data easier to read using octal and hexadecimal.
  - Important for computer architecture and processor design.
  - Used extensively in Verilog, RTL, FPGA, ASIC, and VLSI design.
  - Helps engineers interpret memory addresses, register values, and simulation data.

---

* **Number Systems Used in Digital Electronics**

| Number System | Base | Digits Used | Common Representation |
|---|---:|---|---|
| Binary | 2 | 0, 1 | `101101₂` |
| Octal | 8 | 0–7 | `55₈` |
| Decimal | 10 | 0–9 | `45₁₀` |
| Hexadecimal | 16 | 0–9, A–F | `2D₁₆` |

---

* **Working Principle**

Number system conversion is based on the **base** and **positional weights** of each number system.

The four commonly used systems are:

**Binary → Base 2**

**Octal → Base 8**

**Decimal → Base 10**

**Hexadecimal → Base 16**

The conversion method depends on the source and destination number systems.

---

* **Conversion Methods**

  - **Decimal → Binary**
    - Repeated division by **2**.

  - **Binary → Decimal**
    - Positional-weight method using powers of **2**.

  - **Decimal → Octal**
    - Repeated division by **8**.

  - **Octal → Decimal**
    - Positional-weight method using powers of **8**.

  - **Decimal → Hexadecimal**
    - Repeated division by **16**.

  - **Hexadecimal → Decimal**
    - Positional-weight method using powers of **16**.

  - **Binary → Octal**
    - Group binary digits into groups of **3**.

  - **Octal → Binary**
    - Replace every octal digit with its **3-bit binary equivalent**.

  - **Binary → Hexadecimal**
    - Group binary digits into groups of **4**.

  - **Hexadecimal → Binary**
    - Replace every hexadecimal digit with its **4-bit binary equivalent**.

---

* **Binary to Decimal Conversion**

To convert binary to decimal:

  - Multiply each binary digit by its corresponding power of 2.
  - Add the resulting values.

Example:

**101101₂**

**= (1 × 2⁵) + (0 × 2⁴) + (1 × 2³) + (1 × 2²) + (0 × 2¹) + (1 × 2⁰)**

**= 32 + 0 + 8 + 4 + 0 + 1**

**= 45₁₀**

Therefore:

**101101₂ = 45₁₀**

---

* **Decimal to Binary Conversion**

To convert decimal to binary:

  - Divide the decimal number repeatedly by **2**.
  - Record the remainders.
  - Read the remainders from bottom to top.

Example:

Convert **45₁₀** to binary.

| Division | Quotient | Remainder |
|---|---:|---:|
| 45 ÷ 2 | 22 | 1 |
| 22 ÷ 2 | 11 | 0 |
| 11 ÷ 2 | 5 | 1 |
| 5 ÷ 2 | 2 | 1 |
| 2 ÷ 2 | 1 | 0 |
| 1 ÷ 2 | 0 | 1 |

Read from bottom to top:

**101101₂**

Therefore:

**45₁₀ = 101101₂**

---

* **Binary to Octal Conversion**

To convert binary to octal:

  - Start grouping from the right.
  - Divide the binary number into groups of **3 bits**.
  - Add leading zeros if necessary.
  - Convert each group into an octal digit.

Example:

**101101₂**

Group:

**101 | 101**

Convert:

**101 → 5**

**101 → 5**

Therefore:

**101101₂ = 55₈**

---

* **Octal to Binary Conversion**

To convert octal to binary:

  - Replace every octal digit with its corresponding 3-bit binary value.

Example:

**55₈**

**5 → 101**

**5 → 101**

Therefore:

**55₈ = 101101₂**

---

* **Binary to Hexadecimal Conversion**

To convert binary to hexadecimal:

  - Start grouping from the right.
  - Divide the binary number into groups of **4 bits**.
  - Add leading zeros if necessary.
  - Convert each group into its hexadecimal equivalent.

Example:

**101101₂**

Group:

**10 | 1101**

Add leading zeros:

**0010 | 1101**

Convert:

**0010 → 2**

**1101 → D**

Therefore:

**101101₂ = 2D₁₆**

---

* **Hexadecimal to Binary Conversion**

To convert hexadecimal to binary:

  - Replace every hexadecimal digit with its corresponding 4-bit binary value.

Example:

**2D₁₆**

**2 → 0010**

**D → 1101**

Therefore:

**2D₁₆ = 00101101₂**

---

* **Decimal to Octal Conversion**

To convert decimal to octal:

  - Repeatedly divide the decimal number by **8**.
  - Record the remainders.
  - Read the remainders from bottom to top.

Example:

Convert **45₁₀** to octal.

| Division | Quotient | Remainder |
|---|---:|---:|
| 45 ÷ 8 | 5 | 5 |
| 5 ÷ 8 | 0 | 5 |

Therefore:

**45₁₀ = 55₈**

---

* **Octal to Decimal Conversion**

To convert octal to decimal:

  - Multiply each digit by its corresponding power of 8.
  - Add the results.

Example:

**55₈**

**= (5 × 8¹) + (5 × 8⁰)**

**= 40 + 5**

**= 45₁₀**

Therefore:

**55₈ = 45₁₀**

---

* **Decimal to Hexadecimal Conversion**

To convert decimal to hexadecimal:

  - Repeatedly divide the decimal number by **16**.
  - Record the remainders.
  - Convert remainders 10–15 into A–F.
  - Read the remainders from bottom to top.

Example:

Convert **45₁₀** to hexadecimal.

| Division | Quotient | Remainder |
|---|---:|---:|
| 45 ÷ 16 | 2 | 13 |
| 2 ÷ 16 | 0 | 2 |

**13 → D**

Therefore:

**45₁₀ = 2D₁₆**

---

* **Hexadecimal to Decimal Conversion**

To convert hexadecimal to decimal:

  - Multiply each digit by its corresponding power of 16.
  - Convert A–F into decimal values.
  - Add the results.

Example:

**2D₁₆**

**= (2 × 16¹) + (D × 16⁰)**

Since:

**D = 13**

**= 32 + 13**

**= 45₁₀**

Therefore:

**2D₁₆ = 45₁₀**

---

* **Octal to Hexadecimal Conversion**

The easiest method is:

**Octal → Binary → Hexadecimal**

Example:

**55₈**

First convert octal to binary:

**5 → 101**

**5 → 101**

Therefore:

**55₈ = 101101₂**

Group into 4 bits:

**0010 | 1101**

Convert:

**0010 → 2**

**1101 → D**

Therefore:

**55₈ = 2D₁₆**

---

* **Hexadecimal to Octal Conversion**

The easiest method is:

**Hexadecimal → Binary → Octal**

Example:

**2D₁₆**

Convert to binary:

**2 → 0010**

**D → 1101**

Therefore:

**2D₁₆ = 00101101₂**

Group into 3 bits from the right:

**00 | 101 | 101**

Add leading zeros:

**000 | 101 | 101**

Convert:

**000 → 0**

**101 → 5**

**101 → 5**

Therefore:

**2D₁₆ = 55₈**

---

* **Conversion Reference Table**

| From | To | Main Method |
|---|---|---|
| Binary | Decimal | Positional weights of 2 |
| Decimal | Binary | Repeated division by 2 |
| Binary | Octal | Group 3 bits |
| Octal | Binary | 1 digit → 3 bits |
| Binary | Hexadecimal | Group 4 bits |
| Hexadecimal | Binary | 1 digit → 4 bits |
| Decimal | Octal | Repeated division by 8 |
| Octal | Decimal | Positional weights of 8 |
| Decimal | Hexadecimal | Repeated division by 16 |
| Hexadecimal | Decimal | Positional weights of 16 |
| Octal | Hexadecimal | Octal → Binary → Hexadecimal |
| Hexadecimal | Octal | Hexadecimal → Binary → Octal |

---

* **Truth Table**

Number system conversion does not have a conventional truth table because it is a mathematical representation process rather than a Boolean logic operation.

However, the basic binary, octal, and hexadecimal relationships are:

| Binary | Octal | Decimal | Hexadecimal |
|---|---:|---:|---|
| 0000 | 0 | 0 | 0 |
| 0001 | 1 | 1 | 1 |
| 0010 | 2 | 2 | 2 |
| 0011 | 3 | 3 | 3 |
| 0100 | 4 | 4 | 4 |
| 0101 | 5 | 5 | 5 |
| 0110 | 6 | 6 | 6 |
| 0111 | 7 | 7 | 7 |
| 1000 | 10 | 8 | 8 |
| 1001 | 11 | 9 | 9 |
| 1010 | 12 | 10 | A |
| 1011 | 13 | 11 | B |
| 1100 | 14 | 12 | C |
| 1101 | 15 | 13 | D |
| 1110 | 16 | 14 | E |
| 1111 | 17 | 15 | F |

---

* **Boolean Expression**

Number system conversion itself does not use a Boolean expression.

Boolean expressions are used for digital logic operations, while number system conversion is used to represent the same numerical value using different bases.

For example:

**45₁₀ = 101101₂ = 55₈ = 2D₁₆**

All four representations represent the same numerical value.

---

* **Input and Output Description**
  - Input:-
    - A number represented in one number system.
  - Output:-
    - The equivalent number represented in another number system.

  - Common inputs and outputs include:
    - Binary.
    - Decimal.
    - Octal.
    - Hexadecimal.

---

* **Working Example**

Consider the decimal number:

**45₁₀**

Its equivalent representations are:

**45₁₀ = 101101₂**

**45₁₀ = 55₈**

**45₁₀ = 2D₁₆**

Therefore:

**101101₂ = 45₁₀ = 55₈ = 2D₁₆**

The numerical value remains the same; only the representation changes.

---

* **Applications**

  *Number System Conversion is used in:*

  - Digital Electronics.
  - Computer Architecture.
  - Processor Design.
  - Memory Address Representation.
  - Register Representation.
  - Verilog and SystemVerilog.
  - RTL Design.
  - FPGA Design.
  - ASIC Design.
  - VLSI Design.
  - Embedded Systems.
  - Microprocessor Programming.
  - Debugging and Simulation.
  - Low-Level Programming.

---

* **Advantages**
  - Allows the same value to be represented in different formats.
  - Makes binary data easier to understand.
  - Simplifies digital system calculations.
  - Helps engineers interpret memory and register values.
  - Supports communication between human-readable and machine-oriented representations.
  - Makes binary data compact using octal and hexadecimal.

---

* **Limitations**
  - Conversion can become time-consuming for very large numbers when performed manually.
  - Different number systems require different conversion methods.
  - Manual conversion can lead to calculation errors.
  - Beginners may find hexadecimal and octal notation confusing initially.

---

* **Real-World Example**

  - In RTL and Verilog design, binary values are commonly used to describe individual bits, while hexadecimal values are often used to represent wider buses.

For example:

**8'b10101111**

can also be represented as:

**8'hAF**

Both represent the same 8-bit value.

**10101111₂ = AF₁₆**

This makes hexadecimal notation convenient when working with registers, memory values, counters, and simulation results.

---

* **Key Points**
  - Number system conversion changes the **representation**, not the numerical value.
  - Binary uses base **2**.
  - Octal uses base **8**.
  - Decimal uses base **10**.
  - Hexadecimal uses base **16**.
  - Binary → Octal uses groups of **3 bits**.
  - Binary → Hexadecimal uses groups of **4 bits**.
  - Decimal → Binary uses repeated division by **2**.
  - Decimal → Octal uses repeated division by **8**.
  - Decimal → Hexadecimal uses repeated division by **16**.
  - Octal ↔ Hexadecimal conversion can be performed through binary.
  - Number system conversion is fundamental to digital electronics and VLSI.

---

* **Interview Questions**

**1. What is Number System Conversion?**

**Answer:**

Number System Conversion is the process of representing the same numerical value in a different number system or base.

---

**2. What are the four commonly used number systems in digital electronics?**

**Answer:**

The four commonly used number systems are:

- Binary — Base 2.
- Octal — Base 8.
- Decimal — Base 10.
- Hexadecimal — Base 16.

---

**3. How do you convert binary to decimal?**

**Answer:**

Multiply each binary digit by its corresponding power of 2 and add all the results.

---

**4. How do you convert decimal to binary?**

**Answer:**

Repeatedly divide the decimal number by 2, record the remainders, and read the remainders from bottom to top.

---

**5. How do you convert binary to octal?**

**Answer:**

Group the binary digits into groups of 3 bits from the right and convert each group into its corresponding octal digit.

---

**6. How do you convert binary to hexadecimal?**

**Answer:**

Group the binary digits into groups of 4 bits from the right and convert each group into its corresponding hexadecimal digit.

---

**7. Why can octal be directly converted to binary?**

**Answer:**

Because one octal digit represents exactly 3 binary bits:

**8 = 2³**

---

**8. Why can hexadecimal be directly converted to binary?**

**Answer:**

Because one hexadecimal digit represents exactly 4 binary bits:

**16 = 2⁴**

---

**9. Convert 110101₂ to decimal.**

**Answer:**

**110101₂ = (1 × 32) + (1 × 16) + (0 × 8) + (1 × 4) + (0 × 2) + (1 × 1)**

**= 32 + 16 + 4 + 1**

**= 53₁₀**

Therefore:

**110101₂ = 53₁₀**

---

**10. Convert 53₁₀ to binary.**

**Answer:**

**53₁₀ = 110101₂**

---

**11. Convert 53₁₀ to octal.**

**Answer:**

**53₁₀ = 65₈**

---

**12. Convert 53₁₀ to hexadecimal.**

**Answer:**

**53₁₀ = 35₁₆**

---

**13. Convert 65₈ to hexadecimal.**

**Answer:**

Convert octal to binary:

**6 → 110**

**5 → 101**

Therefore:

**65₈ = 110101₂**

Group into 4 bits:

**0011 | 0101**

Therefore:

**65₈ = 35₁₆**

---

**14. Which number system is mainly used internally by digital circuits?**

**Answer:**

Digital circuits primarily use the **Binary System** because electronic logic circuits are designed around two main logic states.

---

**15. Why is hexadecimal widely used in digital design?**

**Answer:**

Hexadecimal provides a compact representation of binary data because one hexadecimal digit represents four binary bits. This makes registers, memory addresses, and simulation values easier to read.

---

**16. Why is number system conversion important in VLSI?**

**Answer:**

Number system conversion is important because VLSI engineers work with binary logic, hexadecimal register values, memory addresses, simulation results, and numerical specifications. Conversion allows these values to be interpreted and represented conveniently.

---

* **Quick Revision**
  - Binary → **Base 2**
  - Octal → **Base 8**
  - Decimal → **Base 10**
  - Hexadecimal → **Base 16**
  - Binary → Decimal → **Powers of 2**
  - Decimal → Binary → **Divide by 2**
  - Binary → Octal → **Group 3 bits**
  - Octal → Binary → **3 bits per digit**
  - Binary → Hexadecimal → **Group 4 bits**
  - Hexadecimal → Binary → **4 bits per digit**
  - Decimal → Octal → **Divide by 8**
  - Decimal → Hexadecimal → **Divide by 16**
  - Same Value → **Different Representation**

---

* **Summary**

**Number System Conversion** is an essential concept in digital electronics that allows the same numerical value to be represented using different bases. Binary is primarily used by digital circuits, decimal is commonly used by humans, and octal and hexadecimal provide compact representations of binary data. Understanding these conversions is fundamental for digital logic, computer architecture, Verilog, RTL design, FPGA, ASIC, and VLSI engineering.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
