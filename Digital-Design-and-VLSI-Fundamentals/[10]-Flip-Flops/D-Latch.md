# **D Latch**

* **What Problem Does It Solve?**
  - A D Latch (Data Latch) is a digital sequential circuit.
  - It stores one bit of binary data (0 or 1).
  - It eliminates the invalid state found in the SR Latch.
  - It transfers the input to the output only when the Enable (E) signal is HIGH.

---

* **Why is it used?**

  *A D Latch is used because:*

  - It stores one bit of binary information.
  - It removes the invalid condition of the SR Latch.
  - It provides temporary data storage.
  - It is simple and reliable.
  - It is used as a building block for flip-flops and memory circuits.

---

* **Where is it used?**

  *A D Latch is widely used in:*

  - Registers.
  - Memory circuits.
  - Data storage systems.
  - CPUs (Processors).
  - Digital control systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Sequential logic circuits.

---

* **Circuit Diagram:**

![D_LATCH](Image/d-latch.png)

---

* **Function of Inputs and Outputs**

  - D = Data input.
  - E = Enable input.
  - Q = Normal output.
  - Q̅ = Complement output.

---

* **Truth Table**

| E | D | Q(next) | Q̅(next) | Operation |
|:-:|:-:|:-------:|:--------:|-----------|
| 0 | X | Previous | Previous | Hold |
| 1 | 0 | 0 | 1 | Reset/Store 0 |
| 1 | 1 | 1 | 0 | Set/Store 1 |

> **Note:** **X = Don't Care**

---

* **Characteristic Table**

| E | D | Q(next) |
|:-:|:-:|:--------:|
| 0 | X | Q |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

---

* **Characteristic Equation**

- **Q(next) = E·D + E̅·Q**

---

* **Working**

- **E = 0** → The latch holds the previous output.
- **E = 1, D = 0** → The output becomes **0**.
- **E = 1, D = 1** → The output becomes **1**.
- When **Enable is HIGH**, the output follows the input.
- When **Enable is LOW**, the previous value is stored.

---

