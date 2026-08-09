# **Gray Code**

* **Overview**

**Gray Code** is a binary coding system in which two consecutive code values differ by only **one bit**. It is also known as the **Reflected Binary Code (RBC)** and is widely used in digital systems where minimizing errors during transitions is important.

---

* **Definition**

**Gray Code** is a non-weighted binary code in which adjacent code words differ by exactly **one bit**. This property helps reduce errors during transitions between consecutive values.

---

* **Why is Gray Code Needed?**
  - To minimize errors during transitions.
  - To reduce ambiguity when multiple bits change simultaneously.
  - To improve reliability in position and rotation measurement systems.
  - To simplify certain digital communication and encoding applications.
  - To improve the accuracy of digital systems involving changing binary values.

---

* **Characteristics**
  - It is a **non-weighted code**.
  - Consecutive Gray Code values differ by only **one bit**.
  - It is also called **Reflected Binary Code**.
  - It is not normally used for direct arithmetic operations.
  - It is useful in systems involving position, rotation, and state transitions.
  - An N-bit Gray Code contains **2ⁿ unique code words**.

---

* **Gray Code Table**

The standard 4-bit Gray Code sequence is:

| Decimal | Binary | Gray Code |
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

* **One-Bit Change Property**

The most important property of Gray Code is that consecutive values differ by exactly **one bit**.

Example:

**0000 → 0001**

Only one bit changes.

**0001 → 0011**

Only one bit changes.

**0011 → 0010**

Only one bit changes.

**0010 → 0110**

Only one bit changes.

Therefore, the transition between consecutive Gray Code values is less likely to produce ambiguity caused by different bits changing at slightly different times.

---

* **Binary to Gray Code Conversion**

To convert Binary to Gray Code:

**1. The MSB of the Gray Code is the same as the MSB of the Binary number.**

**2. Each following Gray bit is obtained by XORing two adjacent Binary bits.**

For a 4-bit binary number:

**Binary = B₃ B₂ B₁ B₀**

Gray Code:

**G₃ = B₃**

**G₂ = B₃ ⊕ B₂**

**G₁ = B₂ ⊕ B₁**

**G₀ = B₁ ⊕ B₀**

Therefore:

**G = B ⊕ (B >> 1)**

---

* **Binary to Gray Code Example**

Convert:

**Binary = 1011**

Step 1:

The MSB remains unchanged:

**G₃ = 1**

Step 2:

**1 ⊕ 0 = 1**

Step 3:

**0 ⊕ 1 = 1**

Step 4:

**1 ⊕ 1 = 0**

Therefore:

**1011₂ → 1110 Gray Code**

---

* **Binary to Gray Conversion Table**

For:

**Binary = 1011**

| Position | Operation | Gray Bit |
|---|---|---:|
| MSB | 1 | 1 |
| Next | 1 ⊕ 0 | 1 |
| Next | 0 ⊕ 1 | 1 |
| LSB | 1 ⊕ 1 | 0 |

Therefore:

**Gray Code = 1110**

---

* **Gray to Binary Conversion**

To convert Gray Code to Binary:

**1. The MSB of Binary is the same as the MSB of Gray Code.**

**2. Each next Binary bit is obtained by XORing the previous Binary bit with the current Gray bit.**

For a 4-bit Gray Code:

**Gray = G₃ G₂ G₁ G₀**

Binary:

**B₃ = G₃**

**B₂ = B₃ ⊕ G₂**

**B₁ = B₂ ⊕ G₁**

**B₀ = B₁ ⊕ G₀**

---

* **Gray to Binary Example**

Convert:

**Gray Code = 1110**

Step 1:

**B₃ = G₃ = 1**

Step 2:

**B₂ = B₃ ⊕ G₂**

**B₂ = 1 ⊕ 1 = 0**

Step 3:

**B₁ = B₂ ⊕ G₁**

**B₁ = 0 ⊕ 1 = 1**

Step 4:

**B₀ = B₁ ⊕ G₀**

**B₀ = 1 ⊕ 0 = 1**

Therefore:

**1110 Gray Code → 1011₂**

---

* **Gray Code Generation**

Gray Code can be generated using the **reflection method**.

For 1-bit Gray Code:

**0**

**1**

For 2-bit Gray Code:

Start with:

**0, 1**

Reflect the sequence:

**1, 0**

Prefix **0** to the original sequence:

**00**

**01**

Prefix **1** to the reflected sequence:

**11**

**10**

