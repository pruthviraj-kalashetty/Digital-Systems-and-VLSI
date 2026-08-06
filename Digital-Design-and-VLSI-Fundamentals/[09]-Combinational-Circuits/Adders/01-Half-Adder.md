# **Half Adder**

* **Overview**

A Half Adder is a fundamental combinational logic circuit used in digital electronics to add two single-bit binary numbers. It generates two outputs: **Sum (S)** and **Carry (C)**. The Half Adder is the basic building block for designing Full Adders and other arithmetic circuits.

---

* **Definition**

A Half Adder is a combinational logic circuit that adds two one-bit binary inputs (**A** and **B**) and produces two outputs: **Sum (S)** and **Carry (C)**.

---

* **Purpose**
  - To add two binary bits.
  - To generate both Sum and Carry outputs.
  - To perform simple binary addition.
  - To serve as a building block for Full Adders.

---

* **Importance**
  - It is one of the basic arithmetic circuits in digital electronics.
  - It is used to construct Full Adders.
  - It forms the foundation of binary addition circuits.
  - It is widely used in digital systems and processors.

---

* **Working Principle**
  - A Half Adder accepts two binary inputs: **A** and **B**.
  - It adds both input bits simultaneously.
  - The **Sum (S)** represents the least significant bit (LSB) of the result.
  - The **Carry (C)** is generated when both inputs are HIGH (1).

---

* **Circuit Description**
  - A Half Adder consists of:
    - One XOR Gate for generating the Sum.
    - One AND Gate for generating the Carry.
  - The XOR gate produces the Sum output.
  - The AND gate produces the Carry output.

---

* **Circuit Diagram:**

![Half Adder](Image/half-adder.png)

---

* **Truth Table:**

genui{"computing_fundamentals_algorithms_learning_block":{"type_id":"HALF_FULL_ADDER_LOGIC"}}

| A | B | S | C |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

---

* **Boolean Expression**

**Sum (S):**

**S = A ⊕ B**

**Carry (C):**

**C = A.B**

---

* **Input and Output Description**
  - Inputs:- A, B [2 Inputs]
  - Outputs:-
    - Sum (S)
    - Carry (C)

  - **A** and **B** are the binary numbers to be added.
  - **S** represents the sum bit.
  - **C** represents the carry generated during addition.

---

* **Working Example**
  - Consider:
    - A = 1
    - B = 1

Binary Addition:

```
   1
 + 1
 ----
  10
```

Output:

- **Sum (S) = 0**
- **Carry (C) = 1**

---

* **Applications**

  *The Half Adder is used in:*

  - Full Adders.
  - Arithmetic Logic Units (ALUs).
  - Digital Computers.
  - Calculator Circuits.
  - Binary Addition Circuits.
  - FPGA Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Simple circuit design.
  - Easy to implement.
  - Requires fewer logic gates.
  - Fast binary addition.
  - Forms the basis of larger arithmetic circuits.

---

* **Limitations**
  - Cannot add a Carry-in input.
  - Suitable only for adding two binary bits.
  - Cannot perform multi-bit addition independently.
  - Requires a Full Adder for cascading operations.

---

* **Real-World Example**
  - Calculator Circuits.
  - Computer Arithmetic Units.
  - Arithmetic Logic Units (ALUs).
  - FPGA-Based Designs.
  - Digital Processors.

---

* **Key Points**
  - A Half Adder is a combinational logic circuit.
  - It adds two binary inputs.
  - Inputs: **A, B**
  - Outputs: **Sum (S), Carry (C)**
  - Sum Equation:

    **S = A ⊕ B**

  - Carry Equation:

    **C = A.B**

---

* **Interview Questions**

**1. What is a Half Adder?**

**Answer:**

A Half Adder is a combinational logic circuit that adds two one-bit binary inputs and produces a Sum and a Carry output.

---

**2. How many inputs and outputs does a Half Adder have?**

**Answer:**

A Half Adder has **2 inputs (A and B)** and **2 outputs (Sum and Carry).**

---

**3. What is the Boolean expression for the Sum output?**

**Answer:**

**S = A ⊕ B**

---

**4. What is the Boolean expression for the Carry output?**

**Answer:**

**C = A.B**

---

**5. Which logic gates are used to implement a Half Adder?**

**Answer:**

A Half Adder is implemented using **one XOR gate** and **one AND gate**.

---

**6. What is the main limitation of a Half Adder?**

**Answer:**

A Half Adder cannot accept a Carry-in input, so it cannot be directly used for multi-bit binary addition.

---

**7. Mention four applications of a Half Adder.**

**Answer:**

- Full Adders.
- Arithmetic Logic Units (ALUs).
- Calculator Circuits.
- Digital Computers.

---

**8. What is the difference between a Half Adder and a Full Adder?**

**Answer:**

A Half Adder adds **two** binary inputs and has no Carry-in input, whereas a Full Adder adds **three** inputs, including Carry-in.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Inputs → A, B
  - Outputs → Sum (S), Carry (C)
  - Sum Equation → **S = A ⊕ B**
  - Carry Equation → **C = A.B**
  - Built Using → One XOR Gate + One AND Gate

---

* **Summary**

A Half Adder is a combinational logic circuit that adds two one-bit binary inputs (**A** and **B**) and produces **Sum** and **Carry** outputs. It is the simplest arithmetic circuit and serves as the foundation for designing Full Adders, Arithmetic Logic Units (ALUs), processors, and other digital systems. Since it does not have a Carry-in input, it is mainly used for simple binary addition or as a building block for more complex adders.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Donald D. Givone – *Digital Principles and Design*.
  - R. P. Jain – *Modern Digital Electronics*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Neso Academy – Digital Electronics.
  - GeeksforGeeks – Digital Logic.

---

* **Waveform / Timing Diagram:**

![Half Adder Timing Waveform](Image/half_adder_waveform.png)
