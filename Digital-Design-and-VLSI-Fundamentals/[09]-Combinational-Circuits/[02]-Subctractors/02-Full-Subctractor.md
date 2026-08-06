# **Full Subtractor**

* **Overview**

A Full Subtractor is a fundamental combinational logic circuit used in digital electronics to subtract three single-bit binary inputs. It subtracts the **Subtrahend (B)** and the **Borrow-in (Bin)** from the **Minuend (A)** and generates two outputs: **Difference (D)** and **Borrow-out (Bout)**. Full Subtractors are the building blocks of multi-bit binary subtraction circuits used in processors, ALUs, and digital systems.

---

* **Definition**

A Full Subtractor is a combinational logic circuit that subtracts two one-bit binary inputs (**A** and **B**) along with a **Borrow-in (Bin)** input and produces two outputs: **Difference (D)** and **Borrow-out (Bout)**.

---

* **Purpose**
  - To subtract three binary bits.
  - To generate Difference and Borrow outputs.
  - To perform multi-bit binary subtraction.
  - To build arithmetic circuits such as ripple borrow subtractors and ALUs.

---

* **Importance**
  - It is one of the most important arithmetic circuits in digital electronics.
  - It is used to construct multi-bit binary subtractors.
  - It forms the foundation of Arithmetic Logic Units (ALUs).
  - It is widely used in processors, computers, and VLSI systems.

---

* **Working Principle**
  - A Full Subtractor accepts three binary inputs: **A**, **B**, and **Borrow-in (Bin)**.
  - It subtracts **B** and **Bin** from **A**.
  - The **Difference (D)** represents the subtraction result.
  - The **Borrow-out (Bout)** indicates whether a borrow is required for the next stage.

---

* **Circuit Description**
  - A Full Subtractor can be implemented using:
    - Two Half Subtractors.
    - One OR Gate.
  - The first Half Subtractor subtracts **B** from **A**.
  - The second Half Subtractor subtracts **Bin** from the first Difference.
  - The OR gate combines the borrow outputs from both Half Subtractors to generate **Borrow-out (Bout)**.

---

* **Circuit Diagram:**

![Full Subtractor](Subctractors-Images/full-subctractor.png)

---

* **Truth Table:**

| A | B | Bin | D | Bout |
|---|---|-----|---|------|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 1 | 1 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 1 |

---

* **Boolean Expression**

**Difference (D):**

**D = A ⊕ B ⊕ Bin**

**Borrow-out (Bout):**

**Bout = A̅B + A̅Bin + BBin**

---

* **Input and Output Description**
  - Inputs:- A, B, Bin [3 Inputs]
  - Outputs:-
    - Difference (D)
    - Borrow-out (Bout)

  - **A** is the Minuend.
  - **B** is the Subtrahend.
  - **Bin** is the Borrow received from the previous stage.
  - **D** represents the subtraction result.
  - **Bout** is passed to the next Full Subtractor during multi-bit subtraction.

---

* **Working Example**
  - Consider:
    - A = 0
    - B = 1
    - Bin = 1

Binary Subtraction:

```text
   0
 - 1
 - 1
 ----
  10
```

Output:

- **Difference (D) = 0**
- **Borrow-out (Bout) = 1**

---

* **Applications**

  *The Full Subtractor is used in:*

  - Ripple Borrow Subtractors.
  - Arithmetic Logic Units (ALUs).
  - Digital Computers.
  - Microprocessors.
  - Calculator Circuits.
  - FPGA Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Subtracts three binary inputs simultaneously.
  - Generates Difference and Borrow outputs.
  - Easy to cascade for multi-bit subtraction.
  - Essential for arithmetic circuit design.
  - Widely used in digital processors.

---

* **Limitations**
  - Ripple Borrow Subtractors built using Full Subtractors have propagation delay.
  - Requires more logic gates than a Half Subtractor.
  - Delay increases as the number of bits increases.

---

* **Real-World Example**
  - Computer Processors.
  - Calculator Circuits.
  - Arithmetic Logic Units (ALUs).
  - FPGA-Based Systems.
  - Digital Signal Processing Hardware.

---

* **Key Points**
  - A Full Subtractor is a combinational logic circuit.
  - It subtracts three binary inputs.
  - Inputs: **A, B, Bin**
  - Outputs: **Difference (D), Borrow-out (Bout)**
  - Difference Equation:

    **D = A ⊕ B ⊕ Bin**

  - Borrow Equation:

    **Bout = A̅B + A̅Bin + BBin**

---

* **Interview Questions**

**1. What is a Full Subtractor?**

**Answer:**

A Full Subtractor is a combinational logic circuit that subtracts two one-bit binary inputs and a Borrow-in input, producing Difference and Borrow-out outputs.

---

**2. How many inputs and outputs does a Full Subtractor have?**

**Answer:**

A Full Subtractor has **3 inputs (A, B, Bin)** and **2 outputs (Difference and Borrow-out).**

---

**3. What is the Boolean expression for the Difference output?**

**Answer:**

**D = A ⊕ B ⊕ Bin**

---

**4. What is the Boolean expression for the Borrow-out output?**

**Answer:**

**Bout = A̅B + A̅Bin + BBin**

---

**5. What is the difference between a Half Subtractor and a Full Subtractor?**

**Answer:**

A Half Subtractor subtracts **two** binary inputs and does not have a Borrow-in input, whereas a Full Subtractor subtracts **three** inputs, including Borrow-in.

---

**6. How can a Full Subtractor be implemented?**

**Answer:**

A Full Subtractor can be implemented using **two Half Subtractors and one OR gate**.

---

**7. Mention four applications of a Full Subtractor.**

**Answer:**

- Arithmetic Logic Units (ALUs).
- Ripple Borrow Subtractors.
- Computer Processors.
- FPGA Design.

---

**8. Why is the Borrow-out important in a Full Subtractor?**

**Answer:**

Borrow-out is used as the Borrow-in for the next Full Subtractor during multi-bit binary subtraction.

---

* **Quick Revision**
  - Circuit Type → Combinational Logic
  - Inputs → A, B, Bin
  - Outputs → Difference (D), Borrow-out (Bout)
  - Difference Equation → **D = A ⊕ B ⊕ Bin**
  - Borrow Equation → **Bout = A̅B + A̅Bin + BBin**
  - Built Using → Two Half Subtractors + One OR Gate

---

* **Summary**

A Full Subtractor is a combinational logic circuit that subtracts two one-bit binary inputs (**A** and **B**) along with a **Borrow-in (Bin)** input and produces **Difference** and **Borrow-out** outputs. It is a key building block of multi-bit subtractors, Arithmetic Logic Units (ALUs), processors, and digital systems. Compared to a Half Subtractor, it supports a Borrow-in input, making it suitable for cascading and performing large binary subtraction operations.

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

![Full Subtractor Timing Waveform](Image/full_subtractor_waveform.png)
