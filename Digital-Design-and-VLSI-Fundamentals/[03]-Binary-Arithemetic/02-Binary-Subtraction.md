# **Binary Subtraction**

* **Overview**

**Binary Subtraction** is an arithmetic operation performed on binary numbers using only the digits **0 and 1**. It is an important operation under **Binary Arithmetic** and is widely used in subtractors, ALUs, processors, and digital systems.

---

* **Definition**

**Binary Subtraction** is the process of subtracting one binary number from another using binary subtraction rules and borrow operations.

---

* **Purpose**
  - To perform subtraction on binary numbers.
  - To calculate numerical differences in digital systems.
  - To form the basis of binary subtractor circuits.
  - To support arithmetic operations in ALUs and processors.
  - To provide the foundation for more complex binary arithmetic operations.

---

* **Importance**
  - It is one of the fundamental binary arithmetic operations.
  - It forms the basis of half subtractors and full subtractors.
  - It is used in ALUs and processors.
  - It is essential for understanding digital arithmetic circuits.
  - It is important for RTL, FPGA, ASIC, and VLSI design.

---

* **Binary Subtraction Rules**

Binary subtraction uses four basic rules:

| A | B | Difference | Borrow |
|---|---|---:|---:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |

The important rule is:

**0 − 1 = 1 with Borrow = 1**

The borrow is taken from the next higher bit.

---

* **Working Principle**

Binary subtraction is performed from the **LSB to the MSB**, similar to decimal subtraction.

The basic process is:

**1. Start from the LSB.**

**2. Subtract the corresponding binary bits.**

**3. Include the borrow from the previous position when required.**

**4. Write the Difference bit.**

**5. Generate a Borrow when the upper bit is smaller than the lower bit.**

**6. Continue until all bits have been processed.**

---

* **Circuit Description**

Binary subtraction is implemented using digital arithmetic circuits called **Subtractors**.

The two fundamental subtractors are:

  - **Half Subtractor**
    - Subtracts two binary bits.
    - Produces Difference and Borrow.

  - **Full Subtractor**
    - Subtracts three binary inputs.
    - Inputs are A, B, and Borrow-in.
    - Produces Difference and Borrow-out.

Multiple full subtractors can be connected together to perform multi-bit binary subtraction.

---

* **Boolean Expression**

For a Half Subtractor:

**Difference = A ⊕ B**

**Borrow = A̅.B**

For a Full Subtractor:

**Difference = A ⊕ B ⊕ Bᵢₙ**

**Bₒᵤₜ = A̅.B + A̅.Bᵢₙ + B.Bᵢₙ**

---

* **Input and Output Description**
  - Inputs:-
    - Binary number A.
    - Binary number B.
    - Borrow-in, when required.

  - Outputs:-
    - Difference.
    - Borrow-out.

---

* **Working Example**

Consider:

**1011₂ − 0010₂**

Perform the subtraction from right to left:

```text
      1 0 1 1
    - 0 0 1 0
    ----------
      1 0 0 1
