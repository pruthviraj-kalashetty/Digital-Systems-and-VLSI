# **De Morgan's Theorem**

* **Overview**

**De Morgan's Theorems** are fundamental rules of Boolean Algebra used to transform and simplify Boolean expressions. They describe how complementation interacts with **AND** and **OR** operations and are especially important in digital logic, CMOS design, logic gate conversion, and VLSI.

---

* **Definition**

De Morgan's Theorems state that the complement of an **AND** operation is equivalent to the **OR** of the individual complements, while the complement of an **OR** operation is equivalent to the **AND** of the individual complements.

There are two De Morgan's Theorems:

**(A·B)' = A' + B'**

**(A+B)' = A'·B'**

---

* **Why is De Morgan's Theorem Needed?**
  - To simplify Boolean expressions.
  - To transform Boolean expressions.
  - To convert AND logic into OR logic with complemented inputs.
  - To convert OR logic into AND logic with complemented inputs.
  - To implement logic using NAND and NOR gates.
  - To analyze CMOS pull-up and pull-down networks.
  - To optimize digital circuits.
  - To understand active-low logic.
  - To design efficient VLSI circuits.

---

* **The Two De Morgan's Theorems**

### **First De Morgan's Theorem**

The complement of an AND operation is equal to the OR of the complements.

**(A·B)' = A' + B'**

In words:

**NOT (A AND B) = (NOT A) OR (NOT B)**

---

### **Second De Morgan's Theorem**

The complement of an OR operation is equal to the AND of the complements.

**(A+B)' = A'·B'**

In words:

**NOT (A OR B) = (NOT A) AND (NOT B)**

---

* **First De Morgan's Theorem – Truth Table**

Verify:

**(A·B)' = A' + B'**

| A | B | A·B | (A·B)' | A' | B' | A'+B' |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 1 | 1 | 1 | 1 |
| 0 | 1 | 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 | 1 | 1 |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 |

Since:

**(A·B)' = A'+B'**

the theorem is verified.

---

* **Second De Morgan's Theorem – Truth Table**

Verify:

**(A+B)' = A'·B'**

| A | B | A+B | (A+B)' | A' | B' | A'·B' |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 0 | 0 | 0 | 1 | 1 | 1 | 1 |
| 0 | 1 | 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 1 | 0 | 0 | 1 | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 |

Since:

**(A+B)' = A'·B'**

the theorem is verified.

---

* **De Morgan's Theorem Rules**

When applying De Morgan's Theorem:

**1. Complement the entire expression.**

**2. Change AND ↔ OR.**

**3. Complement every individual variable.**

Therefore:

**AND → OR**

**OR → AND**

**0 → 1**

**1 → 0**

**A → A'**

---

* **Basic Transformation**

### AND to OR

Starting expression:

**(AB)'**

Apply De Morgan's Theorem:

**(AB)' = A'+B'**

Therefore:

**AND + NOT → OR + NOT inputs**

---

### OR to AND

Starting expression:

**(A+B)'**

Apply De Morgan's Theorem:

**(A+B)' = A'B'**

Therefore:

**OR + NOT → AND + NOT inputs**

---

* **Example 1**

Simplify:

**Y = (AB)'**

Using the first De Morgan's Theorem:

**(AB)' = A'+B'**

Therefore:

**Y = A'+B'**

---

* **Example 2**

Simplify:

**Y = (A+B)'**

Using the second De Morgan's Theorem:

**(A+B)' = A'B'**

Therefore:

**Y = A'B'**

---

* **Example 3**

Simplify:

**Y = (ABC)'**

Treat:

**ABC = A·B·C**

Using De Morgan's Theorem:

**(ABC)' = A'+B'+C'**

Therefore:

**Y = A'+B'+C'**

---

* **Example 4**

Simplify:

**Y = (A+B+C)'**

Using De Morgan's Theorem:

**(A+B+C)' = A'B'C'**

Therefore:

**Y = A'B'C'**

---

* **Example 5**

Simplify:

**Y = (A+BC)'**

First identify the OR operation:

**Y = (A + BC)'**

Apply De Morgan's Theorem:

**Y = A'(BC)'**

Now apply De Morgan's Theorem again:

**(BC)' = B'+C'**

Therefore:

**Y = A'(B'+C')**

---

* **Example 6**

Simplify:

**Y = (AB+C)'**

