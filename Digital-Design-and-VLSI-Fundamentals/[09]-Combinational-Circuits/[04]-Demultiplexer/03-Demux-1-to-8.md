# **1 × 8 Demultiplexer (DEMUX)**

* **Overview**

A **1 × 8 Demultiplexer (DEMUX)** is a combinational logic circuit that routes one input signal to one of eight output lines based on the values of three select lines. It performs the opposite operation of a Multiplexer (MUX) and is widely used in digital systems for data distribution, signal routing, and memory addressing.

---

* **Definition**

A **1 × 8 Demultiplexer (DEMUX)** is a digital combinational circuit that takes one data input, three select lines, and directs the input to one of eight outputs depending on the select line values.

---

* **Purpose**
  - To distribute one input signal to one of eight outputs.
  - To perform controlled signal routing.
  - To simplify digital circuit interconnections.
  - To implement efficient data distribution.

---

* **Importance**
  - Performs the reverse operation of a Multiplexer.
  - Enables efficient signal routing.
  - Reduces wiring complexity.
  - Widely used in FPGA, ASIC, RTL, and VLSI designs.

---

* **Working Principle**
  - A **1 × 8 DEMUX** has:
    - One Data Input (**I**).
    - Three Select Lines (**S2**, **S1**, **S0**).
    - Eight Outputs (**Y0** to **Y7**).
  - The combination of the select lines determines which output receives the input signal.
  - The selected output follows the input, while all other outputs remain LOW (0).

---

* **Circuit Description**
  - Components Required:
    - NOT Gates.
    - AND Gates.
  - A **1 × 8 DEMUX** consists of:
    - One Data Input (I).
    - Three Select Lines (S2, S1, S0).
    - Eight Outputs (Y0, Y1, Y2, Y3, Y4, Y5, Y6, Y7).
    - Three NOT Gates.
    - Eight AND Gates.

---

* **Circuit Diagram:**

![1 × 8 Demultiplexer](Demultiplexer-Images/1x8-demultiplexer.png)

---

* **Truth Table:**

| S2 | S1 | S0 | I | Y0 | Y1 | Y2 | Y3 | Y4 | Y5 | Y6 | Y7 |
|----|----|----|---|----|----|----|----|----|----|----|----|
| 0 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |

*(When **I = 0**, all outputs remain **0** regardless of the select line values.)*

---

* **Boolean Expression**

**Y0 = I · S2̅ · S1̅ · S0̅**

**Y1 = I · S2̅ · S1̅ · S0**

**Y2 = I · S2̅ · S1 · S0̅**

**Y3 = I · S2̅ · S1 · S0**

**Y4 = I · S2 · S1̅ · S0̅**

**Y5 = I · S2 · S1̅ · S0**

**Y6 = I · S2 · S1 · S0̅**

**Y7 = I · S2 · S1 · S0**

---

* **Input and Output Description**
  - Inputs:-
    - I (Data Input)
    - S2 (Select Line 2)
    - S1 (Select Line 1)
    - S0 (Select Line 0)
  - Outputs:-
    - Y0
    - Y1
    - Y2
    - Y3
    - Y4
    - Y5
    - Y6
    - Y7

  - **I** is the input signal to be routed.
  - **S2, S1, and S0** determine the selected output.
  - Only one output receives the input signal at a time.
  - All unselected outputs remain LOW.

---

* **Working Example**

Consider:

- I = **1**
- S2 = **1**
- S1 = **0**
- S0 = **1**

Output:

- Y5 = **1**
- Y0, Y1, Y2, Y3, Y4, Y6, Y7 = **0**

Another Example:

- I = **1**
- S2 = **0**
- S1 = **1**
- S0 = **0**

Output:

- Y2 = **1**
- All remaining outputs = **0**

---

