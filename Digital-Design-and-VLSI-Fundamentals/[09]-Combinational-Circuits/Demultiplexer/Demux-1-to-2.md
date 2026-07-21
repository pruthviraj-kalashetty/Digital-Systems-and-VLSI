# **1 : 2 Demultiplexer (DEMUX)**

* **What Problem Does It Solve?**
  - A 1 : 2 Demultiplexer (DEMUX) is a digital combinational circuit.
  - It takes one input signal and sends it to one of two outputs.
  - The output is selected using one select line (S).
  - Only one output is active at a time.

---

* **Why is it used?**

  *A 1 : 2 Demultiplexer is used because:*

  - It routes one input signal to one of multiple outputs.
  - It controls the flow of data in digital circuits.
  - It reduces wiring complexity.
  - It simplifies circuit design.
  - It improves hardware efficiency.

---

* **Where is it used?**

  *A 1 : 2 Demultiplexer is widely used in:*

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

![1X2_DEMUX](Image/1x2-demultiplexer.png)

---

* **Function of Inputs and Outputs**

  - D = Data input.
  - S = Select line.
  - Y0 = First output.
  - Y1 = Second output.

---

* **Truth Table**

| S | D | Y0 | Y1 |
|:-:|:-:|:--:|:--:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 1 | 0 | 1 |

---

* **Boolean Expressions**

- **Y0 = D · S̅**
- **Y1 = D · S**

---

* **Easy Way to Remember**

- A **1 : 2 DEMUX** has **1 input**, **2 outputs**, and **1 select line**.
- When **S = 0**, the input is sent to **Y0**.
- When **S = 1**, the input is sent to **Y1**.
- Only **one output** receives the input at a time.

---

* **One-Line Definition (Interview)**

> A 1 : 2 Demultiplexer (DEMUX) is a combinational logic circuit that routes one input signal to one of two outputs based on a single select line.
