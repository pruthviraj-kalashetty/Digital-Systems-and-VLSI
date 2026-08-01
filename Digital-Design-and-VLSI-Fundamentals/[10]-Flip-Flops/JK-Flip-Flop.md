# **JK Flip-Flop**

* **What Problem Does It Solve?**
  - A JK Flip-Flop is a digital sequential circuit.
  - It stores one bit of binary data (0 or 1).
  - It eliminates the invalid state of the SR Flip-Flop.
  - It changes its output only on the active edge of the clock signal.

---

* **Why is it used?**

  *A JK Flip-Flop is used because:*

  - It stores one bit of binary information.
  - It removes the invalid condition of the SR Flip-Flop.
  - It performs Set, Reset, Hold, and Toggle operations.
  - It is reliable for synchronous digital circuits.
  - It is widely used in counters and sequential circuits.

---

* **Where is it used?**

  *A JK Flip-Flop is widely used in:*

  - Counters.
  - Registers.
  - Shift registers.
  - Memory circuits.
  - CPUs (Processors).
  - Digital control systems.
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.

---

* **Circuit Diagram:**

![JK_FLIP_FLOP](Circuit-Images/jk-flip-flop.png)

---

* **Function of Inputs and Outputs**

  - J = Set input.
  - K = Reset input.
  - CLK = Clock input.
  - Q = Normal output.
  - Q̅ = Complement output.

---

* **Truth Table**

| CLK | J | K | Q(next) | Q̅(next) | Operation |
|:---:|:-:|:-:|:-------:|:--------:|-----------|
| ↑ | 0 | 0 | Previous | Previous | Hold |
| ↑ | 0 | 1 | 0 | 1 | Reset |
| ↑ | 1 | 0 | 1 | 0 | Set |
| ↑ | 1 | 1 | Toggle | Toggle | Toggle |

> **Note:**
> - **↑ = Rising edge of the clock**
> - **Toggle** means the output changes from **0 to 1** or **1 to 0**.

---

* **Characteristic Table**

| J | K | Q(next) |
|:-:|:-:|:--------:|
| 0 | 0 | Q |
| 0 | 1 | 0 |
| 1 | 0 | 1 |
| 1 | 1 | Q̅ |

---

* **Characteristic Equation**

- **Q(next) = JQ̅ + K̅Q**

---

* **Working**

- **J = 0, K = 0** → Output holds the previous state.
- **J = 0, K = 1** → Output resets to **0**.
- **J = 1, K = 0** → Output sets to **1**.
- **J = 1, K = 1** → Output toggles (changes to the opposite state).
- The output changes only on the active clock edge.

---



> A JK Flip-Flop is an edge-triggered sequential logic circuit that stores one bit of binary data and performs Hold, Set, Reset, and Toggle operations based on the J and K inputs.
