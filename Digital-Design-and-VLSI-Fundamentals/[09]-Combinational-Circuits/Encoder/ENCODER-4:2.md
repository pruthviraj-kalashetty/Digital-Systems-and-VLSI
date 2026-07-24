# **4 : 2 Encoder**

* **What Problem Does It Solve?**
  - A 4 : 2 Encoder is a digital combinational circuit.
  - It converts one of four active input lines into a 2-bit binary output.
  - It reduces the number of output lines from four to two.
  - Only one input should be HIGH (1) at a time.

---

* **Why is it used?**

  *A 4 : 2 Encoder is used because:*

  - It converts multiple input signals into binary code.
  - It reduces the number of output lines.
  - It simplifies digital circuit design.
  - It improves hardware efficiency.
  - It provides fast binary encoding.

---

* **Where is it used?**

  *A 4 : 2 Encoder is widely used in:*

  - Digital communication systems.
  - Keyboard encoding circuits.
  - Data transmission systems.
  - CPUs (Processors).
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Control systems.
  - Binary encoding applications.

---

* **Circuit Diagram:**

![4X2_ENCODER](Image/4x2-encoder.png)

---

* **Function of Inputs and Outputs**

  - I0 = First input.
  - I1 = Second input.
  - I2 = Third input.
  - I3 = Fourth input.
  - Y1 = Most Significant Bit (MSB) output.
  - Y0 = Least Significant Bit (LSB) output.

---

* **Truth Table**

| I3 | I2 | I1 | I0 | Y1 | Y0 |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 1 |
| 0 | 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 | 1 |

> **Note:** Only one input should be HIGH (1) at a time.

---

* **Boolean Expressions**

- **Y1 = I2 + I3**
- **Y0 = I1 + I3**

---

* **Easy Way to Remember**

- A **4 : 2 Encoder** has **4 inputs** and **2 outputs**.
- **I0 → 00**
- **I1 → 01**
- **I2 → 10**
- **I3 → 11**
- Only one input can be HIGH at a time.

---

* **One-Line Definition (Interview)**

> A 4 : 2 Encoder is a combinational logic circuit that converts one of four active input lines into a 2-bit binary output.
