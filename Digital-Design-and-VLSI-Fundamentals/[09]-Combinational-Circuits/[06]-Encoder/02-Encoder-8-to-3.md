# **8 × 3 Encoder**

* **Overview**

An **8 × 3 Encoder** is a combinational logic circuit that converts one of eight active input lines into a corresponding 3-bit binary code. For each valid input combination, the encoder produces the binary code representing the active input.

---

* **Definition**

An **8 × 3 Encoder** is a digital combinational circuit with eight input lines and three output lines that converts the active input into its corresponding 3-bit binary representation.

---

* **Purpose**
  - To convert active input signals into binary codes.
  - To reduce the number of output lines.
  - To represent one of eight inputs using only three bits.
  - To simplify digital data transmission and processing.

---

* **Importance**
  - Reduces the number of required output lines.
  - Provides efficient binary encoding.
  - Simplifies digital circuit design.
  - Forms the basic building block for larger encoder circuits.

---

* **Working Principle**
  - An **8 × 3 Encoder** has:
    - Eight Input Lines (**D0** to **D7**).
    - Three Output Lines (**Y2**, **Y1**, **Y0**).
  - Only one input should be HIGH at a time.
  - The encoder identifies the active input.
  - It converts the active input into its corresponding 3-bit binary code.

---

* **Circuit Description**
  - Components Required:
    - OR Gates.
  - An **8 × 3 Encoder** can be implemented using:
    - Three OR Gates.
  - The OR gates generate the three output bits based on the active input.

---

* **Circuit Diagram:**

![8 × 3 Encoder](ENCODER-Images/8x3-encoder.png)

---

* **Truth Table:**

| D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 | Y2 | Y1 | Y0 |
|----|----|----|----|----|----|----|----|----|----|----|----|
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 1 |
| 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 1 | 0 | 1 |
| 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 | 1 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 |

*(Only one input should be HIGH at a time for a basic encoder.)*

---

* **Boolean Expression**

**Y2 = D4 + D5 + D6 + D7**

**Y1 = D2 + D3 + D6 + D7**

**Y0 = D1 + D3 + D5 + D7**

---

* **Input and Output Description**
  - Inputs:-
    - D0, D1, D2, D3, D4, D5, D6, D7 [8 Inputs]
  - Outputs:-
    - Y2, Y1, Y0 [3 Outputs]

  - **D0** represents binary code **000**.
  - **D1** represents binary code **001**.
  - **D2** represents binary code **010**.
  - **D3** represents binary code **011**.
  - **D4** represents binary code **100**.
  - **D5** represents binary code **101**.
  - **D6** represents binary code **110**.
  - **D7** represents binary code **111**.
  - **Y2, Y1, and Y0** provide the 3-bit binary code corresponding to the active input.

---

* **Working Example**
  - Consider:

    - D0 = 0
    - D1 = 0
    - D2 = 0
    - D3 = 0
    - D4 = 0
    - D5 = 1
    - D6 = 0
    - D7 = 0

Output:

- Y2 = **1**
- Y1 = **0**
- Y0 = **1**

Therefore, the output is **101**, which represents **D5**.

Another Example:

- D0 = 0
- D1 = 0
- D2 = 0
- D3 = 0
- D4 = 0
- D5 = 0
- D6 = 1
- D7 = 0

Output:

- Y2 = **1**
- Y1 = **1**
- Y0 = **0**

Therefore, the output is **110**, which represents **D6**.

---

* **Applications**

  *The 8 × 3 Encoder is used in:*

  - Data Encoding Systems.
  - Digital Communication Systems.
  - Keyboard Encoding.
  - Interrupt Encoding.
  - Data Compression.
  - Digital Control Systems.
  - Device Selection.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Reduces the number of output lines.
  - Efficient binary representation.
  - Simple combinational implementation.
  - Reduces hardware connections.
  - Easy to design and implement.

---

* **Limitations**
  - Only one input should be active at a time.
  - Multiple active inputs can produce an invalid or ambiguous output.
  - Basic encoders do not provide priority between inputs.

---

* **Real-World Example**
  - Keyboard Encoder.
  - Interrupt Controller.
  - Digital Communication System.
  - Data Encoding Circuit.
  - Device Selection System.

---

* **Key Points**
  - An **8 × 3 Encoder** has 8 inputs and 3 outputs.
  - It converts one active input into a 3-bit binary code.
  - Only one input should be HIGH at a time.
  - It can be implemented using OR gates.
  - It is the opposite operation of a Decoder.
  - Widely used in FPGA, ASIC, RTL, and VLSI systems.

---

* **Interview Questions**

**1. What is an 8 × 3 Encoder?**

**Answer:**

An 8 × 3 Encoder is a combinational logic circuit that converts one of eight active input lines into a corresponding 3-bit binary output.

---

**2. How many inputs and outputs does an 8 × 3 Encoder have?**

**Answer:**

It has **8 input lines and 3 output lines**.

---

**3. Why does an 8 × 3 Encoder require 3 output lines?**

**Answer:**

Because **2³ = 8**, three binary bits are sufficient to represent all eight input lines.

---

**4. What is the Boolean expression for Y2?**

**Answer:**

**Y2 = D4 + D5 + D6 + D7**

---

**5. What is the Boolean expression for Y1?**

**Answer:**

**Y1 = D2 + D3 + D6 + D7**

---

**6. What is the Boolean expression for Y0?**

**Answer:**

**Y0 = D1 + D3 + D5 + D7**

---

**7. What happens when D5 is HIGH?**

**Answer:**

When **D5 = 1** and all other inputs are 0, the output is **Y2Y1Y0 = 101**.

---

**8. What is the main limitation of a basic encoder?**

**Answer:**

A basic encoder cannot correctly handle multiple active inputs at the same time because the output can become ambiguous.

---

**9. How can the multiple-input problem be solved?**

**Answer:**

The problem can be solved by using a **Priority Encoder**, which gives priority to one input when multiple inputs are active.

---

**10. What is the difference between an Encoder and a Decoder?**

**Answer:**

An Encoder converts **multiple input lines into fewer binary output lines**, whereas a Decoder converts **binary input lines into multiple output lines**.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Inputs → 8
  - Outputs → 3
  - Possible Input Lines → 8
  - Output Code → 3-bit Binary
  - Basic Gates → OR Gates
  - Main Function → Binary Encoding
  - Opposite Operation → Decoder

---

* **Summary**

An **8 × 3 Encoder** is a combinational logic circuit that converts one of eight active input signals into a corresponding 3-bit binary code. It reduces the number of output lines and provides an efficient method of representing input information. It is widely used in keyboard encoding, interrupt controllers, communication systems, FPGA, ASIC, RTL, and VLSI designs.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Donald D. Givone – *Digital Principles and Design*.
  - Neso Academy – Encoder.
  - GeeksforGeeks – Encoder.

---

* **Waveform / Timing Diagram:**

![8 × 3 Encoder Timing Waveform](Image/8x3_encoder_waveform.png)
