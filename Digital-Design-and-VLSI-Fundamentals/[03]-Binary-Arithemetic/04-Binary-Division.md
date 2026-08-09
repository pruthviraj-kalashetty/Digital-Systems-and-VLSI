# **Binary Division**

* **Overview**

**Binary Division** is an arithmetic operation used to divide one binary number by another binary number. It follows a process similar to decimal long division, but it uses only the binary digits **0 and 1**. Binary division is an important operation under **Binary Arithmetic** and is used in digital systems, processors, ALUs, FPGA, ASIC, and VLSI designs.

---

* **Definition**

**Binary Division** is the process of dividing a binary number called the **Dividend** by another binary number called the **Divisor** to obtain a **Quotient** and, when applicable, a **Remainder**.

---

* **Purpose**
  - To perform division of binary numbers.
  - To calculate quotient and remainder in digital systems.
  - To support arithmetic operations in ALUs and processors.
  - To implement division algorithms in hardware.
  - To perform numerical calculations in FPGA, ASIC, and VLSI systems.

---

* **Importance**
  - It is one of the fundamental operations of **Binary Arithmetic**.
  - It is used in processors and ALUs.
  - It is required for arithmetic and mathematical operations.
  - It forms the basis of hardware divider circuits.
  - It is important for RTL, FPGA, ASIC, and VLSI design.

---

* **Binary Division Rules**

Binary division uses four basic cases:

| Dividend Bit | Divisor | Result |
|---|---|---|
| 0 | 1 | 0 |
| 1 | 1 | 1 |
| 0 | 0 | Undefined |
| 1 | 0 | Undefined |

Division by zero is **not allowed**.

The basic binary division rule is:

**1 ÷ 1 = 1**

and:

**0 ÷ 1 = 0**

---

* **Basic Terminology**

Binary division consists of four important terms:

  - **Dividend**
    - The number being divided.

  - **Divisor**
    - The number by which the dividend is divided.

  - **Quotient**
    - The result obtained after division.

  - **Remainder**
    - The value left after the division is completed.

The basic relationship is:

**Dividend = Divisor × Quotient + Remainder**

---

* **Working Principle**

Binary division is similar to decimal long division.

The basic process is:

**1. Start from the MSB of the dividend.**

**2. Compare the current partial dividend with the divisor.**

**3. If the partial dividend is greater than or equal to the divisor, write 1 in the quotient.**

**4. Subtract the divisor from the partial dividend.**

**5. If the partial dividend is smaller than the divisor, write 0 in the quotient.**

**6. Bring down the next bit of the dividend.**

**7. Repeat the process until all dividend bits are processed.**

**8. The final value remaining is the remainder.**

---

* **Input and Output Description**

  - Inputs:-
    - Dividend.
    - Divisor.

  - Outputs:-
    - Quotient.
    - Remainder.

For example:

**Dividend ÷ Divisor = Quotient**

and possibly:

**Remainder**

---

* **Working Example**

Consider:

**1100₂ ÷ 10₂**

Convert to decimal for verification:

**1100₂ = 12₁₀**

**10₂ = 2₁₀**

Therefore:

**12 ÷ 2 = 6**

And:

**6₁₀ = 110₂**

Binary division:

        110
      -----
    10 ) 1100
         10
         --
          10
          10
          --
           0

Therefore:

**1100₂ ÷ 10₂ = 110₂**

Quotient:

**110₂**

Remainder:

**0₂**

---

* **Working Example with Remainder**

Consider:

**1011₂ ÷ 10₂**

Convert to decimal:

**1011₂ = 11₁₀**

**10₂ = 2₁₀**

Therefore:

**11 ÷ 2 = 5 remainder 1**

Binary form:

**5₁₀ = 101₂**

**1₁₀ = 1₂**

Therefore:

**1011₂ ÷ 10₂ = 101₂ remainder 1₂**

---

* **Long Division Method**

Consider:

**1111₂ ÷ 11₂**

Binary long division:

        101
      -----
    11 ) 1111
         11
         --
          01
           1
          ---
           11
           11
           --
            0

Therefore:

**1111₂ ÷ 11₂ = 101₂**

Verification:

**101₂ × 11₂ = 1111₂**

Therefore:

**Quotient = 101₂**

