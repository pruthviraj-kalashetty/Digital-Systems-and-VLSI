# **Excess-3 Code**

* **Overview**

**Excess-3 (XS-3) Code** is a non-weighted decimal code in which each decimal digit is represented by adding **3** to the digit and then converting the result into a 4-bit binary number. It is an important code under **Binary Codes** and is mainly used for decimal representation and decimal arithmetic operations.

---

* **Definition**

**Excess-3 Code** is a 4-bit non-weighted code obtained by adding **3 (0011)** to each decimal digit and then representing the resulting value in binary.

Therefore:

**Excess-3 = Decimal Digit + 3 → 4-bit Binary**

---

* **Why is Excess-3 Code Needed?**
  - To represent decimal digits in a binary-coded form.
  - To simplify certain decimal arithmetic operations.
  - To provide a self-complementing decimal code.
  - To reduce the complexity of some complement-based subtraction operations.
  - To provide an alternative to weighted BCD codes.

---

* **Characteristics**
  - Excess-3 is a **non-weighted code**.
  - Each decimal digit is represented using **4 bits**.
  - It is obtained by adding **3** to each decimal digit.
  - It is also called **XS-3 Code**.
  - It is a **self-complementing code**.
  - It has **10 valid code combinations**.
  - The remaining 6 combinations are invalid for decimal digits.

---

* **Excess-3 Code Table**

| Decimal Digit | Add 3 | Binary Result | Excess-3 Code |
|---:|---:|:---:|:---:|
| 0 | 3 | 0011 | 0011 |
| 1 | 4 | 0100 | 0100 |
| 2 | 5 | 0101 | 0101 |
| 3 | 6 | 0110 | 0110 |
| 4 | 7 | 0111 | 0111 |
| 5 | 8 | 1000 | 1000 |
| 6 | 9 | 1001 | 1001 |
| 7 | 10 | 1010 | 1010 |
| 8 | 11 | 1011 | 1011 |
| 9 | 12 | 1100 | 1100 |

---

* **How Excess-3 Code Works**

The conversion process is simple:

**Step 1:** Take the decimal digit.

**Step 2:** Add **3** to the digit.

**Step 3:** Convert the result into a 4-bit binary number.

For example:

**Decimal digit = 5**

Add 3:

**5 + 3 = 8**

Convert 8 to binary:

**8 = 1000**

Therefore:

**5 → 1000 (Excess-3)**

---

* **Excess-3 Conversion: Decimal to Excess-3**

To convert a decimal number into Excess-3:

**1. Separate the decimal number into individual digits.**

**2. Add 3 to each digit separately.**

**3. Convert each resulting value into 4-bit binary.**

**4. Combine the 4-bit groups.**

---

* **Working Example 1**

Convert:

**5₁₀ → Excess-3**

Add 3:

**5 + 3 = 8**

Binary:

**8 = 1000**

Therefore:

**5₁₀ = 1000 (Excess-3)**

---

* **Working Example 2**

Convert:

**27₁₀ → Excess-3**

Separate the digits:

**2 and 7**

For 2:

**2 + 3 = 5**

**5 = 0101**

For 7:

**7 + 3 = 10**

**10 = 1010**

Therefore:

**27₁₀ = 0101 1010 (Excess-3)**

---

* **Working Example 3**

Convert:

**509₁₀ → Excess-3**

Separate:

**5, 0, 9**

For 5:

**5 + 3 = 8**

**8 = 1000**

For 0:

**0 + 3 = 3**

**3 = 0011**

For 9:

**9 + 3 = 12**

**12 = 1100**

Therefore:

**509₁₀ = 1000 0011 1100 (Excess-3)**

---

* **Excess-3 Conversion: Excess-3 to Decimal**

To convert Excess-3 back to decimal:

**1. Divide the code into 4-bit groups.**

**2. Convert each group into decimal.**

**3. Subtract 3 from each decimal value.**

Therefore:

**Decimal Digit = Binary Value − 3**

---

* **Working Example 4**

Convert:

**1000 (Excess-3) → Decimal**

Binary:

**1000₂ = 8₁₀**

Subtract 3:

**8 − 3 = 5**

Therefore:

**1000 (Excess-3) = 5₁₀**

---

* **Working Example 5**

Convert:

**0101 1010 → Decimal**

First group:

**0101₂ = 5**

**5 − 3 = 2**

Second group:

**1010₂ = 10**

**10 − 3 = 7**

Therefore:

**0101 1010 (Excess-3) = 27₁₀**

---

* **Excess-3 vs BCD**

