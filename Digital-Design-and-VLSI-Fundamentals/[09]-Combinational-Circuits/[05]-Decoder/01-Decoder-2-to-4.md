# **2 × 4 Decoder**

* **Overview**

A **2 × 4 Decoder** is a combinational logic circuit that converts 2 input lines into 4 unique output lines. For each combination of the two inputs, exactly one output becomes HIGH while all other outputs remain LOW.

---

* **Definition**

A **2 × 4 Decoder** is a digital combinational circuit with 2 input lines and 4 output lines, where the binary value applied to the inputs selects exactly one of the four outputs.

---

* **Purpose**
  - To decode binary information.
  - To select one output from multiple output lines.
  - To convert binary inputs into unique output signals.
  - To implement memory and control circuits.

---

* **Importance**
  - Simplifies binary decoding.
  - Provides unique output selection.
  - Forms the basic building block of larger decoders.
  - Widely used in memory addressing and digital control systems.

---

* **Working Principle**
  - A **2 × 4 Decoder** has:
    - Two Input Lines (**A**, **B**).
    - Four Output Lines (**Y0**, **Y1**, **Y2**, **Y3**).
  - The two input bits represent one of four possible binary combinations.
  - For each input combination, only the corresponding output becomes HIGH.
  - All other outputs remain LOW.

---

* **Circuit Description**
  - Components Required:
    - NOT Gates.
    - AND Gates.
  - A **2 × 4 Decoder** can be implemented using:
    - Two NOT Gates.
    - Four AND Gates.
  - The NOT gates generate the complemented inputs.
  - The AND gates generate the four unique output combinations.

---

* **Circuit Diagram:**

![2 × 4 Decoder](DECODER-Image/2x4-decoder.png)

---

* **Truth Table:**

| A | B | Y0 | Y1 | Y2 | Y3 |
|---|---|----|----|----|----|
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 | 0 | 1 |

---

* **Boolean Expression**

**Y0 = A̅ · B̅**

**Y1 = A̅ · B**

**Y2 = A · B̅**

**Y3 = A · B**

---

* **Input and Output Description**
  - Inputs:-
    - A, B [2 Inputs]
  - Outputs:-
    - Y0, Y1, Y2, Y3 [4 Outputs]

  - **A** and **B** are the binary input signals.
  - **Y0** is selected when A = 0 and B = 0.
  - **Y1** is selected when A = 0 and B = 1.
  - **Y2** is selected when A = 1 and B = 0.
  - **Y3** is selected when A = 1 and B = 1.

---

* **Working Example**
  - Consider:

    - A = 1
    - B = 0

Output:

- Y2 = **1**
- Y0 = Y1 = Y3 = **0**

Another Example:

- A = 0
- B = 1

Output:

- Y1 = **1**
- Y0 = Y2 = Y3 = **0**

---

* **Applications**

  *The 2 × 4 Decoder is used in:*

  - Memory Address Decoding.
  - Data Selection.
  - Instruction Decoding.
  - Digital Control Systems.
  - Demultiplexing.
  - Microprocessor Systems.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Simple circuit design.
  - Fast decoding operation.
  - Easy to implement.
  - Provides unique output selection.
  - Useful for larger decoder designs.

---

* **Limitations**
  - Number of outputs increases exponentially with the number of inputs.
  - Larger decoders require more hardware.
  - Propagation delay increases as the circuit becomes larger.

---

* **Real-World Example**
  - Memory Address Decoder.
  - Microprocessor Instruction Decoder.
  - Digital Control Unit.
  - Device Selection Circuit.
  - FPGA-Based Digital Systems.

---

* **Key Points**
  - A **2 × 4 Decoder** has 2 inputs and 4 outputs.
  - It has **2² = 4** possible input combinations.
  - Only one output is HIGH for each input combination.
  - It can be implemented using NOT and AND gates.
  - Widely used in memory addressing and digital control systems.

---

* **Interview Questions**

**1. What is a 2 × 4 Decoder?**

**Answer:**

A 2 × 4 Decoder is a combinational logic circuit that converts 2 binary input lines into 4 unique output lines, with only one output active for each input combination.

---

**2. How many outputs does a 2 × 4 Decoder have?**

**Answer:**

It has **4 output lines**.

---

**3. How many input combinations are possible in a 2 × 4 Decoder?**

**Answer:**

There are **2² = 4 possible input combinations**.

---

**4. What happens when A = 1 and B = 0?**

**Answer:**

**Y2 becomes HIGH (1)** and all other outputs remain LOW (0).

---

**5. What is the Boolean expression for Y3?**

**Answer:**

**Y3 = A · B**

---

**6. How is a 2 × 4 Decoder implemented using basic gates?**

**Answer:**

It can be implemented using **two NOT gates and four AND gates**.

---

**7. What is the main function of a Decoder?**

**Answer:**

The main function of a Decoder is to convert binary input information into a unique active output line.

---

**8. Where is a 2 × 4 Decoder commonly used?**

**Answer:**

It is commonly used in memory address decoding, instruction decoding, digital control systems, FPGA, ASIC, RTL, and VLSI designs.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Inputs → 2
  - Outputs → 4
  - Possible Combinations → 2² = 4
  - Active Outputs → 1
  - Basic Gates → NOT + AND
  - Used for → Binary Decoding

---

* **Summary**

A **2 × 4 Decoder** is a combinational logic circuit that converts two binary inputs into four unique output lines. For each input combination, exactly one output becomes HIGH. It is an important building block in memory addressing, instruction decoding, digital control systems, FPGA, ASIC, RTL, and VLSI designs.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Donald D. Givone – *Digital Principles and Design*.
  - Neso Academy – Decoder.
  - GeeksforGeeks – Decoder.

---

* **Waveform / Timing Diagram:**

![2 × 4 Decoder Timing Waveform](Image/2x4_decoder_waveform.png)
