# **Full Adder Using Two Half Adders**

* **Overview**

A Full Adder can be constructed by connecting two Half Adders and one OR gate. The first Half Adder adds the two input bits (**A** and **B**), while the second Half Adder adds the Sum output of the first Half Adder with the Carry-in (**Cin**). The carry outputs from both Half Adders are combined using an OR gate to generate the final Carry-out (**Cout**).

---

* **Definition**

A Full Adder Using Two Half Adders is a combinational logic circuit that adds three one-bit binary inputs (**A**, **B**, and **Cin**) by connecting two Half Adders and one OR gate, producing **Sum (S)** and **Carry-out (Cout)**.

---

* **Purpose**
  - To add three binary bits.
  - To generate Sum and Carry outputs.
  - To construct a Full Adder using basic building blocks.
  - To understand hierarchical digital circuit design.

---

* **Importance**
  - Demonstrates how complex circuits are built from simpler circuits.
  - Reduces design complexity using modular design.
  - Forms the basis for multi-bit binary adders.
  - Widely used in processors, ALUs, FPGA, and VLSI design.

---

* **Working Principle**
  - The first Half Adder adds inputs **A** and **B**.
  - It produces:
    - Intermediate Sum (**S₁**)
    - Carry (**C₁**)
  - The second Half Adder adds **S₁** and **Cin**.
  - It produces:
    - Final Sum (**S**)
    - Carry (**C₂**)
  - The OR gate combines **C₁** and **C₂** to produce the final Carry-out (**Cout**).

---

* **Circuit Description**
  - Components Required:
    - Two Half Adders.
    - One OR Gate.
  - First Half Adder:
    - Inputs → A, B
    - Outputs → S₁, C₁
  - Second Half Adder:
    - Inputs → S₁, Cin
    - Outputs → S, C₂
  - OR Gate:
    - Inputs → C₁, C₂
    - Output → Cout

---

* **Circuit Diagram:**

![Full Adder Using Two Half Adders](Adders-Images/full-adder-using-two-half-adders.png)

---

* **Truth Table:**

genui{"computing_fundamentals_algorithms_learning_block":{"type_id":"HALF_FULL_ADDER_LOGIC"}}

| A | B | Cin | S | Cout |
|---|---|-----|---|------|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

---

* **Boolean Expression**

**First Half Adder**

- **S₁ = A ⊕ B**
- **C₁ = A.B**

**Second Half Adder**

- **S = S₁ ⊕ Cin**
- **C₂ = S₁.Cin**

**Final Carry**

- **Cout = C₁ + C₂**

Equivalent Expression:

- **S = A ⊕ B ⊕ Cin**
- **Cout = AB + ACin + BCin**

---

* **Input and Output Description**
  - Inputs:- A, B, Cin [3 Inputs]
  - Outputs:-
    - Sum (S)
    - Carry-out (Cout)

  - **A** and **B** are the binary numbers to be added.
  - **Cin** is the carry received from the previous stage.
  - **S** is the final sum output.
  - **Cout** is forwarded to the next Full Adder in multi-bit addition.

---

* **Working Example**
  - Consider:
    - A = 1
    - B = 0
    - Cin = 1

**Step 1:** First Half Adder

- S₁ = 1 ⊕ 0 = 1
- C₁ = 1 × 0 = 0

**Step 2:** Second Half Adder

- S = 1 ⊕ 1 = 0
- C₂ = 1 × 1 = 1

**Step 3:** OR Gate

- Cout = C₁ + C₂
- Cout = 0 + 1 = 1

Final Output:

- **Sum = 0**
- **Carry-out = 1**

---

* **Applications**

  *The Full Adder Using Two Half Adders is used in:*

  - Ripple Carry Adders.
  - Arithmetic Logic Units (ALUs).
  - Digital Computers.
  - Microprocessors.
  - FPGA Design.
  - RTL Design.
  - VLSI Systems.
  - Digital Arithmetic Circuits.

---

* **Advantages**
  - Simple modular design.
  - Easy to understand and implement.
  - Reuses Half Adder circuits.
  - Suitable for hierarchical circuit design.
  - Forms the basis of larger arithmetic circuits.

---

* **Limitations**
  - Requires more hardware than a Half Adder.
  - Ripple Carry Adders built using this design have propagation delay.
  - Delay increases with the number of bits.

---

* **Real-World Example**
  - Computer Processors.
  - Calculator Circuits.
  - Arithmetic Logic Units (ALUs).
  - FPGA-Based Systems.
  - Digital Signal Processing Hardware.

---

* **Key Points**
  - Built using **Two Half Adders + One OR Gate**.
  - First Half Adder adds **A** and **B**.
  - Second Half Adder adds **S₁** and **Cin**.
  - OR gate generates the final Carry-out.
  - Inputs → **A, B, Cin**
  - Outputs → **Sum (S), Carry-out (Cout)**

---

* **Interview Questions**

**1. How is a Full Adder implemented using Half Adders?**

**Answer:**

A Full Adder is implemented using **two Half Adders and one OR gate**.

---

**2. Why are two Half Adders required?**

**Answer:**

The first Half Adder adds **A** and **B**, while the second Half Adder adds the intermediate Sum (**S₁**) with **Cin**.

---

**3. What is the function of the OR gate?**

**Answer:**

The OR gate combines the carry outputs (**C₁** and **C₂**) from the two Half Adders to generate the final Carry-out (**Cout**).

---

**4. What are the intermediate outputs of the first Half Adder?**

**Answer:**

The first Half Adder produces:

- Intermediate Sum (**S₁**)
- Carry (**C₁**)

---

**5. What is the Boolean expression for the final Carry-out?**

**Answer:**

**Cout = C₁ + C₂**

or

**Cout = AB + ACin + BCin**

---

**6. What are the advantages of implementing a Full Adder using Half Adders?**

**Answer:**

It provides a modular design, simplifies circuit implementation, and demonstrates hierarchical digital design.

---

**7. Mention four applications of a Full Adder using Two Half Adders.**

**Answer:**

- Ripple Carry Adders.
- Arithmetic Logic Units (ALUs).
- Computer Processors.
- FPGA Design.

---

**8. How many Half Adders and OR gates are required to implement one Full Adder?**

**Answer:**

One Full Adder requires **two Half Adders** and **one OR gate**.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Components → Two Half Adders + One OR Gate
  - Inputs → A, B, Cin
  - Outputs → Sum (S), Carry-out (Cout)
  - Intermediate Outputs → S₁, C₁, C₂
  - Final Carry → **Cout = C₁ + C₂**

---

* **Summary**

A Full Adder Using Two Half Adders is a modular implementation of a Full Adder that uses two Half Adders and one OR gate. The first Half Adder adds **A** and **B**, while the second Half Adder adds the intermediate Sum with **Cin**. The carry outputs are combined using an OR gate to produce the final Carry-out. This design is widely used in arithmetic circuits, ALUs, processors, FPGA, and VLSI systems.

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

![Full Adder Using Two Half Adders Timing Waveform](Image/full_adder_using_two_half_adders_waveform.png)