| Feature | BCD (8421) | Excess-3 |
|---|---|---|
| Type | Weighted | Non-weighted |
| Bits per digit | 4 | 4 |
| Method | Direct binary representation | Add 3 before encoding |
| Weight | 8-4-2-1 | No fixed weights |
| Self-complementing | No | Yes |
| Valid Codes | 10 | 10 |
| Invalid Codes | 6 | 6 |
| Arithmetic | Decimal arithmetic | Useful for complement arithmetic |
| Example for 5 | 0101 | 1000 |

---

* **Excess-3 vs Gray Code**

| Feature | Excess-3 | Gray Code |
|---|---|---|
| Type | Non-weighted | Non-weighted |
| Main Purpose | Decimal digit coding | Minimize transition changes |
| Bits per digit | 4 | Depends on number of states |
| Main Property | Self-complementing | One-bit transition |
| Arithmetic | Can support complement arithmetic | Not directly suitable |
| Example for 5 | 1000 | 0111 |
| Main Applications | Decimal arithmetic and coding | Encoders, counters, FIFO |

---

* **Self-Complementing Property**

One of the most important properties of Excess-3 Code is that it is **self-complementing**.

This means that the **9's complement** of a decimal digit can be obtained by simply complementing all four bits of its Excess-3 representation.

For example:

Decimal:

**2**

Excess-3:

**0101**

Complement all bits:

**1010**

1010 in Excess-3 represents:

**10 − 3 = 7**

And:

**9's complement of 2 = 7**

Therefore, the property works.

---

* **Self-Complementing Example**

Take decimal digit:

**4**

Excess-3 representation:

**0111**

1's complement:

**1000**

Convert 1000:

**1000₂ = 8**

Subtract 3:

**8 − 3 = 5**

Therefore:

**4 → 5**

And:

**9's complement of 4 = 5**

Hence, Excess-3 is self-complementing.

---

* **Why is Excess-3 Self-Complementing?**

For a decimal digit **D**, Excess-3 encoding gives:

**D + 3**

The 1's complement of a 4-bit number **X** is:

**15 − X**

Therefore:

**15 − (D + 3)**

**= 12 − D**

Now subtract 3 to decode:

**12 − D − 3**

**= 9 − D**

The result is the **9's complement** of D.

Therefore, Excess-3 is a self-complementing code.

---

* **Invalid Excess-3 Codes**

The valid Excess-3 codes are:

**0011 to 1100**

These represent decimal digits:

**0 to 9**

The 4-bit combinations outside this range are invalid.

| Code | Decimal Value | Excess-3 Status |
|:---:|---:|:---:|
| 0000 | 0 | Invalid |
| 0001 | 1 | Invalid |
| 0010 | 2 | Invalid |
| 0011 | 3 | Valid → 0 |
| 0100 | 4 | Valid → 1 |
| 0101 | 5 | Valid → 2 |
| 0110 | 6 | Valid → 3 |
| 0111 | 7 | Valid → 4 |
| 1000 | 8 | Valid → 5 |
| 1001 | 9 | Valid → 6 |
| 1010 | 10 | Valid → 7 |
| 1011 | 11 | Valid → 8 |
| 1100 | 12 | Valid → 9 |
| 1101 | 13 | Invalid |
| 1110 | 14 | Invalid |
| 1111 | 15 | Invalid |

---

* **Excess-3 Addition**

Excess-3 addition is different from ordinary binary addition.

After adding two Excess-3 digits, the result requires correction depending on whether a carry is generated.

For two Excess-3 digits:

**If there is no carry, subtract 0011 from the result.**

**If there is a carry, add 0011 to the lower 4-bit result.**

This correction is necessary because each digit is already biased by 3.

---

* **Excess-3 Addition Example**

Consider:

**2 + 3**

Excess-3 representation:

**2 → 0101**

**3 → 0110**

Add:

**0101 + 0110 = 1011**

There is no carry.

Subtract 0011:

**1011 − 0011 = 1000**

**1000** is Excess-3 representation of:

**8 − 3 = 5**

Therefore:

**2 + 3 = 5**

---

* **Applications**

  *Excess-3 Code is used in:*

  - Decimal arithmetic circuits.
  - Digital systems.
  - Decimal counters.
  - Digital displays.
  - Complement-based arithmetic systems.
  - Older computer systems.
  - Digital logic circuits.
  - Code conversion circuits.
  - Educational digital electronics applications.
  - VLSI and ASIC code-conversion logic.

---

* **Advantages**
  - Simple conversion method.
  - Non-weighted decimal code.
  - Self-complementing property.
  - Useful for 9's complement arithmetic.
  - Can simplify certain decimal subtraction operations.
  - Uses only 4 bits per decimal digit.

---

* **Limitations**
  - Requires 4 bits for every decimal digit.
  - Six of the sixteen possible 4-bit combinations are invalid.
  - Additional correction is required during arithmetic.
  - Less commonly used in modern systems than standard binary and Unicode-based representations.
  - Not suitable for general binary arithmetic.