Apply De Morgan's Theorem:

**Y = (AB)'·C'**

Now:

**(AB)' = A'+B'**

Therefore:

**Y = (A'+B')C'**

---

* **Example 7**

Simplify:

**Y = ((A+B)C)'**

First apply De Morgan's Theorem to the outer operation:

**Y = (A+B)'C'**

Now:

**(A+B)' = A'B'**

Therefore:

**Y = A'B'C'**

---

* **De Morgan's Theorem and Logic Gates**

De Morgan's Theorems explain the relationship between:

**AND + NOT**

and:

**OR + NOT**

For example:

**(AB)' = A'+B'**

This means a **NAND** function can be represented as an OR function with inverted inputs.

Similarly:

**(A+B)' = A'B'**

This means a **NOR** function can be represented as an AND function with inverted inputs.

---

* **NAND Transformation**

NAND function:

**Y = (AB)'**

Using De Morgan's Theorem:

**Y = A'+B'**

Therefore:

**NAND = OR with inverted inputs**

This is useful because NAND is a **universal gate**.

---

* **NOR Transformation**

NOR function:

**Y = (A+B)'**

Using De Morgan's Theorem:

**Y = A'B'**

Therefore:

**NOR = AND with inverted inputs**

NOR is also a **universal gate**.

---

* **De Morgan's Theorem and CMOS**

De Morgan's Theorems are extremely important in CMOS logic design.

CMOS circuits use:

**Pull-Up Network (PUN)**

and:

**Pull-Down Network (PDN)**

The Boolean relationship between these networks can be understood using De Morgan's Theorems.

For example:

**Y = (AB)'**

is a NAND function.

The corresponding CMOS structure uses:

**PMOS → Parallel**

**NMOS → Series**

Similarly:

**Y = (A+B)'**

is a NOR function.

The CMOS structure uses:

**PMOS → Series**

**NMOS → Parallel**

De Morgan's Theorem therefore helps explain the complementary structure of CMOS logic.

---

* **De Morgan's Theorem and Active-Low Logic**

De Morgan's Theorems are also important when working with active-low signals.

For example:

**Y = (A+B)'**

can be written as:

**Y = A'B'**

This allows a logic function to be expressed using active-low inputs and outputs.

Active-low signals are commonly represented using:

**'**

or:

**overbar**

or a signal name such as:

**RESET_N**

---

* **Generalized De Morgan's Theorem**

For multiple variables:

**(A·B·C·D)' = A'+B'+C'+D'**

Similarly:

**(A+B+C+D)' = A'B'C'D'**

The same rule applies regardless of the number of variables.

---

* **De Morgan's Theorem with Constants**

The theorem also applies to Boolean constants.

For example:

**(A·1)'**

Using De Morgan's Theorem:

**A' + 1'**

Since:

**1' = 0**

Therefore:

**A'+0 = A'**

Similarly:

**(A+0)'**

**= A'·0'**

**= A'·1**

**= A'**

---

* **De Morgan's Theorem vs Boolean Complement**

| Feature | De Morgan's Theorem | Complement Law |
|---|---|---|
| Purpose | Transforms expressions | Simplifies complements |
| Main Rule | AND ↔ OR | Variable + complement |
| Example | (AB)'=A'+B' | A+A'=1 |
| Main Use | Expression transformation | Logic simplification |

---

* **Common Mistakes**

  - Forgetting to complement every variable.
  - Changing AND to OR but not complementing the variables.
  - Changing OR to AND but not complementing the variables.
  - Applying De Morgan's Theorem to only part of an expression.
  - Confusing **(AB)'** with **A'B'**.
  - Confusing **(A+B)'** with **A'+B'**.
  - Forgetting that AND and OR must be interchanged.

Remember:

**Complement + Change Operation + Complement Variables**

---

* **Best Practices**
  - Identify the complete complemented expression first.
  - Change every AND to OR.
  - Change every OR to AND.
  - Complement every variable.
  - Apply the theorem step-by-step for complex expressions.
  - Use parentheses to avoid ambiguity.
  - Verify the final result using a truth table when necessary.

---

* **Applications**

  *De Morgan's Theorems are used in:*

  - Boolean Expression Simplification.
  - Logic Gate Conversion.
  - NAND Logic Design.
  - NOR Logic Design.
  - CMOS Logic Design.
  - Pull-Up Network Design.
  - Pull-Down Network Design.
  - Active-Low Logic.
  - Digital Circuit Optimization.
  - RTL Design.
  - FPGA Design.
  - ASIC Design.
  - VLSI Design.