* **Applications**

  *The 1 × 8 Demultiplexer is used in:*

  - Data Distribution Systems.
  - Communication Systems.
  - Memory Address Decoding.
  - Signal Routing.
  - Digital Switching Circuits.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Efficient signal routing.
  - Simple implementation.
  - Reduces wiring complexity.
  - High-speed operation.
  - Easy hardware implementation.

---

* **Limitations**
  - Only one output can be selected at a time.
  - Hardware complexity increases with more outputs.
  - Requires additional select lines for larger DEMUX circuits.

---

* **Real-World Example**
  - Memory Selection Circuits.
  - Communication Networks.
  - Embedded Systems.
  - FPGA-Based Systems.
  - Digital Signal Distribution.

---

* **Key Points**
  - A **1 × 8 DEMUX** has one input, three select lines, and eight outputs.
  - It performs the opposite function of a Multiplexer.
  - The selected output receives the input signal.
  - Uses three NOT gates and eight AND gates.
  - Widely used in FPGA, ASIC, RTL, and VLSI systems.

---

* **Interview Questions**

**1. What is a 1 × 8 Demultiplexer?**

**Answer:**

A 1 × 8 Demultiplexer is a combinational logic circuit that routes one input to one of eight outputs based on three select lines.

---

**2. How many select lines are required for a 1 × 8 DEMUX?**

**Answer:**

A **1 × 8 DEMUX requires three select lines**.

---

**3. How many outputs does a 1 × 8 DEMUX have?**

**Answer:**

It has **eight outputs**.

---

**4. What are the Boolean expressions of a 1 × 8 DEMUX?**

**Answer:**

- **Y0 = I · S2̅ · S1̅ · S0̅**
- **Y1 = I · S2̅ · S1̅ · S0**
- **Y2 = I · S2̅ · S1 · S0̅**
- **Y3 = I · S2̅ · S1 · S0**
- **Y4 = I · S2 · S1̅ · S0̅**
- **Y5 = I · S2 · S1̅ · S0**
- **Y6 = I · S2 · S1 · S0̅**
- **Y7 = I · S2 · S1 · S0**

---

**5. What happens when S2 = 1, S1 = 0, and S0 = 1?**

**Answer:**

The input is routed to **Y5**, while all other outputs remain LOW.

---

**6. What is the main function of a Demultiplexer?**

**Answer:**

Its main function is to route one input signal to one of several output lines based on the select lines.

---

**7. What is the difference between a Multiplexer and a Demultiplexer?**

**Answer:**

A Multiplexer selects **one of many inputs and sends it to one output**, whereas a Demultiplexer routes **one input to one of many outputs**.

---

**8. Where is a 1 × 8 DEMUX commonly used?**

**Answer:**

It is commonly used in communication systems, memory decoding, FPGA, ASIC, RTL design, and VLSI systems.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Data Input → 1
  - Select Lines → 3
  - Outputs → 8
  - Boolean Expressions:
    - **Y0 = I · S2̅ · S1̅ · S0̅**
    - **Y1 = I · S2̅ · S1̅ · S0**
    - **Y2 = I · S2̅ · S1 · S0̅**
    - **Y3 = I · S2̅ · S1 · S0**
    - **Y4 = I · S2 · S1̅ · S0̅**
    - **Y5 = I · S2 · S1̅ · S0**
    - **Y6 = I · S2 · S1 · S0̅**
    - **Y7 = I · S2 · S1 · S0**
  - Opposite of Multiplexer

---

* **Summary**

A **1 × 8 Demultiplexer (DEMUX)** is a combinational logic circuit that routes one input signal to one of eight outputs based on three select lines. It performs the reverse operation of a Multiplexer and is widely used in data distribution, signal routing, memory decoding, FPGA, ASIC, RTL, and VLSI applications.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Donald D. Givone – *Digital Principles and Design*.
  - Neso Academy – Multiplexer and Demultiplexer.
  - GeeksforGeeks – Demultiplexer.

---

* **Waveform / Timing Diagram:**

![1 × 8 Demultiplexer Timing Waveform](Image/1x8_demultiplexer_waveform.png)