**Remainder = 0₂**

---

* **Division by Powers of Two**

Binary division becomes very simple when dividing by powers of **2**.

Dividing by:

**2 = 2¹**

means shifting right by **1 bit**.

Dividing by:

**4 = 2²**

means shifting right by **2 bits**.

Dividing by:

**8 = 2³**

means shifting right by **3 bits**.

Example:

**11000₂ ÷ 2 = 1100₂**

Example:

**11000₂ ÷ 4 = 110₂**

Example:

**11000₂ ÷ 8 = 11₂**

Therefore, right shifting can be used to perform division by powers of two.

---

* **Right Shift and Binary Division**

For an unsigned binary number:

**A >> 1 = A ÷ 2**

**A >> 2 = A ÷ 4**

**A >> 3 = A ÷ 8**

Example:

**10100₂ >> 1 = 1010₂**

Therefore:

**10100₂ ÷ 2 = 1010₂**

---

* **Binary Division Algorithm**

A common hardware approach is the **Restoring Division Algorithm**.

The basic steps are:

  - Initialize the remainder register.
  - Shift the dividend and remainder.
  - Subtract the divisor from the partial remainder.
  - Check whether the result is negative.
  - If the result is non-negative, set the quotient bit to 1.
  - If the result is negative, restore the previous remainder and set the quotient bit to 0.
  - Repeat for all dividend bits.

---

* **Non-Restoring Division**

The **Non-Restoring Division Algorithm** is an alternative to the Restoring Division Algorithm.

Instead of restoring the remainder immediately after an unsuccessful subtraction, the algorithm uses the sign of the partial remainder to determine the next operation.

It can reduce some of the operations required during division.

---

* **Hardware Divider**

A hardware divider may contain:

  - Dividend register.
  - Divisor register.
  - Quotient register.
  - Remainder register.
  - Subtractor.
  - Shifter.
  - Control logic.

The hardware repeatedly performs shifting, comparison, subtraction, and quotient generation.

---

* **Division by Zero**

Division by zero is undefined.

For example:

**1010₂ ÷ 0000₂**

is not a valid mathematical operation.

Therefore, digital systems must detect a zero divisor and handle the condition appropriately.

---

* **Signed Binary Division**

Binary division can also be performed on signed numbers.

Signed division generally requires:

  - Sign handling.
  - Magnitude calculation.
  - Division of magnitudes.
  - Correct sign assignment to the quotient.
  - Proper handling of the remainder.

For signed binary numbers, **Two's Complement** representation is commonly used.

---

* **Quotient and Remainder Relationship**

The fundamental relationship is:

**Dividend = Divisor × Quotient + Remainder**

Example:

**11 = 2 × 5 + 1**

In binary:

**1011₂ = 10₂ × 101₂ + 1₂**

This relationship can be used to verify a binary division result.

---

* **Applications**

  *Binary Division is used in:*

  - Arithmetic Logic Units.
  - Microprocessors.
  - Microcontrollers.
  - Digital Signal Processing.
  - Digital Calculators.
  - Computer Arithmetic.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.
  - Address and index calculations.
  - Mathematical processing units.

---

* **Advantages**
  - Uses simple binary operations.
  - Can be implemented using shifting and subtraction.
  - Division by powers of two can be performed efficiently using right shifts.
  - Suitable for hardware implementation.
  - Can be optimized using dedicated division algorithms.

---

* **Limitations**
  - Binary division is generally more complex than binary addition and subtraction.
  - Hardware dividers require more resources.
  - Division can require multiple clock cycles in sequential implementations.
  - Division has higher latency than simple arithmetic operations.
  - Signed division requires additional sign-handling logic.
  - Division by zero must be detected and handled.

---

* **Real-World Example**

A processor may need to divide a value stored in one register by another value.

For example:

**Dividend = 110010₂**

**Divisor = 10₂**

Since:

**110010₂ = 50₁₀**

and:

**10₂ = 2₁₀**

Therefore:

**50 ÷ 2 = 25**

And:

**25₁₀ = 11001₂**

Therefore:

**110010₂ ÷ 10₂ = 11001₂**

This type of operation can be performed by the processor's arithmetic unit or a dedicated hardware divider.

---

