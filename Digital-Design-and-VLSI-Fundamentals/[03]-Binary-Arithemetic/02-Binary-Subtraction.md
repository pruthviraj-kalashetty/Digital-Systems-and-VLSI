# **Binary Subtraction**

* **Overview**

**Binary Subtraction** is an arithmetic operation performed on binary numbers using only the digits **0 and 1**. It is one of the fundamental operations under **Binary Arithmetic** and is widely used in digital systems, ALUs, processors, FPGA, ASIC, and VLSI designs.

---

* **Definition**

**Binary Subtraction** is the process of subtracting one binary number from another using binary subtraction rules and borrow operations when required.

---

* **Purpose**
  - To perform subtraction of binary numbers.
  - To calculate differences in digital systems.
  - To form the basis of subtractor circuits.
  - To support arithmetic operations in ALUs and processors.
  - To implement arithmetic operations in FPGA, ASIC, and VLSI systems.

---

* **Importance**
  - It is a fundamental operation under **Binary Arithmetic**.
  - It forms the basis of Half Subtractors and Full Subtractors.
  - It is used in ALUs and arithmetic circuits.
  - It is important for processor and digital-system design.
  - It is widely used in RTL, FPGA, ASIC, and VLSI design.

---

* **Binary Subtraction Rules**

Binary subtraction uses four basic rules:

| A | B | Difference | Borrow |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |

The most important rule is:

**0 − 1 = 1 with Borrow = 1**

This means that when **0 − 1** occurs, we borrow **1** from the next higher bit.

---

* **Working Principle**

Binary subtraction is normally performed from the **LSB to the MSB**.

The basic process is:

**1. Start from the rightmost bit, called the LSB.**

**2. Subtract the corresponding bits of the two binary numbers.**

**3. Consider the Borrow from the previous bit, if present.**

**4. Write the Difference bit.**

**5. Generate a Borrow when required.**

**6. Pass the Borrow to the next higher bit position.**

**7. Continue until all bits have been processed.**

---

* **Circuit Description**

Binary subtraction can be implemented using digital arithmetic circuits called **Subtractors**.

The main types are:

  - **Half Subtractor**
    - Subtracts two binary bits.
    - Produces Difference and Borrow.

  - **Full Subtractor**
    - Subtracts three binary inputs.
    - Inputs are A, B, and Borrow-in.
    - Produces Difference and Borrow-out.

  - **Multi-Bit Subtractor**
    - Uses multiple Full Subtractors.
    - Performs subtraction of multi-bit binary numbers.

  - **Adder-Based Subtractor**
    - Uses binary addition and two's complement.
    - Commonly used in ALUs and processors.

---

* **Boolean Expression**

For a Half Subtractor:

**Difference = A ⊕ B**

**Borrow = A'.B**

For a Full Subtractor:

**Difference = A ⊕ B ⊕ Bᵢₙ**

**Bₒᵤₜ = A'.B + A'.Bᵢₙ + B.Bᵢₙ**

---

* **Input and Output Description**

  - Inputs:-
    - Minuend.
    - Subtrahend.
    - Borrow-in, when required.

  - Outputs:-
    - Difference.
    - Borrow-out.

For an N-bit subtraction:

**N-bit − N-bit → N-bit Difference + possible Borrow**

---

* **Working Example**

Consider:

**1011₂ − 0011₂**

Perform the subtraction from right to left:

      1011
    - 0011
    ------
      1000

Therefore:

**1011₂ − 0011₂ = 1000₂**

In decimal:

**11 − 3 = 8**

Therefore:

**1000₂ = 8₁₀**

---

* **Working Example with Borrow**

Consider:

**1000₂ − 0001₂**

      1000
    - 0001
    ------
      0111

The subtraction requires borrowing through the intermediate zero bits.

Therefore:

**1000₂ − 0001₂ = 0111₂**

In decimal:

**8 − 1 = 7**

Therefore:

**0111₂ = 7₁₀**

---

* **Borrow Operation**

A **Borrow** occurs when the bit being subtracted is larger than the bit from which it is being subtracted.

For example:

**0 − 1**

Since binary has only **0 and 1**, we cannot directly perform:

**0 − 1**

Therefore, we borrow **1** from the next higher bit.

The borrowed binary 1 represents **2** at the current bit position.

Therefore:

**10₂ − 1₂ = 1₂**

