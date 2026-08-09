# **Binary to Gray Code**

* **Overview**

**Binary to Gray Code Conversion** is the process of converting a binary number into its equivalent Gray Code representation. Gray Code is a non-weighted code in which two consecutive code values differ by only **one bit**. Binary-to-Gray conversion is commonly implemented using **XOR logic** and is important in digital systems such as counters, rotary encoders, asynchronous FIFOs, and VLSI designs.

---

* **Definition**

Binary to Gray conversion converts an **N-bit Binary number** into an **N-bit Gray Code** using XOR operations between adjacent binary bits.

The **MSB remains unchanged**, while every remaining Gray bit is obtained by XORing two adjacent binary bits.

---

* **Why is Binary to Gray Conversion Needed?**
  - To convert binary values into Gray Code.
  - To reduce errors during transitions between consecutive values.
  - To support rotary encoder applications.
  - To support asynchronous FIFO pointer synchronization.
  - To reduce multi-bit transition problems in digital systems.
  - To implement Gray Code counters.

---

* **Conversion Rule**

For an N-bit binary number:

**Binary = Bₙ₋₁ Bₙ₋₂ ... B₂ B₁ B₀**

The Gray Code is:

**Gₙ₋₁ = Bₙ₋₁**

**Gₙ₋₂ = Bₙ₋₁ ⊕ Bₙ₋₂**

**Gₙ₋₃ = Bₙ₋₂ ⊕ Bₙ₋₃**

**...**

**G₀ = B₁ ⊕ B₀**

Therefore:

**Gray = Binary ⊕ (Binary >> 1)**

---

* **Basic Logic**

For a 4-bit binary number:

**Binary = B₃ B₂ B₁ B₀**

The Gray Code is:

**G₃ = B₃**

**G₂ = B₃ ⊕ B₂**

**G₁ = B₂ ⊕ B₁**

**G₀ = B₁ ⊕ B₀**

Therefore:

**Gray = G₃ G₂ G₁ G₀**

---

* **Logic Circuit**

The conversion can be implemented using:

  - **1 direct connection** for the MSB.
  - **3 XOR gates** for a 4-bit binary input.

Conceptually:

**B₃ ───────────────→ G₃**

**B₃ ──┐**

**     XOR ─────────→ G₂**

**B₂ ──┘**

**B₂ ──┐**

**     XOR ─────────→ G₁**

**B₁ ──┘**

**B₁ ──┐**

**     XOR ─────────→ G₀**

**B₀ ──┘**

---

* **Truth Table**

For a 2-bit Binary to Gray converter:

| Binary | Gray |
|:---:|:---:|
| 00 | 00 |
| 01 | 01 |
| 10 | 11 |
| 11 | 10 |

---

* **4-Bit Binary to Gray Conversion Table**

| Decimal | Binary | Gray |
|---:|:---:|:---:|
| 0 | 0000 | 0000 |
| 1 | 0001 | 0001 |
| 2 | 0010 | 0011 |
| 3 | 0011 | 0010 |
| 4 | 0100 | 0110 |
| 5 | 0101 | 0111 |
| 6 | 0110 | 0101 |
| 7 | 0111 | 0100 |
| 8 | 1000 | 1100 |
| 9 | 1001 | 1101 |
| 10 | 1010 | 1111 |
| 11 | 1011 | 1110 |
| 12 | 1100 | 1010 |
| 13 | 1101 | 1011 |
| 14 | 1110 | 1001 |
| 15 | 1111 | 1000 |

---

* **Step-by-Step Conversion**

Consider:

**Binary = 1011**

Write the binary bits:

**B₃ B₂ B₁ B₀**

**1  0  1  1**

Step 1: Copy the MSB.

**G₃ = B₃ = 1**

Step 2: XOR the first two binary bits.

**G₂ = B₃ ⊕ B₂**

**G₂ = 1 ⊕ 0 = 1**

Step 3: XOR the next two binary bits.

**G₁ = B₂ ⊕ B₁**

**G₁ = 0 ⊕ 1 = 1**

Step 4: XOR the last two binary bits.

**G₀ = B₁ ⊕ B₀**

**G₀ = 1 ⊕ 1 = 0**

Therefore:

**1011₂ = 1110 Gray Code**

---

