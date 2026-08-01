# **3-Bit Comparator**

* **What Problem Does It Solve?**
  - A 3-Bit Comparator is a digital combinational circuit.
  - It compares two 3-bit binary numbers.
  - It determines whether one number is greater than, less than, or equal to the other.
  - It provides comparison results through three output signals.

---

* **Why is it used?**

  *A 3-Bit Comparator is used because:*

  - It compares two binary numbers.
  - It helps in making logical decisions.
  - It is used in arithmetic and control circuits.
  - It is the basic building block for larger comparators.
  - It improves the performance of digital systems.

---

* **Where is it used?**

  *A 3-Bit Comparator is widely used in:*

  - CPUs (Processors).
  - ALU (Arithmetic Logic Unit).
  - Digital calculators.
  - Digital control systems.
  - Memory address comparison.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Data comparison circuits.

---

* **Circuit Diagram:**

![3_BIT_COMPARATOR](Comparator-Images/3-bit-comparator.png)

---

* **Function of Inputs and Outputs**

  - A2 = Most Significant Bit (MSB) of first number.
  - A1 = Middle bit of first number.
  - A0 = Least Significant Bit (LSB) of first number.
  - B2 = Most Significant Bit (MSB) of second number.
  - B1 = Middle bit of second number.
  - B0 = Least Significant Bit (LSB) of second number.
  - A>B = HIGH when A is greater than B.
  - A=B = HIGH when A is equal to B.
  - A<B = HIGH when A is less than B.

---

* **Truth Table**

> A complete truth table contains **64 (2⁶)** input combinations, so it is usually not included in datasheets or textbooks.

### Sample Truth Table

| A2A1A0 | B2B1B0 | A>B | A=B | A<B |
|:------:|:------:|:---:|:---:|:---:|
| 000 | 000 | 0 | 1 | 0 |
| 001 | 010 | 0 | 0 | 1 |
| 010 | 001 | 1 | 0 | 0 |
| 011 | 011 | 0 | 1 | 0 |
| 100 | 011 | 1 | 0 | 0 |
| 101 | 110 | 0 | 0 | 1 |
| 110 | 101 | 1 | 0 | 0 |
| 111 | 111 | 0 | 1 | 0 |

---

* **Boolean Expressions**

- **A>B = A2B2̅ + (A2 ⊙ B2)A1B1̅ + (A2 ⊙ B2)(A1 ⊙ B1)A0B0̅**

- **A=B = (A2 ⊙ B2)(A1 ⊙ B1)(A0 ⊙ B0)**

- **A<B = A2̅B2 + (A2 ⊙ B2)A1̅B1 + (A2 ⊙ B2)(A1 ⊙ B1)A0̅B0**

> **Note:** **⊙** represents the **XNOR (Equality)** operation.

---

