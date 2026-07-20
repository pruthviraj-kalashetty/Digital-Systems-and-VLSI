# **D Flip-Flop**

* **What Problem Does It Solve?**
  - A D Flip-Flop (Data Flip-Flop) is a digital sequential circuit.
  - It stores one bit of binary data (0 or 1).
  - It transfers the input data to the output only on the active edge of the clock.
  - It eliminates the invalid state found in the SR Flip-Flop.

---

* **Why is it used?**

  *A D Flip-Flop is used because:*

  - It stores one bit of binary information.
  - It transfers data only on the clock edge.
  - It provides synchronized data storage.
  - It eliminates the invalid state of the SR Flip-Flop.
  - It is widely used in sequential digital circuits.

---

* **Where is it used?**

  *A D Flip-Flop is widely used in:*

  - Registers.
  - Shift registers.
  - Counters.
  - Memory circuits.
  - CPUs (Processors).
  - Digital control systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.

---

* **Circuit Diagram:**

![D_FLIP_FLOP](Circuits-Images/d-flip-flop.png)

---

* **Function of Inputs and Outputs**

  - D = Data input.
  - CLK = Clock input.
  - Q = Normal output.
  - Q̅ = Complement output.

---

* **Truth Table**

| CLK | D | Q(next) | Q̅(next) | Operation |
|:---:|:-:|:-------:|:--------:|-----------|
| ↑ | 0 | 0 | 1 | Store 0 |
| ↑ | 1 | 1 | 0 | Store 1 |
| No Edge | X | Previous | Previous | Hold |

> **Note:**
> - **↑ = Rising edge of the clock**
> - **X = Don't Care**

---

* **Characteristic Table**

| D | Q(next) |
|:-:|:--------:|
| 0 | 0 |
| 1 | 1 |

---

* **Characteristic Equation**

- **Q(next) = D**

---

* **Working**

- On the **rising edge (↑)** of the clock, the output copies the value of **D**.
- If **D = 0**, then **Q = 0**.
- If **D = 1**, then **Q = 1**.
- Between clock edges, the output remains unchanged.
- It stores one bit of data until the next clock edge.

---

