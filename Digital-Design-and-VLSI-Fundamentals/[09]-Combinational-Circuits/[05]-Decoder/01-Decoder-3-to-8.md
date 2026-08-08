# **3 × 8 Decoder**

* **Overview**

A **3 × 8 Decoder** is a combinational logic circuit that converts 3 input lines into 8 unique output lines. For each combination of the three inputs, exactly one output becomes HIGH while all other outputs remain LOW.

---

* **Definition**

A **3 × 8 Decoder** is a digital combinational circuit with 3 input lines and 8 output lines, where the binary value applied to the inputs selects exactly one of the eight outputs.

---

* **Purpose**
  - To decode binary information.
  - To select one output from multiple output lines.
  - To convert 3-bit binary input into one of 8 unique output signals.
  - To implement memory and control circuits.

---

* **Importance**
  - Simplifies binary decoding.
  - Provides unique output selection.
  - Can be used to construct larger decoders.
  - Widely used in memory addressing and digital control systems.

---

* **Working Principle**
  - A **3 × 8 Decoder** has:
    - Three Input Lines (**A**, **B**, **C**).
    - Eight Output Lines (**Y0** to **Y7**).
  - The three input bits represent one of eight possible binary combinations.
  - For each input combination, only the corresponding output becomes HIGH.
  - All other outputs remain LOW.

---

* **Circuit Description**
  - Components Required:
    - NOT Gates.
    - AND Gates.
  - A **3 × 8 Decoder** can be implemented using:
    - Three NOT Gates.
    - Eight AND Gates.
  - The NOT gates generate the complemented inputs.
  - The AND gates generate the eight unique output combinations.

---

* **Circuit Diagram:**

![3 × 8 Decoder](DECODER-Images/3x8-decoder.png)

---

* **Truth Table:**

| A | B | C | Y0 | Y1 | Y2 | Y3 | Y4 | Y5 | Y6 | Y7 |
|---|---|---|----|----|----|----|----|----|----|----|
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |

---

* **Boolean Expression**

**Y0 = A̅ · B̅ · C̅**

**Y1 = A̅ · B̅ · C**

**Y2 = A̅ · B · C̅**

**Y3 = A̅ · B · C**

**Y4 = A · B̅ · C̅**

**Y5 = A · B̅ · C**

**Y6 = A · B · C̅**

**Y7 = A · B · C**

---

* **Input and Output Description**
  - Inputs:-
    - A, B, C [3 Inputs]
  - Outputs:-
    - Y0, Y1, Y2, Y3, Y4, Y5, Y6, Y7 [8 Outputs]

  - **A, B, and C** are the binary input signals.
  - **Y0** is selected when A = 0, B = 0, C = 0.
  - **Y1** is selected when A = 0, B = 0, C = 1.
  - **Y2** is selected when A = 0, B = 1, C = 0.
  - **Y3** is selected when A = 0, B = 1, C = 1.
  - **Y4** is selected when A = 1, B = 0, C = 0.
  - **Y5** is selected when A = 1, B = 0, C = 1.
  - **Y6** is selected when A = 1, B = 1, C = 0.
  - **Y7** is selected when A = 1, B = 1, C = 1.

---

* **Working Example**
  - Consider:

    - A = 1
    - B = 0
    - C = 1

Output:

- Y5 = **1**
- Y0 = Y1 = Y2 = Y3 = Y4 = Y6 = Y7 = **0**

Another Example:

- A = 0
- B = 1
- C = 1

Output:

- Y3 = **1**
- All other outputs = **0**

---

* **Applications**

  *The 3 × 8 Decoder is used in:*

  - Memory Address Decoding.
  - Instruction Decoding.
  - Data Selection.
  - Digital Control Systems.
  - Device Selection.
  - Microprocessor Systems.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Simple and efficient decoding.
  - Fast operation.
  - Provides unique output selection.
  - Easy to implement.
  - Can be used to construct larger decoders.

---

* **Limitations**
  - Number of outputs increases exponentially with the number of inputs.
  - Larger decoders require more hardware.
  - Propagation delay can increase as the circuit becomes larger.

---

* **Real-World Example**
  - Memory Address Decoder.
  - Microprocessor Instruction Decoder.
  - Device Selection Circuit.
  - Digital Control Unit.
  - FPGA-Based Digital Systems.

---

* **Key Points**
  - A **3 × 8 Decoder** has 3 inputs and 8 outputs.
  - It has **2³ = 8** possible input combinations.
  - Only one output is HIGH for each input combination.
  - It can be implemented using NOT and AND gates.
  - It is commonly used for memory and instruction decoding.

---

* **Interview Questions**

**1. What is a 3 × 8 Decoder?**

**Answer:**

A 3 × 8 Decoder is a combinational logic circuit that converts 3 binary input lines into 8 unique output lines, with only one output active for each input combination.

---

**2. How many input lines does a 3 × 8 Decoder have?**

**Answer:**

It has **3 input lines**.

---

**3. How many output lines does a 3 × 8 Decoder have?**

**Answer:**

It has **8 output lines**.

---

**4. How many input combinations are possible in a 3 × 8 Decoder?**

**Answer:**

There are **2³ = 8 possible input combinations**.

---

**5. What happens when A = 1, B = 0, and C = 1?**

**Answer:**

**Y5 becomes HIGH (1)** and all other outputs remain LOW (0).

---

**6. What is the Boolean expression for Y7?**

**Answer:**

**Y7 = A · B · C**

---

**7. How can a 3 × 8 Decoder be implemented using basic gates?**

**Answer:**

It can be implemented using **three NOT gates and eight AND gates**.

---

**8. What is the main function of a Decoder?**

**Answer:**

The main function of a Decoder is to convert binary input information into a unique active output line.

---

**9. Where is a 3 × 8 Decoder commonly used?**

**Answer:**

It is commonly used in memory address decoding, instruction decoding, device selection, FPGA, ASIC, RTL, and VLSI systems.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Inputs → 3
  - Outputs → 8
  - Possible Combinations → 2³ = 8
  - Active Outputs → 1
  - Basic Gates → NOT + AND
  - Used for → Binary Decoding

---

* **Summary**

A **3 × 8 Decoder** is a combinational logic circuit that converts three binary inputs into eight unique output lines. For every input combination, exactly one output becomes HIGH while the remaining outputs stay LOW. It is widely used in memory addressing, instruction decoding, device selection, FPGA, ASIC, RTL, and VLSI designs.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Donald D. Givone – *Digital Principles and Design*.
  - Neso Academy – Decoder.
  - GeeksforGeeks – Decoder.

---

* **Waveform / Timing Diagram:**

![3 × 8 Decoder Timing Waveform](Image/3x8_decoder_waveform.png)
