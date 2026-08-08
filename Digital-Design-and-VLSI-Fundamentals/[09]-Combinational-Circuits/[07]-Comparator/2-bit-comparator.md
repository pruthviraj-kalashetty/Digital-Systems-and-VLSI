# **2-Bit Comparator**

* **Overview**

A **2-Bit Comparator** is a combinational logic circuit that compares two 2-bit binary numbers and determines whether the first number is greater than, less than, or equal to the second number.

---

* **Definition**

A **2-Bit Comparator** is a digital combinational circuit that compares two 2-bit binary numbers and produces three outputs indicating **A > B**, **A < B**, or **A = B**.

---

* **Purpose**
  - To compare two 2-bit binary numbers.
  - To determine the magnitude relationship between two binary values.
  - To generate greater-than, less-than, and equal outputs.
  - To provide a building block for larger multi-bit comparators.

---

* **Importance**
  - Helps understand multi-bit binary comparison.
  - Forms the foundation for larger magnitude comparators.
  - Used in digital decision-making circuits.
  - Important for processor, control, and VLSI circuit design.

---

* **Working Principle**
  - A **2-Bit Comparator** compares two 2-bit numbers:
    - **A = A1A0**
    - **B = B1B0**
  - The Most Significant Bits (**A1** and **B1**) are compared first.
  - If A1 and B1 are different, their values determine the result.
  - If A1 and B1 are equal, the Least Significant Bits (**A0** and **B0**) are compared.
  - The circuit produces three outputs:
    - **G** → A > B
    - **L** → A < B
    - **E** → A = B

---

* **Circuit Description**
  - A 2-Bit Comparator can be implemented using:
    - XNOR Gates.
    - AND Gates.
    - OR Gates.
    - NOT Gates.
  - The equality of the MSBs is checked first.
  - The LSB comparison is considered only when the MSBs are equal.
  - The comparison of the MSB has higher priority than the LSB.

---

* **Circuit Diagram:**

![2-Bit Comparator](Comparator-Images/2-bit-comparator.png)

---

* **Truth Table:**

| A1 | A0 | B1 | B0 | A > B | A < B | A = B |
|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 | 0 | 1 |
| 0 | 0 | 0 | 1 | 0 | 1 | 0 |
| 0 | 0 | 1 | 0 | 0 | 1 | 0 |
| 0 | 0 | 1 | 1 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 | 1 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 | 1 |
| 0 | 1 | 1 | 0 | 0 | 1 | 0 |
| 0 | 1 | 1 | 1 | 0 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 | 1 |
| 1 | 0 | 1 | 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 0 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 1 |

---

* **Boolean Expression**

**G = A1 · B1̅ + E1 · A0 · B0̅**

**L = A1̅ · B1 + E1 · A0̅ · B0**

**E = E1 · E0**

Where:

**E1 = A1 XNOR B1**

**E0 = A0 XNOR B0**

Therefore:

**E = (A1 XNOR B1) · (A0 XNOR B0)**

---

* **Input and Output Description**
  - Inputs:-
    - A1, A0 [2 Inputs for Number A]
    - B1, B0 [2 Inputs for Number B]
  - Outputs:-
    - G, L, E [3 Outputs]

  - **A1** and **B1** are the Most Significant Bits.
  - **A0** and **B0** are the Least Significant Bits.
  - **G = 1** when A > B.
  - **L = 1** when A < B.
  - **E = 1** when A = B.

---

* **Working Example**
  - Consider:

    - A = 10
    - B = 01

  Decimal values:

    - A = 2
    - B = 1

Output:

- **G = 1**
- **L = 0**
- **E = 0**

Therefore:

**A > B**

Another Example:

- A = 01
- B = 01

Output:

- **G = 0**
- **L = 0**
- **E = 1**

Therefore:

**A = B**

---

* **Applications**

  *The 2-Bit Comparator is used in:*

  - Digital Comparators.
  - Arithmetic Logic Units.
  - Processor Control Units.
  - Address Comparison.
  - Data Comparison.
  - Digital Control Systems.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Simple combinational implementation.
  - Can compare two 2-bit binary numbers.
  - Provides three comparison results.
  - Forms the basis for larger comparators.
  - Easy to extend to multi-bit comparison.

---

* **Limitations**
  - Can compare only two 2-bit numbers.
  - Larger numbers require additional comparison logic.
  - Circuit complexity increases as the number of bits increases.

---

* **Real-World Example**
  - In a digital control system, a 2-bit comparator can compare a sensor or control value with a 2-bit reference value and generate a greater-than, less-than, or equal signal for further control operations.

---

* **Key Points**
  - A **2-Bit Comparator** compares two 2-bit binary numbers.
  - Inputs → **A1A0** and **B1B0**.
  - Outputs → **A > B, A < B, A = B**.
  - The **MSB is compared first**.
  - The LSB is compared only when the MSBs are equal.
  - XNOR gates are commonly used for equality detection.
  - It can be extended to construct larger multi-bit comparators.

---

* **Interview Questions**

**1. What is a 2-Bit Comparator?**

**Answer:**

A 2-Bit Comparator is a combinational logic circuit that compares two 2-bit binary numbers and determines whether one number is greater than, less than, or equal to the other.

---

**2. How many inputs does a 2-Bit Comparator have?**

**Answer:**

It has **four input signals**, two for each binary number:

- A1, A0
- B1, B0

---

**3. How many outputs does a 2-Bit Comparator have?**

**Answer:**

It has **three outputs**:

- A > B
- A < B
- A = B

---

**4. Which bit is compared first in a 2-Bit Comparator?**

**Answer:**

The **Most Significant Bit (MSB)** is compared first because it has a higher binary weight.

---

**5. What happens when the MSBs are equal?**

**Answer:**

When the MSBs are equal, the **Least Significant Bits (LSBs)** are compared to determine whether A is greater than, less than, or equal to B.

---

**6. What is the equality expression for a 2-Bit Comparator?**

**Answer:**

**E = (A1 XNOR B1) · (A0 XNOR B0)**

---

**7. When is A > B?**

**Answer:**

A is greater than B when:

**A1 > B1**

or when the MSBs are equal and:

**A0 > B0**

---

**8. When is A < B?**

**Answer:**

A is less than B when:

**A1 < B1**

or when the MSBs are equal and:

**A0 < B0**

---

**9. Why are XNOR gates used in a comparator?**

**Answer:**

XNOR gates are used to determine whether two corresponding bits are equal. This makes them useful for equality detection in comparators.

---

**10. Can a 2-Bit Comparator be used to build a larger comparator?**

**Answer:**

Yes. Comparator logic can be extended and cascaded to compare larger binary numbers.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Numbers Compared → 2-Bit vs 2-Bit
  - Inputs → 4
  - Outputs → 3
  - Comparison → Greater, Less, Equal
  - First Comparison → MSB
  - Equality → XNOR
  - Main Function → Binary Magnitude Comparison
  - Building Block → Multi-Bit Comparator

---

* **Summary**

A **2-Bit Comparator** is a combinational logic circuit that compares two 2-bit binary numbers and generates three outputs indicating whether A is greater than B, less than B, or equal to B. The MSBs are compared first, and the LSBs are considered only when the MSBs are equal. This concept forms the foundation for larger multi-bit comparators used in digital systems, processors, FPGA, ASIC, RTL, and VLSI designs.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Jan M. Rabaey – *Digital Integrated Circuits: A Design Perspective*.
  - Neil H. E. Weste & David Harris – *CMOS VLSI Design*.
  - Neso Academy – Digital Electronics.