* **Working Example 1**

Convert:

**Binary = 1101**

Write:

**1 1 0 1**

MSB:

**G₃ = 1**

XOR:

**1 ⊕ 1 = 0**

XOR:

**1 ⊕ 0 = 1**

XOR:

**0 ⊕ 1 = 1**

Therefore:

**1101₂ → 1011 Gray**

---

* **Working Example 2**

Convert:

**Binary = 1001**

MSB:

**G₃ = 1**

Next:

**1 ⊕ 0 = 1**

Next:

**0 ⊕ 0 = 0**

Next:

**0 ⊕ 1 = 1**

Therefore:

**1001₂ → 1101 Gray**

---

* **Working Example 3**

Convert:

**Binary = 0110**

MSB:

**G₃ = 0**

Next:

**0 ⊕ 1 = 1**

Next:

**1 ⊕ 1 = 0**

Next:

**1 ⊕ 0 = 1**

Therefore:

**0110₂ → 0101 Gray**

---

* **XOR Rule Used**

The XOR operation follows:

| A | B | A ⊕ B |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Therefore:

**Same bits → 0**

**Different bits → 1**

This makes Binary-to-Gray conversion very simple using XOR gates.

---

* **General Formula**

The most compact formula for Binary-to-Gray conversion is:

**G = B ⊕ (B >> 1)**

Where:

**B = Binary number**

**G = Gray Code**

**>> 1 = Right shift by one bit**

For example:

**B = 1011**

Right shift:

**B >> 1 = 0101**

Now XOR:

**1011**

**⊕ 0101**

**───────**

**1110**

Therefore:

**Gray = 1110**

---

* **Hardware Implementation**

For an N-bit binary input:

**Binary → XOR Network → Gray**

The MSB is directly connected to the Gray MSB.

Each remaining Gray output uses one XOR gate.

Therefore, for an **N-bit Binary-to-Gray converter**:

**XOR gates required = N − 1**

Example:

**4-bit → 3 XOR gates**

**8-bit → 7 XOR gates**

**16-bit → 15 XOR gates**

---

* **Input & Output Description**

| Signal | Description |
|---|---|
| Binary Input | N-bit binary number |
| Gray Output | N-bit Gray Code |
| MSB | Directly transferred |
| Remaining Bits | Generated using XOR |
| Logic Required | XOR gates |

---

* **Working Principle**

The MSB of the binary number is directly copied to the Gray Code.

For every remaining bit, the current binary bit is XORed with the binary bit immediately to its left.

Therefore:

**Binary MSB → Gray MSB**

**Adjacent Binary Bits → XOR → Gray Bit**

This produces a Gray Code sequence where consecutive values differ by only one bit.

---

* **Binary vs Gray Transition**

Consider a binary counter:

**01 → 10**

Two bits change simultaneously.

In Gray Code:

**01 → 11**

Only one bit changes.

Therefore, Gray Code can reduce transition ambiguity in systems where multiple binary bits changing simultaneously can cause problems.

---

* **Applications**

  *Binary-to-Gray conversion is used in:*

  - Rotary Encoders.
  - Position Encoders.
  - Digital Counters.
  - Gray Code Counters.
  - Asynchronous FIFO.
  - Clock Domain Crossing.
  - Analog-to-Digital Converters.
  - FPGA Designs.
  - ASIC Designs.
  - VLSI Systems.
  - Digital Communication Systems.

---

* **Advantages**
  - Simple XOR-based implementation.
  - Requires only N−1 XOR gates for N-bit input.
  - Reduces multi-bit transition problems.
  - Easy to implement in combinational logic.
  - Useful in clock-domain crossing applications.
  - Useful for position and rotation measurement.

---

* **Limitations**
  - Gray Code is not directly suitable for normal arithmetic.
  - Conversion logic is required when binary processing is needed.
  - The main advantage applies to transition-sensitive applications.
  - Additional logic may be required when converting back to binary.

---

* **Real-World Example**

A rotary encoder may use Gray Code to represent the angular position of a rotating shaft.

Suppose the binary position changes from:

**0111 → 1000**

Multiple bits change.

A Gray Code representation changes from:

**0100 → 1100**

Only one bit changes.

This helps reduce errors caused by different signal paths having slightly different propagation delays.