---

* **Real-World Example**

Consider a decimal counter that needs to represent the digit:

**6**

Excess-3 conversion:

**6 + 3 = 9**

Binary representation:

**9 = 1001**

Therefore:

**6 → 1001 (Excess-3)**

If the circuit needs to recover the decimal digit:

**1001₂ = 9**

**9 − 3 = 6**

Therefore:

**1001 → 6**

---

* **Key Points**
  - Excess-3 is also called **XS-3 Code**.
  - It is a **non-weighted code**.
  - Each decimal digit uses **4 bits**.
  - Add **3** to the decimal digit before encoding.
  - Valid codes range from **0011 to 1100**.
  - It has **10 valid codes**.
  - Six 4-bit combinations are invalid.
  - Excess-3 is a **self-complementing code**.
  - Complementing an Excess-3 code gives the 9's complement of the digit.
  - To decode, convert the 4-bit value to decimal and subtract **3**.
  - It is useful in decimal arithmetic and code conversion circuits.

---

* **Interview Questions**

**1. What is Excess-3 Code?**

**Answer:**

Excess-3 is a non-weighted decimal code in which **3 is added to each decimal digit**, and the result is represented using 4-bit binary.

---

**2. Why is it called Excess-3?**

**Answer:**

Because the decimal digit is represented by a binary value that is **3 greater than the original decimal digit**.

---

**3. What is the Excess-3 representation of decimal 5?**

**Answer:**

**5 + 3 = 8**

**8 = 1000**

Therefore:

**5 → 1000**

---

**4. What is the Excess-3 representation of decimal 9?**

**Answer:**

**9 + 3 = 12**

**12 = 1100**

Therefore:

**9 → 1100**

---

**5. Is Excess-3 a weighted code?**

**Answer:**

No. Excess-3 is a **non-weighted code**.

---

**6. Why is Excess-3 called a self-complementing code?**

**Answer:**

Because complementing all four bits of an Excess-3 code produces the Excess-3 representation of the **9's complement** of the original decimal digit.

---

**7. What is the Excess-3 code for decimal 4?**

**Answer:**

**4 + 3 = 7**

**7 = 0111**

Therefore:

**4 → 0111**

---

**8. Convert 1010 Excess-3 to decimal.**

**Answer:**

**1010₂ = 10**

Subtract 3:

**10 − 3 = 7**

Therefore:

**1010 (Excess-3) = 7**

---

**9. What is the difference between BCD and Excess-3?**

**Answer:**

BCD directly represents each decimal digit using its 4-bit binary equivalent, while Excess-3 adds **3** to the decimal digit before converting it to binary.

For decimal 5:

**BCD = 0101**

**Excess-3 = 1000**

---

**10. What is the valid Excess-3 code range?**

**Answer:**

The valid Excess-3 codes range from:

**0011 to 1100**

These represent decimal digits:

**0 to 9**

---

**11. How many invalid codes are present in Excess-3?**

**Answer:**

There are **6 invalid 4-bit combinations** because only 10 of the 16 possible combinations are used.

---

**12. What is the main advantage of Excess-3 Code?**

**Answer:**

Its major advantage is that it is **self-complementing**, which makes it useful for complement-based decimal arithmetic.

---

**13. How do you convert decimal to Excess-3?**

**Answer:**

Add **3** to each decimal digit and convert the result into a 4-bit binary number.

---

**14. How do you convert Excess-3 to decimal?**

**Answer:**

Convert each 4-bit Excess-3 group into decimal and subtract **3**.

---

**15. Where is Excess-3 used?**

**Answer:**

It is used in decimal arithmetic circuits, code converters, digital systems, counters, displays, and certain VLSI/ASIC logic circuits.

---

* **Quick Revision**
  - Main Topic → **Binary Codes**
  - Subtopic → **Excess-3 Code**
  - Alternative Name → **XS-3**
  - Type → **Non-Weighted Code**
  - Bits per Digit → **4**
  - Encoding Rule → **Digit + 3**
  - Decoding Rule → **Binary − 3**
  - Valid Codes → **0011 to 1100**
  - Invalid Codes → **6**
  - Special Property → **Self-Complementing**
  - Complement → **9's Complement**
  - Main Use → **Decimal Arithmetic**
  - Main Advantage → **Simplifies Complement Operations**

---

* **Summary**

**Excess-3 Code** is a 4-bit non-weighted decimal code obtained by adding **3** to every decimal digit before converting it into binary. Its most important property is that it is **self-complementing**, meaning that complementing all bits produces the code for the 9's complement of the original digit. Excess-3 is mainly studied as an important **Binary Code** and is useful in decimal arithmetic, code conversion, counters, displays, and digital logic design.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
