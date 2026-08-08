# **Decimal System**

* **Overview**

The **Decimal System** is a number system that uses ten digits, **0 to 9**, to represent numerical values. It is the most commonly used number system in everyday life and is also important for understanding conversions between decimal and other number systems used in digital electronics.

---

* **Definition**

The **Decimal System** is a base-10 number system in which each digit has a positional value based on powers of **10**.

---

* **Purpose**
  - To represent numerical values using ten digits.
  - To perform everyday counting and arithmetic operations.
  - To provide a human-friendly number representation.
  - To convert values between decimal and other number systems.
  - To understand number-system conversions used in digital electronics.

---

* **Importance**
  - It is the most commonly used number system in everyday life.
  - It provides the basis for conventional arithmetic calculations.
  - It is frequently used to display numerical results from digital systems.
  - It is important for converting between decimal, binary, octal, and hexadecimal systems.
  - It helps understand positional number representation.

---

* **Working Principle**
  - The Decimal System uses **base 10**.
  - It has ten digits:

**0, 1, 2, 3, 4, 5, 6, 7, 8, 9**

  - Each position represents a power of 10.
  - The positional weights increase from right to left.

For example:

**5832₁₀**

The positional weights are:

**10³  10²  10¹  10⁰**

**1000  100  10  1**

Therefore:

**5832₁₀ = (5 × 1000) + (8 × 100) + (3 × 10) + (2 × 1)**

**= 5000 + 800 + 30 + 2**

**= 5832**

genui{"integer_number_operations_learning_block":{"type_id":"PLACE_VALUE"}}

---

* **Number Representation**

A decimal number can be written as:

**(dₙdₙ₋₁...d₂d₁d₀)₁₀**

Its value is:

**dₙ × 10ⁿ + dₙ₋₁ × 10ⁿ⁻¹ + ... + d₂ × 10² + d₁ × 10¹ + d₀ × 10⁰**

Where each digit **d** can have a value from **0 to 9**.

---

* **Decimal Place Values**

| Position | Power of 10 | Value |
|---|---:|---:|
| 10⁰ | 0 | 1 |
| 10¹ | 1 | 10 |
| 10² | 2 | 100 |
| 10³ | 3 | 1000 |
| 10⁴ | 4 | 10000 |
| 10⁵ | 5 | 100000 |
| 10⁶ | 6 | 1000000 |

---

* **Decimal Fractions**

The Decimal System can also represent fractional values using positions to the right of the decimal point.

For example:

**25.375₁₀**

The positional values are:

**10¹  10⁰  .  10⁻¹  10⁻²  10⁻³**

Therefore:

**25.375 = (2 × 10) + (5 × 1) + (3 × 10⁻¹) + (7 × 10⁻²) + (5 × 10⁻³)**

**= 20 + 5 + 0.3 + 0.07 + 0.005**

**= 25.375**

---

* **Truth Table**

The Decimal System is a positional number system and does not have a conventional truth table.

The ten available decimal digits are:

| Decimal Digit | Value |
|---|---:|
| 0 | Zero |
| 1 | One |
| 2 | Two |
| 3 | Three |
| 4 | Four |
| 5 | Five |
| 6 | Six |
| 7 | Seven |
| 8 | Eight |
| 9 | Nine |

---

* **Boolean Expression**

The Decimal System itself does not use Boolean expressions.

Boolean expressions are primarily used to describe digital logic operations. For example:

**Y = A.B**

The values of **A**, **B**, and **Y** can be represented using binary logic.

---

* **Input and Output Description**
  - Input:-
    - Decimal digits from **0 to 9**.
  - Output:-
    - Decimal numbers formed using combinations of the digits **0 to 9**.

  - Decimal numbers can represent:
    - Integers.
    - Fractions.
    - Measurements.
    - Quantities.
    - Numerical results from digital systems.

---

* **Working Example**

  - Consider the decimal number:

**4726₁₀**

  - Positional weights:

**10³  10²  10¹  10⁰**

**1000  100  10  1**

  - Calculation:

**4726 = (4 × 1000) + (7 × 100) + (2 × 10) + (6 × 1)**

**= 4000 + 700 + 20 + 6**

**= 4726**

Therefore, the value of **4726₁₀** is **4726** in decimal representation.

---

* **Binary to Decimal Conversion**

To convert a binary number into decimal:

  - Multiply each binary digit by its corresponding power of 2.
  - Add all the resulting values.

Example:

**1011₂**

**= (1 × 2³) + (0 × 2²) + (1 × 2¹) + (1 × 2⁰)**

**= 8 + 0 + 2 + 1**

**= 11₁₀**

Therefore:

**1011₂ = 11₁₀**

---

* **Decimal to Binary Conversion**

To convert a decimal integer into binary:

  - Repeatedly divide the decimal number by **2**.
  - Record the remainder after each division.
  - Continue until the quotient becomes 0.
  - Read the remainders from bottom to top.

Example:

Convert **13₁₀** into binary.

