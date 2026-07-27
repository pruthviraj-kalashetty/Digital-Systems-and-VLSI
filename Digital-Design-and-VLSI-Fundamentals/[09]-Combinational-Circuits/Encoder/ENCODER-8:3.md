# **8 : 3 Encoder**

* **What Problem Does It Solve?**
  - An 8 : 3 Encoder is a digital combinational circuit.
  - It converts one of eight active input lines into a 3-bit binary output.
  - It reduces the number of output lines from eight to three.
  - Only one input should be HIGH (1) at a time.

---

* **Why is it used?**

  *An 8 : 3 Encoder is used because:*

  - It converts multiple input signals into binary code.
  - It reduces the number of output lines.
  - It simplifies digital circuit design.
  - It improves hardware efficiency.
  - It provides fast binary encoding.

---

* **Where is it used?**

  *An 8 : 3 Encoder is widely used in:*

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

![8X3_ENCODER](ENCODER-Images/8x3-encoder.png)

---

* **Function of Inputs and Outputs**

  - I0 = First input.
  - I1 = Second input.
  - I2 = Third input.
  - I3 = Fourth input.
  - I4 = Fifth input.
  - I5 = Sixth input.
  - I6 = Seventh input.
  - I7 = Eighth input.
  - Y2 = Most Significant Bit (MSB).
  - Y1 = Middle output bit.
  - Y0 = Least Significant Bit (LSB).

---

* **Truth Table**

| I7 | I6 | I5 | I4 | I3 | I2 | I1 | I0 | Y2 | Y1 | Y0 |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 |
| 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 1 |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 |

> **Note:** Only one input should be HIGH (1) at a time.

---

* **Boolean Expressions**

- **Y2 = I4 + I5 + I6 + I7**
- **Y1 = I2 + I3 + I6 + I7**
- **Y0 = I1 + I3 + I5 + I7**

---

* **Waveform / Timing Diagram:**

  ![8X3_ENCODER](ENCODER-Images/8x3_encoder.png)