Therefore:

**2-bit Gray Code:**

**00, 01, 11, 10**

---

* **4-Bit Gray Code Generation**

The 4-bit Gray Code sequence is:

**0000**

**0001**

**0011**

**0010**

**0110**

**0111**

**0101**

**0100**

**1100**

**1101**

**1111**

**1110**

**1010**

**1011**

**1001**

**1000**

Notice that every consecutive code differs by only one bit.

---

* **Gray Code and Binary Comparison**

| Feature | Binary Code | Gray Code |
|---|---|---|
| Type | Weighted positional representation | Non-weighted code |
| Consecutive values | Multiple bits may change | Only one bit changes |
| Arithmetic operations | Easy | Not directly suitable |
| Transition errors | Higher possibility | Reduced |
| Main purpose | General computation | Reliable transitions |
| Common applications | Processors, ALUs | Encoders, counters, ADCs |

---

* **Gray Code vs BCD**

| Feature | Gray Code | BCD |
|---|---|---|
| Full Form | Reflected Binary Code | Binary-Coded Decimal |
| Type | Non-weighted | Weighted |
| Main Property | One-bit transition | Each decimal digit uses 4 bits |
| Arithmetic | Not directly suitable | Decimal arithmetic possible |
| Main Use | Position and transition encoding | Decimal representation and display |
| Valid 4-bit Codes | All 16 combinations | 10 combinations |
| Main Application | Rotary encoders | Digital displays and calculators |

---

* **Gray Code in Digital Counters**

Gray Code can be used in counters where only one bit changes between consecutive states.

Example:

Binary Counter:

**00 → 01 → 10 → 11**

The transition:

**01 → 10**

changes two bits simultaneously.

Gray Counter:

**00 → 01 → 11 → 10**

Every transition changes only one bit.

This can reduce transition-related errors in certain digital systems.

---

* **Gray Code in Rotary Encoders**

Rotary encoders are commonly associated with Gray Code because the encoder output changes as the shaft rotates.

If multiple binary bits change at nearly the same time, temporary incorrect values can occur because of propagation delays.

Gray Code reduces this problem because only one bit changes between adjacent positions.

---

* **Gray Code in Asynchronous FIFO**

Gray Code is commonly used in **asynchronous FIFO** designs for transferring pointer information between different clock domains.

The pointer is converted from binary to Gray Code before crossing the clock-domain boundary.

Since only one bit changes between adjacent Gray Code values, synchronization becomes safer and reduces the possibility of ambiguous multi-bit transitions.

---

* **Gray Code in ADC**

Gray Code can be used in certain **Analog-to-Digital Converter** architectures and encoding systems where reducing transition errors is important.

The one-bit transition property can help reduce errors caused by simultaneous changes in multiple bits.

---

* **Applications**

  *Gray Code is used in:*

  - Rotary Encoders.
  - Position Encoders.
  - Shaft Encoders.
  - Asynchronous FIFO.
  - Clock Domain Crossing circuits.
  - Digital Counters.
  - Analog-to-Digital Converters.
  - Karnaugh Maps.
  - Communication and encoding systems.
  - FPGA Design.
  - ASIC Design.
  - RTL Design.
  - VLSI Systems.

---

* **Advantages**
  - Only one bit changes between consecutive values.
  - Reduces transition-related errors.
  - Reduces ambiguity during state transitions.
  - Useful for position and rotation measurement.
  - Useful in clock-domain crossing applications.
  - Easy to convert between Binary and Gray Code using XOR gates.

---

* **Limitations**
  - Not directly suitable for normal arithmetic operations.
  - Requires conversion for arithmetic processing.
  - Gray Code values are less intuitive than ordinary binary values.
  - Additional conversion logic may be required in digital systems.
  - Its main advantage is limited to applications where transition behavior matters.

---

* **Real-World Example**

A rotary encoder measures the angular position of a rotating shaft.

Suppose consecutive positions are represented using:

**00 → 01 → 11 → 10**

Only one bit changes at every transition.

If the encoder moves from:

**01 → 11**

only one bit changes.

This reduces the possibility of reading an incorrect intermediate value caused by different signal paths changing at slightly different times.

---