---

* **Synthesizability**

Binary-to-Gray conversion is fully synthesizable in Verilog/SystemVerilog.

It consists only of:

  - XOR operations.
  - Wire connections.
  - Combinational logic.

No clock or storage element is required.

---

* **Common Mistakes**
  - Changing the MSB instead of copying it directly.
  - XORing Gray bits instead of adjacent binary bits during Binary-to-Gray conversion.
  - Forgetting that the MSB is unchanged.
  - Using subtraction instead of XOR.
  - Confusing Binary-to-Gray conversion with Gray-to-Binary conversion.
  - Assuming Gray Code is a weighted code.
  - Assuming Gray Code is intended for arithmetic operations.

---

* **Best Practices**
  - Always copy the binary MSB directly.
  - XOR each pair of adjacent binary bits.
  - Verify the result using the conversion formula.
  - Use XOR gates for hardware implementation.
  - Clearly define input and output widths in RTL.
  - Use Gray Code for applications where transition reliability is important.

---

* **Key Points**
  - Binary-to-Gray conversion is a **combinational logic operation**.
  - The MSB remains unchanged.
  - Every other Gray bit is obtained using XOR.
  - Formula:

**G = B ⊕ (B >> 1)**

  - N-bit Binary-to-Gray converter requires **N−1 XOR gates**.
  - 4-bit converter requires **3 XOR gates**.
  - Gray Code changes only one bit between consecutive values.
  - Common applications include **rotary encoders and asynchronous FIFOs**.

---

* **Interview Questions**

**1. How do you convert Binary to Gray Code?**

**Answer:**

Copy the MSB directly and XOR every pair of adjacent binary bits.

---

**2. What is the formula for Binary-to-Gray conversion?**

**Answer:**

**G = B ⊕ (B >> 1)**

---

**3. Convert 1011 Binary to Gray Code.**

**Answer:**

**MSB = 1**

**1 ⊕ 0 = 1**

**0 ⊕ 1 = 1**

**1 ⊕ 1 = 0**

Therefore:

**1011 → 1110**

---

**4. How many XOR gates are required for an N-bit Binary-to-Gray converter?**

**Answer:**

**N − 1 XOR gates**

The MSB does not require an XOR gate.

---

**5. How many XOR gates are required for a 4-bit Binary-to-Gray converter?**

**Answer:**

**4 − 1 = 3 XOR gates**

---

**6. Is Binary-to-Gray conversion combinational or sequential?**

**Answer:**

It is **combinational logic** because the output depends only on the current binary input and does not require a clock or memory.

---

**7. Why is Gray Code preferred in rotary encoders?**

**Answer:**

Because only one bit changes between adjacent Gray Code values, reducing errors during transitions.

---

**8. Why is Gray Code used in asynchronous FIFO?**

**Answer:**

Gray-coded pointers reduce ambiguity when pointer information crosses between different clock domains because only one bit changes between consecutive pointer values.

---

**9. What logic gate is mainly used for Binary-to-Gray conversion?**

**Answer:**

The **XOR gate** is mainly used.

---

**10. Does the MSB change during Binary-to-Gray conversion?**

**Answer:**

No. The Gray Code MSB is directly equal to the Binary Code MSB.

---

* **Quick Revision**
  - Main Topic → **Binary Codes**
  - Subtopic → **Binary to Gray Code**
  - Type → **Combinational Logic**
  - Main Gate → **XOR**
  - MSB → **Same as Binary MSB**
  - Remaining Bits → **Adjacent Binary XOR**
  - Formula → **G = B ⊕ (B >> 1)**
  - N-bit XOR Gates → **N − 1**
  - 4-bit XOR Gates → **3**
  - Main Property → **One-Bit Transition**
  - Main Applications → **Encoder, FIFO, CDC, Counter**

---

* **Summary**

**Binary-to-Gray conversion** converts an N-bit binary number into its equivalent Gray Code using XOR operations. The MSB is copied directly, while every remaining Gray bit is obtained by XORing two adjacent binary bits. The conversion is simple, fully combinational, and requires **N−1 XOR gates** for an N-bit input. It is particularly important in **rotary encoders, asynchronous FIFOs, clock-domain crossing, counters, FPGA, ASIC, and VLSI designs**.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
