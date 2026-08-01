# **1-Bit Comparator**

* **What Problem Does It Solve?**
  - A 1-Bit Comparator is a digital combinational circuit.
  - It compares two 1-bit binary numbers.
  - It determines whether one input is greater than, less than, or equal to the other.
  - It provides comparison results through three output signals.

---

* **Why is it used?**

  *A 1-Bit Comparator is used because:*

  - It compares two binary values.
  - It helps in making logical decisions.
  - It is used in arithmetic and control circuits.
  - It is the basic building block for multi-bit comparators.
  - It improves the performance of digital systems.

---

* **Where is it used?**

  *A 1-Bit Comparator is widely used in:*

  - CPUs (Processors).
  - ALU (Arithmetic Logic Unit).
  - Digital calculators.
  - Digital control systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Memory address comparison.
  - Data comparison circuits.

---

* **Circuit Diagram:**

![1_BIT_COMPARATOR](Comparator-Images/1-bit-comparator.png)

---

* **Function of Inputs and Outputs**

  - A = First input bit.
  - B = Second input bit.
  - A>B = HIGH when A is greater than B.
  - A=B = HIGH when A is equal to B.
  - A<B = HIGH when A is less than B.

---

* **Truth Table**

| A | B | A>B | A=B | A<B |
|:-:|:-:|:---:|:---:|:---:|
| 0 | 0 |  0  |  1  |  0  |
| 0 | 1 |  0  |  0  |  1  |
| 1 | 0 |  1  |  0  |  0  |
| 1 | 1 |  0  |  1  |  0  |

---

* **Boolean Expressions**

- **A>B = A · B̅**
- **A=B = A̅ · B̅ + A · B**
- **A<B = A̅ · B**

---
