# **Binary Addition**

* **Overview**

**Binary Addition** is an arithmetic operation performed on binary numbers using only the digits **0 and 1**. It is one of the fundamental operations in digital electronics and forms the basis of adders, ALUs, processors, and other digital systems.

---

* **Definition**

**Binary Addition** is the process of adding two or more binary numbers using specific addition rules based on the binary number system.

---

* **Purpose**
  - To perform arithmetic addition on binary numbers.
  - To calculate numerical results inside digital systems.
  - To form the basic operation used in binary adders.
  - To support arithmetic operations in ALUs and processors.
  - To provide the foundation for more complex binary arithmetic operations.

---

* **Importance**
  - It is one of the fundamental binary arithmetic operations.
  - It forms the basis of half adders and full adders.
  - It is used extensively in ALUs and processors.
  - It is essential for understanding digital arithmetic circuits.
  - It is an important concept for RTL, FPGA, ASIC, and VLSI design.

---

* **Binary Addition Rules**

Binary addition uses four basic rules:

| A | B | Sum | Carry |
|---|---|---:|---:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

The most important rule is:

**1 + 1 = 10₂**

Here:

**Sum = 0**

**Carry = 1**

---

* **Working Principle**

Binary addition is performed from the **LSB to the MSB**, similar to decimal addition.

The basic process is:

**1. Start from the LSB.**

**2. Add the corresponding binary bits.**

**3. Include the carry from the previous position.**

**4. Write the Sum bit.**

**5. Transfer the Carry to the next higher position.**

**6. Continue until all bits have been added.**

---

* **Circuit Description**

Binary addition is implemented using digital arithmetic circuits called **Adders**.

The two fundamental adders are:

  - **Half Adder**
    - Adds two binary bits.
    - Produces Sum and Carry.

  - **Full Adder**
    - Adds three binary bits.
    - Inputs are A, B, and Carry-in.
    - Produces Sum and Carry-out.

Multiple full adders can be connected together to perform multi-bit binary addition.

Example:

**4-Bit Binary Addition**

**A₃ A₂ A₁ A₀**

+

**B₃ B₂ B₁ B₀**

↓

**S₃ S₂ S₁ S₀**

with carry propagation between stages.

---

* **Boolean Expression**

For adding two binary bits without an input carry:

**Sum = A ⊕ B**

**Carry = A.B**

For a full adder:

**Sum = A ⊕ B ⊕ Cᵢₙ**

**Cₒᵤₜ = A.B + B.Cᵢₙ + A.Cᵢₙ**

---

* **Input and Output Description**
  - Inputs:-
    - Binary number A.
    - Binary number B.
    - Carry-in, when required.

  - Outputs:-
    - Sum.
    - Carry-out.

---

* **Working Example**

Consider:

**1011₂ + 0110₂**

Perform the addition from right to left:

```text
      1 0 1 1
    + 0 1 1 0
    ----------
    1 0 0 0 1