* **Key Points**
  - Binary Division uses only **0 and 1**.
  - The four main terms are **Dividend, Divisor, Quotient, and Remainder**.
  - Division starts from the **MSB** of the dividend.
  - Comparison and subtraction are fundamental steps.
  - The final remaining value is the **Remainder**.
  - Division by zero is undefined.
  - Division by 2 can be performed using a right shift.
  - Division by powers of 2 can be implemented using right shifts.
  - Restoring and Non-Restoring are common hardware division algorithms.
  - Hardware dividers use registers, subtractors, shifters, and control logic.
  - Binary division is used in processors, ALUs, FPGA, ASIC, and VLSI systems.

---

* **Interview Questions**

**1. What is Binary Division?**

**Answer:**

Binary Division is the process of dividing one binary number by another binary number to obtain a Quotient and, when applicable, a Remainder.

---

**2. What are the four main terms in binary division?**

**Answer:**

The four main terms are:

**Dividend**

**Divisor**

**Quotient**

**Remainder**

---

**3. What is the basic relationship between dividend, divisor, quotient, and remainder?**

**Answer:**

The relationship is:

**Dividend = Divisor × Quotient + Remainder**

---

**4. From which side does binary division start?**

**Answer:**

Binary division starts from the **MSB** of the dividend.

---

**5. What happens when the partial dividend is greater than or equal to the divisor?**

**Answer:**

The divisor is subtracted from the partial dividend and a **1** is placed in the corresponding quotient position.

---

**6. What happens when the partial dividend is smaller than the divisor?**

**Answer:**

No subtraction is performed and a **0** is placed in the corresponding quotient position. The next dividend bit is then brought down.

---

**7. What happens when a binary number is divided by 2?**

**Answer:**

For an unsigned binary number, dividing by 2 is equivalent to shifting the number right by one bit.

Example:

**10110₂ ÷ 2 = 1011₂**

---

**8. What is the Restoring Division Algorithm?**

**Answer:**

Restoring Division is a hardware division algorithm in which the divisor is subtracted from the partial remainder. If the result becomes negative, the previous remainder is restored and the quotient bit is set to 0.

---

**9. What is Non-Restoring Division?**

**Answer:**

Non-Restoring Division is a division algorithm that avoids immediately restoring a negative partial remainder and instead uses the sign of the partial remainder to determine the next operation.

---

**10. Why is binary division more complex than binary addition?**

**Answer:**

Binary division requires repeated comparison, shifting, subtraction, and quotient generation, making it more hardware-intensive and time-consuming than simple binary addition.

---

**11. Can binary division be performed using shifting?**

**Answer:**

Yes. Division by powers of two can be efficiently performed using right-shift operations.

---

**12. What happens when the divisor is zero?**

**Answer:**

Division by zero is undefined. Digital systems must detect a zero divisor and handle it using appropriate control logic.

---

**13. What is the difference between quotient and remainder?**

**Answer:**

The **Quotient** is the main result of the division, while the **Remainder** is the value left after the divisor has been applied as many times as possible.

---

**14. Where is Binary Division used?**

**Answer:**

Binary division is used in ALUs, processors, microcontrollers, DSP systems, FPGA, ASIC, RTL, and VLSI-based digital systems.

---

* **Quick Revision**
  - Main Topic → **Binary Arithmetic**
  - Subtopic → **Binary Division**
  - Number System → **Binary**
  - Base → **2**
  - Digits → **0, 1**
  - Main Inputs → **Dividend and Divisor**
  - Main Outputs → **Quotient and Remainder**
  - Starting Position → **MSB**
  - Basic Operations → **Compare, Shift, Subtract**
  - Division by 2 → **Right Shift by 1**
  - Division by 4 → **Right Shift by 2**
  - Common Algorithms → **Restoring and Non-Restoring**
  - Invalid Operation → **Division by Zero**
  - Main Application → **ALU, Processor, FPGA, ASIC, VLSI**

---

* **Summary**

**Binary Division** is a fundamental operation under **Binary Arithmetic** used to divide one binary number by another and produce a Quotient and Remainder. The operation uses comparison, shifting, and subtraction to generate the quotient. For hardware implementation, algorithms such as **Restoring Division** and **Non-Restoring Division** are commonly used. Division by powers of two can be performed efficiently using right-shift operations.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
