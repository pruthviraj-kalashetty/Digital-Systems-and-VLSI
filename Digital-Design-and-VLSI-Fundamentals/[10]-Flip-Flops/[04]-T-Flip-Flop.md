# **T Flip-Flop**

* **What Problem Does It Solve?**
  - A T Flip-Flop (Toggle Flip-Flop) is a digital sequential circuit.
  - It stores one bit of binary data (0 or 1).
  - It changes (toggles) its output whenever the toggle input is HIGH.
  - It changes its output only on the active edge of the clock signal.

---

* **Why is it used?**

  *A T Flip-Flop is used because:*

  - It stores one bit of binary information.
  - It performs the toggle operation efficiently.
  - It is simple and reliable.
  - It is widely used in counters and frequency division circuits.
  - It provides synchronized operation using a clock signal.

---

* **Where is it used?**

  *A T Flip-Flop is widely used in:*

  - Binary counters.
  - Frequency dividers.
  - Digital clocks.
  - Registers.
  - CPUs (Processors).
  - Digital VLSI and RTL design.
  - FPGA and ASIC designs.
  - Sequential logic circuits.

---

* **Circuit Diagram:**

![T_FLIP_FLOP](Circuit-Images/t-flip-flop.png)

---

* **Function of Inputs and Outputs**

  - T = Toggle input.
  - CLK = Clock input.
  - Q = Normal output.
  - Q̅ = Complement output.

---

* **Truth Table**

| CLK | T | Q(next) | Q̅(next) | Operation |
|:---:|:-:|:-------:|:--------:|-----------|
| ↑ | 0 | Previous | Previous | Hold |
| ↑ | 1 | Toggle | Toggle | Toggle |

> **Note:**
> - **↑ = Rising edge of the clock**
> - **Toggle** means the output changes from **0 to 1** or **1 to 0**.

---

* **Characteristic Table**

| T | Q(next) |
|:-:|:--------:|
| 0 | Q |
| 1 | Q̅ |

---

* **Characteristic Equation**

- **Q(next) = T ⊕ Q**

---

* **Working**

- **T = 0** → The output remains the same (Hold).
- **T = 1** → The output toggles (changes to the opposite state).
- The output changes only on the active clock edge.
- It stores one bit of binary data until the next clock pulse.

---