| Division | Quotient | Remainder |
|---|---:|---:|
| 13 ÷ 2 | 6 | 1 |
| 6 ÷ 2 | 3 | 0 |
| 3 ÷ 2 | 1 | 1 |
| 1 ÷ 2 | 0 | 1 |

Reading the remainders from bottom to top:

**13₁₀ = 1101₂**

---

* **Applications**

  *The Decimal System is used in:*

  - Everyday Counting.
  - Financial Calculations.
  - Measurements.
  - Engineering Calculations.
  - Scientific Calculations.
  - Digital System Displays.
  - Computer Input and Output.
  - Number-System Conversion.
  - Digital Electronics.
  - VLSI and RTL Design Calculations.

---

* **Advantages**
  - Easy for humans to understand.
  - Uses familiar digits from 0 to 9.
  - Convenient for everyday calculations.
  - Supports straightforward arithmetic operations.
  - Provides an easy way to interpret numerical results.

---

* **Limitations**
  - Digital electronic circuits do not naturally operate using ten distinct logic states.
  - Decimal numbers must often be converted to binary for processing inside digital systems.
  - Large decimal values can require more hardware when directly encoded in some digital representations.
  - Decimal representation is less natural for basic two-state digital logic than binary representation.

---

* **Real-World Example**
  - When a digital thermometer displays:

**37.5°C**

the temperature is presented to the user in decimal form.

  - Internally, the sensor data may be converted and processed using binary values.
  - The digital system then converts the processed value into a decimal representation for display.

**Sensor → Digital Processing → Decimal Display**

---

* **Key Points**
  - Decimal is a **base-10 number system**.
  - It uses **10 digits: 0 to 9**.
  - Each position represents a power of **10**.
  - The rightmost integer position has a weight of **10⁰**.
  - The position to the left has a weight of **10¹**, then **10²**, and so on.
  - Decimal fractions use negative powers of 10.
  - Decimal is mainly used for human-readable numerical representation.
  - Digital systems commonly convert decimal values into binary for internal processing.

---

* **Interview Questions**

**1. What is the Decimal System?**

**Answer:**

The Decimal System is a base-10 number system that uses ten digits, from 0 to 9, to represent numerical values.

---

**2. What is the base of the Decimal System?**

**Answer:**

The base of the Decimal System is **10**.

---

**3. How many digits are used in the Decimal System?**

**Answer:**

Ten digits are used:

**0, 1, 2, 3, 4, 5, 6, 7, 8, 9**

---

**4. What is the positional value of the rightmost digit in an integer decimal number?**

**Answer:**

The rightmost digit has a positional weight of:

**10⁰ = 1**

---

**5. What is the place value of the digit 5 in 3527?**

**Answer:**

The digit 5 is in the hundreds position.

Therefore:

**5 × 100 = 500**

---

**6. Why is decimal called a positional number system?**

**Answer:**

It is called a positional number system because the value of a digit depends on both the digit itself and its position in the number.

---

**7. Convert 25₁₀ to binary.**

**Answer:**

**25₁₀ = 11001₂**

Because:

**25 = 16 + 8 + 1**

---

**8. Convert 10101₂ to decimal.**

**Answer:**

**10101₂ = (1 × 16) + (0 × 8) + (1 × 4) + (0 × 2) + (1 × 1)**

**= 16 + 4 + 1**

**= 21₁₀**

Therefore:

**10101₂ = 21₁₀**

---

**9. Why is decimal commonly used by humans instead of binary?**

**Answer:**

Decimal is easier for humans to read and perform everyday calculations with, while binary is more suitable for electronic circuits because digital hardware naturally operates with two primary logic states.

---

**10. Is decimal directly used inside digital circuits?**

**Answer:**

Digital circuits primarily process binary information. Decimal values can be represented using binary or special encodings such as **Binary-Coded Decimal (BCD)** when decimal digit representation is required.

---

**11. What is the difference between decimal and binary systems?**

**Answer:**

Decimal is a **base-10** system using digits 0–9, while binary is a **base-2** system using only 0 and 1.

---

**12. Why is decimal-to-binary conversion important in digital electronics?**

**Answer:**

It is important because humans commonly work with decimal values, while digital circuits and processors internally process information using binary values.

---

* **Quick Revision**
  - Number System → **Decimal**
  - Base → **10**
  - Digits → **0 to 9**
  - Integer Place Values → Powers of **10**
  - Rightmost Integer Position → **10⁰**
  - Main Use → Human-readable numerical representation
  - Digital Internal Representation → Usually Binary
  - Decimal → Binary → Repeated division by 2
  - Binary → Decimal → Positional-weight method
  - Important in → Digital Electronics and Number-System Conversion

---

* **Summary**

The **Decimal System** is a base-10 positional number system that uses the ten digits **0 to 9**. Each digit has a value determined by its position and the corresponding power of 10. Decimal is the primary number system used by humans for everyday calculations and numerical representation, while digital systems commonly use binary internally. Understanding the Decimal System and its conversion to and from binary is essential for learning digital electronics, computer architecture, Verilog, RTL design, FPGA, ASIC, and VLSI.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
