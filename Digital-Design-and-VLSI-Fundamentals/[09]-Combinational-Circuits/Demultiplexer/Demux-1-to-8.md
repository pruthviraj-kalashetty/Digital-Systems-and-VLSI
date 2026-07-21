# **1 : 8 Demultiplexer (DEMUX)**

* **What Problem Does It Solve?**
  - A 1 : 8 Demultiplexer (DEMUX) is a digital combinational circuit.
  - It takes one input signal and sends it to one of eight outputs.
  - The output is selected using three select lines (S2, S1, and S0).
  - Only one output is active at a time.

---

* **Why is it used?**

  *A 1 : 8 Demultiplexer is used because:*

  - It routes one input signal to one of multiple outputs.
  - It controls the flow of data in digital circuits.
  - It reduces wiring complexity.
  - It simplifies circuit design.
  - It improves hardware efficiency.

---

* **Where is it used?**

  *A 1 : 8 Demultiplexer is widely used in:*

  - Data distribution circuits.
  - Communication systems.
  - Memory address decoding.
  - Digital control systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Embedded systems.
  - Data routing applications.

---

* **Circuit Diagram:**

![1X8_DEMUX](Image/1x8-demultiplexer.png)

---

* **Function of Inputs and Outputs**

  - D = Data input.
  - S2, S1, S0 = Select lines.
  - Y0 = First output.
  - Y1 = Second output.
  - Y2 = Third output.
  - Y3 = Fourth output.
  - Y4 = Fifth output.
  - Y5 = Sixth output.
  - Y6 = Seventh output.
  - Y7 = Eighth output.

---

* **Truth Table**

| S2 | S1 | S0 | D | Y0 | Y1 | Y2 | Y3 | Y4 | Y5 | Y6 | Y7 |
|:--:|:--:|:--:|:-:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |

---

* **Boolean Expressions**

- **Y0 = D · S2̅ · S1̅ · S0̅**
- **Y1 = D · S2̅ · S1̅ · S0**
- **Y2 = D · S2̅ · S1 · S0̅**
- **Y3 = D · S2̅ · S1 · S0**
- **Y4 = D · S2 · S1̅ · S0̅**
- **Y5 = D · S2 · S1̅ · S0**
- **Y6 = D · S2 · S1 · S0̅**
- **Y7 = D · S2 · S1 · S0**

---

* **Easy Way to Remember**

- A **1 : 8 DEMUX** has **1 input**, **8 outputs**, and **3 select lines**.
- **S2S1S0 = 000 → Y0**
- **S2S1S0 = 001 → Y1**
- **S2S1S0 = 010 → Y2**
- **S2S1S0 = 011 → Y3**
- **S2S1S0 = 100 → Y4**
- **S2S1S0 = 101 → Y5**
- **S2S1S0 = 110 → Y6**
- **S2S1S0 = 111 → Y7**
- Only **one output** receives the input at a time.

---

* **One-Line Definition (Interview)**

> A 1 : 8 Demultiplexer (DEMUX) is a combinational logic circuit that routes one input signal to one of eight outputs based on three select lines.