* **Key Points**
  - Gray Code is a **non-weighted binary code**.
  - It is also called **Reflected Binary Code**.
  - Consecutive Gray Code values differ by exactly **one bit**.
  - An N-bit Gray Code contains **2ⁿ unique code words**.
  - Binary-to-Gray conversion uses XOR operations.
  - Gray-to-Binary conversion also uses XOR operations.
  - Gray Code is not normally used for arithmetic operations.
  - It is useful for reducing transition errors.
  - It is widely used in rotary encoders.
  - It is important in asynchronous FIFO pointer synchronization.
  - It is useful in ADCs, counters, FPGA, ASIC, and VLSI systems.

---

* **Interview Questions**

**1. What is Gray Code?**

**Answer:**

Gray Code is a non-weighted binary code in which consecutive code words differ by exactly one bit.

---

**2. Why is Gray Code called a Reflected Binary Code?**

**Answer:**

It is called Reflected Binary Code because higher-order Gray Code sequences can be generated by reflecting the existing sequence and prefixing appropriate bits.

---

**3. What is the main advantage of Gray Code?**

**Answer:**

The main advantage is that only one bit changes between consecutive code values, which reduces transition-related errors.

---

**4. What is the difference between Binary and Gray Code?**

**Answer:**

In ordinary binary, multiple bits may change when moving between consecutive values. In Gray Code, only one bit changes between consecutive values.

---

**5. How do you convert Binary to Gray Code?**

**Answer:**

The MSB remains unchanged, and each following Gray bit is obtained by XORing two adjacent Binary bits.

The formula is:

**G = B ⊕ (B >> 1)**

---

**6. How do you convert Gray Code to Binary?**

**Answer:**

The MSB remains unchanged. Each following Binary bit is obtained by XORing the previous Binary bit with the current Gray Code bit.

---

**7. Convert Binary 1011 to Gray Code.**

**Answer:**

**G₃ = 1**

**G₂ = 1 ⊕ 0 = 1**

**G₁ = 0 ⊕ 1 = 1**

**G₀ = 1 ⊕ 1 = 0**

Therefore:

**1011₂ → 1110 Gray Code**

---

**8. Convert Gray Code 1110 to Binary.**

**Answer:**

**B₃ = 1**

**B₂ = 1 ⊕ 1 = 0**

**B₁ = 0 ⊕ 1 = 1**

**B₀ = 1 ⊕ 0 = 1**

Therefore:

**1110 Gray Code → 1011₂**

---

**9. Why is Gray Code used in rotary encoders?**

**Answer:**

Gray Code is used because only one bit changes between adjacent positions. This reduces errors caused by simultaneous changes in multiple bits.

---

**10. Why is Gray Code used in asynchronous FIFO?**

**Answer:**

Gray Code is used for FIFO pointers crossing clock domains because only one pointer bit changes at a time, making synchronization safer and reducing ambiguity during transitions.

---

**11. Is Gray Code suitable for arithmetic operations?**

**Answer:**

No. Gray Code is not normally used directly for arithmetic operations. It is generally converted to binary before performing arithmetic.

---

**12. How many unique values can an N-bit Gray Code represent?**

**Answer:**

An N-bit Gray Code can represent:

**2ⁿ unique values**

For example:

**4-bit Gray Code → 2⁴ = 16 values**

---

**13. What is the main property of consecutive Gray Code values?**

**Answer:**

Consecutive Gray Code values differ by exactly **one bit**.

---

**14. Where is Gray Code used?**

**Answer:**

Gray Code is used in rotary encoders, position sensors, asynchronous FIFOs, clock-domain crossing circuits, ADCs, counters, FPGA, ASIC, and VLSI systems.

---

* **Quick Revision**
  - Main Topic → **Binary Codes**
  - Subtopic → **Gray Code**
  - Alternative Name → **Reflected Binary Code**
  - Type → **Non-Weighted Code**
  - Main Property → **One-Bit Change**
  - N-bit Values → **2ⁿ**
  - Binary → Gray → **XOR**
  - Gray → Binary → **XOR**
  - Arithmetic → **Not Directly Suitable**
  - Main Application → **Rotary Encoder**
  - VLSI Application → **Asynchronous FIFO**
  - Main Advantage → **Reduced Transition Errors**

---

* **Summary**

**Gray Code** is a non-weighted binary code in which consecutive code words differ by exactly one bit. This one-bit transition property makes Gray Code useful in applications where multiple simultaneous bit changes could cause errors. It is widely used in **rotary encoders, position sensors, asynchronous FIFOs, ADCs, counters, FPGA, ASIC, and VLSI systems**. Binary-to-Gray and Gray-to-Binary conversions can be efficiently implemented using XOR operations.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