So:

**0 − 1 = 1 with Borrow = 1**

---

* **Borrow Propagation**

**Borrow Propagation** occurs when a borrow generated at one bit position affects the subtraction at the next higher bit position.

Example:

**1000₂ − 0001₂**

The borrow must pass through the intermediate zero bits.

This is similar to carry propagation in binary addition.

---

* **Binary Subtraction Using Half Subtractor**

A Half Subtractor performs subtraction of two single binary bits.

Inputs:

**A, B**

Outputs:

**Difference, Borrow**

Equations:

**Difference = A ⊕ B**

**Borrow = A'.B**

---

* **Binary Subtraction Using Full Subtractor**

A Full Subtractor subtracts three binary inputs:

**A, B, Bᵢₙ**

Outputs:

**Difference, Bₒᵤₜ**

Equations:

**Difference = A ⊕ B ⊕ Bᵢₙ**

**Bₒᵤₜ = A'.B + A'.Bᵢₙ + B.Bᵢₙ**

Full Subtractors can be connected together to perform multi-bit subtraction.

---

* **Multi-Bit Binary Subtraction**

For multi-bit subtraction, multiple Full Subtractors can be connected together.

Example:

**4-bit − 4-bit**

      A₃ A₂ A₁ A₀
    - B₃ B₂ B₁ B₀
    --------------
      D₃ D₂ D₁ D₀

The Borrow-out from one stage becomes the Borrow-in of the next stage.

---

* **Subtraction Using Two's Complement**

Modern digital systems commonly perform subtraction using **Two's Complement**.

Instead of directly subtracting:

**A − B**

The system performs:

**A + Two's Complement of B**

The two's complement of B is obtained by:

**1. Invert all bits of B.**

**2. Add 1 to the result.**

Therefore:

**A − B = A + (~B + 1)**

This allows the same adder hardware to perform both addition and subtraction.

---

* **Working Example Using Two's Complement**

Consider:

**7 − 3**

Using 4-bit binary:

**7 = 0111**

**3 = 0011**

Step 1: Find the one's complement of 3:

**0011 → 1100**

Step 2: Add 1:

**1100 + 0001 = 1101**

Therefore:

**Two's Complement of 0011 = 1101**

Now add:

      0111
    + 1101
    ------
     10100

Discard the final carry:

**0100**

Therefore:

**0111₂ − 0011₂ = 0100₂**

In decimal:

**7 − 3 = 4**

---

* **Adder-Based Subtractor**

A subtractor can be implemented using an adder by using two's complement.

The operation is:

**A − B = A + (~B + 1)**

An XOR gate can be used to complement B when subtraction is selected.

This is commonly used in an **ALU**.

The same hardware can therefore perform:

**Addition**

and

**Subtraction**

depending on the control signal.

---

* **Borrow vs Carry**

| Feature | Carry | Borrow |
|---|---|---|
| Used in | Addition | Subtraction |
| Generated when | Sum exceeds available bit range | Minuend bit is smaller than required |
| Main circuit | Adder | Subtractor |
| Propagation | Carry propagation | Borrow propagation |
| Example | 1 + 1 = 10 | 0 − 1 requires borrow |

---

* **Applications**

  *Binary Subtraction is used in:*

  - Arithmetic Logic Units.
  - Microprocessors.
  - Microcontrollers.
  - Digital calculators.
  - Digital signal processors.
  - Address calculation.
  - Counters.
  - Comparators.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.
  - Digital arithmetic circuits.

---

* **Advantages**
  - Simple binary subtraction rules.
  - Easy to implement using logic gates.
  - Can be implemented using subtractors.
  - Can also be implemented using adders and two's complement.
  - Supports efficient arithmetic operations in digital systems.
  - Suitable for ALU and processor design.

---

* **Limitations**
  - Borrow propagation can increase circuit delay.
  - Large subtractors require more hardware.
  - Direct subtractor architectures may require additional logic.
  - Multi-bit subtraction can become slower when borrow propagation occurs across many bits.
  - High-speed subtractors may require additional hardware resources.

---

* **Real-World Example**

A processor may need to subtract two values stored in registers.

For example:

**Register A = 11010₂**

**Register B = 00101₂**

The ALU performs:

**11010₂ − 00101₂ = 10101₂**

In decimal:

**26 − 5 = 21**

Therefore:

**10101₂ = 21₁₀**

---

* **Key Points**
  - Binary subtraction uses only **0 and 1**.
  - Subtraction starts from the **LSB**.
  - **0 − 1** requires a Borrow.
  - Borrow is passed to the next higher bit.
  - Half Subtractors subtract two bits.
  - Full Subtractors subtract three inputs.
  - Difference is generated using XOR logic.
  - Borrow is generated using AND/OR logic.
  - Two's complement is commonly used for subtraction in digital systems.
  - An adder can perform subtraction using two's complement.
  - Borrow propagation affects subtraction speed.
  - Binary subtraction is fundamental to ALUs and processors.

---

* **Interview Questions**

**1. What is Binary Subtraction?**

**Answer:**

Binary Subtraction is the process of subtracting one binary number from another using binary subtraction rules and Borrow operations.

---

**2. What are the basic rules of binary subtraction?**

**Answer:**

The four basic rules are:

**0 − 0 = 0**

**0 − 1 = 1 with Borrow = 1**

**1 − 0 = 1**

**1 − 1 = 0**

---

**3. What happens when 0 − 1 occurs?**

**Answer:**

A Borrow is taken from the next higher bit. The current bit becomes:

**10₂ − 1₂ = 1₂**

Therefore:

**0 − 1 = 1 with Borrow = 1**

---

**4. What is a Half Subtractor?**

**Answer:**

A Half Subtractor is a combinational circuit that subtracts two binary bits and produces Difference and Borrow outputs.

---

**5. What is a Full Subtractor?**

**Answer:**

A Full Subtractor is a combinational circuit that subtracts three binary inputs: A, B, and Borrow-in. It produces Difference and Borrow-out.

---

**6. What is the Difference equation of a Half Subtractor?**

**Answer:**

**Difference = A ⊕ B**

---

**7. What is the Borrow equation of a Half Subtractor?**

**Answer:**

**Borrow = A'.B**

---

**8. What is Borrow Propagation?**

**Answer:**

Borrow Propagation is the process in which a Borrow generated at one bit position affects the subtraction at the next higher bit position.

---

**9. Why is Two's Complement used for subtraction?**

**Answer:**

Two's Complement allows subtraction to be performed using the same adder hardware used for addition, reducing hardware complexity in digital systems.

---

**10. How is the Two's Complement of a binary number obtained?**

**Answer:**

The Two's Complement is obtained by:

**1. Inverting all bits.**

**2. Adding 1 to the result.**

---

**11. How can an adder perform subtraction?**

**Answer:**

An adder can perform subtraction using Two's Complement:

**A − B = A + (~B + 1)**

---

**12. What is the difference between Carry and Borrow?**

**Answer:**

Carry is generated during addition when the result exceeds the available bit range, while Borrow is generated during subtraction when the minuend bit is smaller than the required subtrahend bit.

---

**13. Where is Binary Subtraction used?**

**Answer:**

Binary subtraction is used in ALUs, processors, microcontrollers, calculators, digital arithmetic circuits, FPGA, ASIC, and VLSI systems.

---

**14. Why is Borrow Propagation important?**

**Answer:**

Borrow Propagation affects the speed of multi-bit subtraction because each subtraction stage may need to wait for the Borrow from the previous stage.

---

* **Quick Revision**
  - Main Topic → **Binary Arithmetic**
  - Subtopic → **Binary Subtraction**
  - Number System → **Binary**
  - Base → **2**
  - Digits → **0, 1**
  - Basic Rule → **0 − 1 = 1 with Borrow**
  - Starting Position → **LSB**
  - Basic Circuit → **Subtractor**
  - Half Subtractor → **2 Inputs**
  - Full Subtractor → **3 Inputs**
  - Difference → **XOR**
  - Borrow → **AND / OR**
  - Multi-Bit Subtraction → **Multiple Full Subtractors**
  - Common Method → **Two's Complement**
  - Main Delay → **Borrow Propagation**
  - Main Application → **ALU and Processor**

---

* **Summary**

**Binary Subtraction** is a fundamental operation under **Binary Arithmetic** in which one binary number is subtracted from another using the digits 0 and 1. The operation starts from the LSB and proceeds toward the MSB while handling Borrow between bit positions. In practical digital systems, subtraction is commonly implemented using **Two's Complement**, allowing the same adder hardware to perform both addition and subtraction.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