---

* **Advantages**
  - Simplifies Boolean expressions.
  - Enables logic transformation.
  - Helps implement circuits using NAND/NOR gates.
  - Reduces design complexity.
  - Helps understand CMOS complementary networks.
  - Useful for active-low signal design.
  - Supports digital circuit optimization.

---

* **Limitations**
  - It does not automatically produce the minimum possible expression.
  - Complex expressions may require multiple applications.
  - Additional Boolean laws may be required after applying De Morgan's Theorem.
  - Physical timing and transistor-level effects are not represented by the theorem itself.

---

* **Real-World Example**

Consider a circuit where an output should be LOW whenever either input is HIGH.

The expression can be written as:

**Y = (A+B)'**

Using De Morgan's Theorem:

**Y = A'B'**

This means the output is HIGH only when:

**A = 0**

and:

**B = 0**

This behavior is directly implemented by a **NOR gate** and is commonly used in digital control and CMOS logic.

---

* **Key Points**
  - There are **two De Morgan's Theorems**.
  - First theorem:

**(AB)' = A'+B'**

  - Second theorem:

**(A+B)' = A'B'**

  - AND changes to OR.
  - OR changes to AND.
  - Every variable is complemented.
  - NAND can be represented as OR with inverted inputs.
  - NOR can be represented as AND with inverted inputs.
  - De Morgan's Theorems are essential in **Boolean Algebra, CMOS, digital logic, and VLSI design**.

---

* **Interview Questions**

**1. What is De Morgan's Theorem?**

**Answer:**

De Morgan's Theorems are Boolean Algebra rules used to transform complemented AND and OR expressions.

---

**2. State the two De Morgan's Theorems.**

**Answer:**

**(AB)' = A'+B'**

**(A+B)' = A'B'**

---

**3. What happens to AND when De Morgan's Theorem is applied?**

**Answer:**

AND changes to OR, and every variable is complemented.

Example:

**(AB)' = A'+B'**

---

**4. What happens to OR when De Morgan's Theorem is applied?**

**Answer:**

OR changes to AND, and every variable is complemented.

Example:

**(A+B)' = A'B'**

---

**5. Simplify (ABC)'.**

**Answer:**

**(ABC)' = A'+B'+C'**

---

**6. Simplify (A+B+C)'.**

**Answer:**

**(A+B+C)' = A'B'C'**

---

**7. What is the De Morgan equivalent of a NAND gate?**

**Answer:**

A NAND function:

**(AB)'**

is equivalent to:

**A'+B'**

Therefore, NAND is equivalent to an **OR gate with inverted inputs**.

---

**8. What is the De Morgan equivalent of a NOR gate?**

**Answer:**

A NOR function:

**(A+B)'**

is equivalent to:

**A'B'**

Therefore, NOR is equivalent to an **AND gate with inverted inputs**.

---

**9. Why is De Morgan's Theorem important in CMOS design?**

**Answer:**

It helps designers understand and transform the Boolean relationships between complementary pull-up and pull-down networks and is fundamental to NAND, NOR, and more complex CMOS logic design.

---

**10. What is the easiest way to remember De Morgan's Theorem?**

**Answer:**

Remember:

**Break the bar → Change the operator → Complement every variable**

Therefore:

**AND ↔ OR**

and:

**A ↔ A'**

---

* **Quick Revision**
  - Main Topic → **Boolean Algebra**
  - Subtopic → **De Morgan's Theorem**
  - Theorem 1 → **(AB)' = A'+B'**
  - Theorem 2 → **(A+B)' = A'B'**
  - AND → **OR**
  - OR → **AND**
  - Variables → **Complemented**
  - NAND → **OR + Inverted Inputs**
  - NOR → **AND + Inverted Inputs**
  - Main Applications → **Digital Logic, CMOS, RTL, ASIC, VLSI**

---

* **Summary**

**De Morgan's Theorems** provide two fundamental Boolean transformations: the complement of an AND becomes the OR of the complements, and the complement of an OR becomes the AND of the complements. They are essential for **Boolean simplification, NAND/NOR logic, CMOS pull-up and pull-down networks, active-low logic, RTL design, and VLSI circuit design**.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
