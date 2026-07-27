# **2 : 4 Decoder**

* **What Problem Does It Solve?**
  - A 2 : 4 Decoder is a digital combinational circuit.
  - It converts a 2-bit binary input into one of four output lines.
  - Only one output becomes HIGH (1) for each input combination.
  - It is used to select one output from four possible outputs.

---

* **Why is it used?**

  *A 2 : 4 Decoder is used because:*

  - It converts binary input into individual output lines.
  - It selects one output from multiple outputs.
  - It simplifies digital circuit design.
  - It is used for address decoding in memory systems.
  - It improves hardware efficiency.

---

* **Where is it used?**

  *A 2 : 4 Decoder is widely used in:*

  - Memory address decoding.
  - CPUs (Processors).
  - ALU (Arithmetic Logic Unit).
  - Data routing circuits.
  - Digital control systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Embedded systems.

---

* **Circuit Diagram:**

![2X4_DECODER](DECODER-Images/2x4-decoder.png)

---

* **Function of Inputs and Outputs**

  - A1 = Most Significant Bit (MSB) input.
  - A0 = Least Significant Bit (LSB) input.
  - Y0 = First output.
  - Y1 = Second output.
  - Y2 = Third output.
  - Y3 = Fourth output.

---

* **Truth Table**

| A1 | A0 | Y0 | Y1 | Y2 | Y3 |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 | 0 | 1 |

---

* **Boolean Expressions**

- **Y0 = A1̅ · A0̅**
- **Y1 = A1̅ · A0**
- **Y2 = A1 · A0̅**
- **Y3 = A1 · A0**

---

![MUX-8-to-1 WAVEFORM](MUX-Images/MUX_8_to_1_waveform.png)
