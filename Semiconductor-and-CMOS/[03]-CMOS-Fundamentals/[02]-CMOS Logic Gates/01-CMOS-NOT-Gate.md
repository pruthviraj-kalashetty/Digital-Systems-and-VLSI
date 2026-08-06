# **CMOS NOT Gate (CMOS Inverter)**

* **Overview**

A CMOS NOT Gate, also known as a **CMOS Inverter**, is the most fundamental CMOS logic circuit in digital electronics. It uses one PMOS transistor and one NMOS transistor connected in a complementary configuration to invert the input signal. CMOS inverters are widely used in digital circuits because they provide high speed, low power consumption, and excellent noise immunity.

---

* **Definition**

A **CMOS NOT Gate (CMOS Inverter)** is a digital logic circuit that uses one PMOS transistor and one NMOS transistor to produce the complement of the input signal. If the input is **LOW (0)**, the output is **HIGH (1)**, and if the input is **HIGH (1)**, the output is **LOW (0)**.

---

* **Purpose**
  - To invert the input signal.
  - To implement logical NOT operation.
  - To provide high-speed signal inversion.
  - To serve as the basic building block of CMOS logic circuits.

---

* **Importance**
  - It is the simplest CMOS logic circuit.
  - It forms the foundation of all CMOS digital circuits.
  - It provides low static power consumption.
  - It is widely used in processors, memory, FPGA, ASIC, and VLSI designs.

---

* **Working Principle**
  - A CMOS NOT Gate consists of one **PMOS** transistor connected to **VDD** and one **NMOS** transistor connected to **Ground (GND)**.
  - Both transistor gates are connected together to form the input.
  - Their drains are connected together to form the output.

**Case 1: Input = 0**
- PMOS turns **ON**.
- NMOS turns **OFF**.
- Output is connected to **VDD**.
- Output = **1**.

**Case 2: Input = 1**
- PMOS turns **OFF**.
- NMOS turns **ON**.
- Output is connected to **Ground**.
- Output = **0**.

---

* **Circuit Description**
  - Components Required:
    - One PMOS Transistor.
    - One NMOS Transistor.
    - Power Supply (VDD).
    - Ground (GND).
  - PMOS forms the **Pull-Up Network (PUN)**.
  - NMOS forms the **Pull-Down Network (PDN)**.
  - The output is taken from the common drain connection.

---

* **Circuit Diagram:**

![CMOS NOT Gate](Image/cmos-not-gate.png)

---

* **Truth Table:**

| Input (A) | Output (Y) |
|-----------|------------|
| 0 | 1 |
| 1 | 0 |

---

* **Boolean Expression**

**Y = A̅**

---

* **Input and Output Description**
  - Input:-
    - A [1 Input]
  - Output:-
    - Y [1 Output]

  - **A** is the input signal applied to both PMOS and NMOS gates.
  - **Y** is the inverted (complement) output.
  - When **A = 0**, PMOS conducts and NMOS is OFF, making **Y = 1**.
  - When **A = 1**, NMOS conducts and PMOS is OFF, making **Y = 0**.

---

* **Working Example**
  - Consider:

    - A = 0

Output:

- PMOS = ON
- NMOS = OFF
- **Y = 1**

Another Example:

- A = 1

Output:

- PMOS = OFF
- NMOS = ON
- **Y = 0**

---

* **Applications**

  *The CMOS NOT Gate is used in:*

  - Digital Logic Circuits.
  - Arithmetic Logic Units (ALUs).
  - Microprocessors.
  - Memory Circuits.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Very low static power consumption.
  - High switching speed.
  - High noise immunity.
  - Full logic voltage swing.
  - Simple and reliable design.

---

* **Limitations**
  - Dynamic power consumption increases with switching frequency.
  - Requires both PMOS and NMOS transistors.
  - Performance depends on transistor sizing.

---

* **Real-World Example**
  - Computer Processors.
  - Mobile Processors.
  - RAM and ROM Circuits.
  - FPGA Devices.
  - ASIC Chips.

---

* **Key Points**
  - CMOS NOT Gate is also called a **CMOS Inverter**.
  - Built using **1 PMOS + 1 NMOS** transistor.
  - PMOS forms the Pull-Up Network (PUN).
  - NMOS forms the Pull-Down Network (PDN).
  - Input = 0 → Output = 1.
  - Input = 1 → Output = 0.
  - Boolean Expression:

    **Y = A̅**

---

* **Interview Questions**

**1. What is a CMOS NOT Gate?**

**Answer:**

A CMOS NOT Gate is a digital logic circuit that uses one PMOS transistor and one NMOS transistor to invert the input signal.

---

**2. Why is it called a CMOS Inverter?**

**Answer:**

Because it produces the complement (inverse) of the input signal using complementary MOS transistors (PMOS and NMOS).

---

**3. How many transistors are used in a CMOS NOT Gate?**

**Answer:**

A CMOS NOT Gate uses **2 transistors**: **1 PMOS** and **1 NMOS**.

---

**4. What happens when the input is LOW (0)?**

**Answer:**

The PMOS turns ON, the NMOS turns OFF, and the output becomes HIGH (1).

---

**5. What happens when the input is HIGH (1)?**

**Answer:**

The PMOS turns OFF, the NMOS turns ON, and the output becomes LOW (0).

---

**6. Why is CMOS technology preferred over other logic families?**

**Answer:**

Because CMOS provides low power consumption, high noise immunity, high switching speed, and high integration density.

---

**7. What are the Pull-Up Network (PUN) and Pull-Down Network (PDN)?**

**Answer:**

The **PMOS** transistor forms the **Pull-Up Network (PUN)**, and the **NMOS** transistor forms the **Pull-Down Network (PDN)**.

---

**8. Mention four applications of a CMOS NOT Gate.**

**Answer:**

- Microprocessors.
- Memory Circuits.
- FPGA Design.
- ASIC Design.

---

* **Quick Revision**
  - Circuit Type → CMOS Combinational Logic
  - Input → A
  - Output → Y
  - PMOS → Pull-Up Network (PUN)
  - NMOS → Pull-Down Network (PDN)
  - Input = 0 → Output = 1
  - Input = 1 → Output = 0
  - Boolean Expression → **Y = A̅**

---

* **Summary**

A **CMOS NOT Gate (CMOS Inverter)** is the simplest CMOS logic circuit and is built using one PMOS transistor and one NMOS transistor connected in a complementary configuration. It performs the NOT operation by producing the complement of the input signal. Due to its low power consumption, high speed, and excellent noise immunity, it is widely used in processors, memory circuits, FPGA, ASIC, and VLSI systems.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Neil H. E. Weste & David Harris – *CMOS VLSI Design*.
  - Jan M. Rabaey – *Digital Integrated Circuits*.
  - R. Jacob Baker – *CMOS: Circuit Design, Layout, and Simulation*.
  - Neso Academy – CMOS Digital Circuits.
  - GeeksforGeeks – CMOS Logic.

---

* **Waveform / Timing Diagram:**

![CMOS NOT Gate Timing Waveform](Image/cmos_not_gate_waveform.png)
