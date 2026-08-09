# **BCD Code**

* **Overview**

**BCD (Binary-Coded Decimal)** is a binary coding system in which each decimal digit is represented separately using a **4-bit binary code**. BCD is an important concept under **Binary Codes** and is widely used in digital displays, calculators, counters, and digital systems that process decimal digits.

---

* **Definition**

**Binary-Coded Decimal (BCD)** is a coding method in which each decimal digit from **0 to 9** is represented by its corresponding **4-bit binary value**.

Unlike ordinary binary representation, BCD encodes **each decimal digit separately**.

---

* **Why is BCD Code Needed?**
  - To represent decimal digits directly in binary form.
  - To simplify decimal display systems.
  - To interface digital circuits with decimal-based devices.
  - To represent decimal numbers without converting the entire number into pure binary.
  - To support digital calculators, counters, and display systems.

---

* **BCD Code Table**

The commonly used BCD code is **8421 BCD**.

| Decimal Digit | BCD Code | 8 | 4 | 2 | 1 |
|---:|:---:|---:|---:|---:|---:|
| 0 | 0000 | 0 | 0 | 0 | 0 |
| 1 | 0001 | 0 | 0 | 0 | 1 |
| 2 | 0010 | 0 | 0 | 1 | 0 |
| 3 | 0011 | 0 | 0 | 1 | 1 |
| 4 | 0100 | 0 | 1 | 0 | 0 |
| 5 | 0101 | 0 | 1 | 0 | 1 |
| 6 | 0110 | 0 | 1 | 1 | 0 |
| 7 | 0111 | 0 | 1 | 1 | 1 |
| 8 | 1000 | 1 | 0 | 0 | 0 |
| 9 | 1001 | 1 | 0 | 0 | 1 |

---

* **BCD Digits**

BCD uses only the following ten 4-bit combinations:

**0000 → 0**

**0001 → 1**

**0010 → 2**

**0011 → 3**

**0100 → 4**

**0101 → 5**

**0110 → 6**

**0111 → 7**

**1000 → 8**

**1001 → 9**

The remaining six 4-bit combinations are invalid in standard 8421 BCD.

---

* **Valid and Invalid BCD Codes**

There are **16 possible combinations** with 4 bits:

**0000 to 1111**

However, standard BCD represents only decimal digits **0 to 9**.

Therefore:

**Valid BCD codes = 0000 to 1001**

**Invalid BCD codes = 1010 to 1111**

| Binary Code | BCD Status |
|:---:|:---:|
| 0000 | Valid |
| 0001 | Valid |
| 0010 | Valid |
| 0011 | Valid |
| 0100 | Valid |
| 0101 | Valid |
| 0110 | Valid |
| 0111 | Valid |
| 1000 | Valid |
| 1001 | Valid |
| 1010 | Invalid |
| 1011 | Invalid |
| 1100 | Invalid |
| 1101 | Invalid |
| 1110 | Invalid |
| 1111 | Invalid |

---

* **Working Principle**

BCD represents every decimal digit independently using four binary bits.

For example:

**Decimal number = 25**

The decimal number contains two digits:

**2 and 5**

Convert each digit separately:

**2 → 0010**

**5 → 0101**

Therefore:

**25₁₀ = 0010 0101 (BCD)**

The digits are not combined into a single pure binary conversion.

---

* **BCD vs Pure Binary**

BCD and ordinary binary representation are different.

Consider the decimal number:

**25₁₀**

In pure binary:

**25₁₀ = 11001₂**

In BCD:

**25₁₀ = 0010 0101**

Therefore:

**Pure Binary → 11001**

**BCD → 0010 0101**

BCD uses **4 bits for every decimal digit**, while pure binary represents the complete number using the minimum required number of bits.

---

* **BCD Conversion: Decimal to BCD**

To convert a decimal number into BCD:

**1. Separate the decimal number into individual digits.**

**2. Convert each decimal digit into its 4-bit BCD representation.**

**3. Combine the 4-bit groups.**

Example:

**Decimal = 59**

Separate the digits:

**5 and 9**

Convert:

**5 → 0101**

**9 → 1001**

Therefore:

**59₁₀ = 0101 1001 (BCD)**

---

* **BCD Conversion: BCD to Decimal**

To convert BCD to decimal:

**1. Divide the BCD number into groups of 4 bits.**

**2. Convert each 4-bit group into its corresponding decimal digit.**

Example:

**BCD = 0011 0111**

Separate:

**0011 → 3**

**0111 → 7**

Therefore:

**0011 0111 (BCD) = 37₁₀**

---

* **Working Example 1**

Convert:

**84₁₀ → BCD**

Separate the digits:

**8 and 4**

Convert:

**8 → 1000**

**4 → 0100**

Therefore:

**84₁₀ = 1000 0100 (BCD)**

---

* **Working Example 2**

Convert:

**306₁₀ → BCD**

Separate the digits:

**3, 0, 6**

Convert:

**3 → 0011**

**0 → 0000**

**6 → 0110**

Therefore:

**306₁₀ = 0011 0000 0110 (BCD)**

---

* **Working Example 3**

Convert:

**729₁₀ → BCD**

Separate the digits:

**7, 2, 9**

Convert:

**7 → 0111**

**2 → 0010**

**9 → 1001**

Therefore:

**729₁₀ = 0111 0010 1001 (BCD)**

---

* **BCD Addition**

BCD addition is different from ordinary binary addition.

Two BCD digits can first be added using binary addition.

If the result is greater than **1001₂ (9)** or if a carry is generated, a correction of:

**0110₂**

must be added.

Therefore:

**BCD Correction = +0110**

---

* **BCD Addition Example**

Consider:

**5 + 4**

BCD representation:

**5 = 0101**

**4 = 0100**

Binary addition:

**0101 + 0100 = 1001**

Since:

**1001 = 9**

The result is a valid BCD digit.

Therefore:

**0101 + 0100 = 1001 (BCD)**

Result:

**9**

---

* **BCD Addition Example with Correction**

Consider:

**7 + 5**

BCD representation:

**7 = 0111**

**5 = 0101**

Binary addition:

**0111 + 0101 = 1100**

But:

**1100 = 12**

The result is greater than 9, so it is an invalid BCD digit.

Add the BCD correction:

**1100 + 0110 = 1 0010**

Therefore:

**7 + 5 = 12**

BCD result:

**0001 0010**

So:

**12₁₀ = 0001 0010 (BCD)**

---

* **BCD Correction Rule**

After adding two BCD digits:

**If the result is greater than 1001₂ or a carry is generated, add 0110₂.**

The correction value is:

**0110₂ = 6₁₀**

This converts the invalid BCD result into a valid BCD representation.

---

* **BCD Subtraction**

BCD subtraction can be performed using methods such as:

  - 9's complement.
  - 10's complement.
  - Binary subtraction with correction.
  - Adder-based complement techniques.

In practical digital systems, complement-based methods are commonly used to simplify decimal arithmetic hardware.

---

* **BCD Code Types**

Common BCD-related codes include:

  - **8421 BCD**
  - **2421 BCD**
  - **5211 BCD**
  - **Excess-3 Code**

Among these, **8421 BCD** is the most commonly introduced and used form of BCD.

---

* **8421 BCD**

The name **8421** comes from the positional weights of the four bits:

**8, 4, 2, 1**

For example:

**0101**

Calculation:

**0×8 + 1×4 + 0×2 + 1×1**

**= 4 + 1**

**= 5**

Therefore:

**0101 = 5 in 8421 BCD**

---

* **BCD Storage Requirement**

BCD requires **4 bits per decimal digit**.

For example:

**Decimal 1234**

contains four decimal digits.

Therefore:

**4 × 4 = 16 bits**

BCD representation:

**0001 0010 0011 0100**

Pure binary representation of 1234 requires fewer bits.

This is one of the main disadvantages of BCD.

---

* **BCD vs Binary**

| Feature | BCD | Pure Binary |
|---|---|---|
| Representation | Each decimal digit separately | Entire number converted to binary |
| Bits per decimal digit | 4 bits | Variable |
| Valid 4-bit combinations | 10 | 16 |
| Invalid combinations | 1010–1111 | None |
| Decimal display | Easy | Requires conversion |
| Storage efficiency | Lower | Higher |
| Arithmetic | More complex | Generally simpler |
| Main use | Decimal-based systems | General digital computation |

---

* **Advantages**
  - Easy to convert between decimal and BCD.
  - Convenient for decimal displays.
  - Useful in calculators and digital meters.
  - Avoids direct conversion of the complete decimal number for display.
  - Each decimal digit can be processed independently.
  - Useful in financial and decimal-oriented applications.

---

* **Limitations**
  - Requires more bits than pure binary.
  - Uses only 10 of the 16 possible 4-bit combinations.
  - BCD arithmetic requires correction logic.
  - Requires more storage for large decimal numbers.
  - Arithmetic operations can be more complex than pure binary arithmetic.

---

* **Applications**

  *BCD Code is used in:*

  - Digital clocks.
  - Digital watches.
  - Calculators.
  - Digital meters.
  - Seven-segment displays.
  - Electronic counters.
  - Digital instruments.
  - Decimal-based processors.
  - Financial and accounting systems.
  - Display interfaces.
  - FPGA and ASIC designs involving decimal data.

---

* **Real-World Example**

A digital clock may need to display the time:

**12:45**

The decimal digits can be represented individually using BCD:

**1 → 0001**

**2 → 0010**

**4 → 0100**

**5 → 0101**

Therefore:

**12:45 → 0001 0010 : 0100 0101**

This makes BCD convenient for driving decimal digit displays.

---

* **Key Points**
  - BCD stands for **Binary-Coded Decimal**.
  - BCD represents each decimal digit separately.
  - Standard BCD uses **4 bits per decimal digit**.
  - **8421 BCD** is the most common BCD representation.
  - Valid BCD codes range from **0000 to 1001**.
  - **1010 to 1111** are invalid in standard BCD.
  - BCD and pure binary are different.
  - BCD is convenient for decimal display systems.
  - BCD requires more storage than pure binary.
  - BCD addition may require **0110 correction**.
  - BCD is widely used in digital clocks, calculators, counters, and display systems.

---

* **Interview Questions**

**1. What is BCD?**

**Answer:**

BCD stands for **Binary-Coded Decimal**. It represents each decimal digit separately using a 4-bit binary code.

---

**2. What is 8421 BCD?**

**Answer:**

8421 BCD is a weighted BCD code whose four bit positions have weights:

**8, 4, 2, 1**

---

**3. How many bits are required to represent one decimal digit in BCD?**

**Answer:**

**4 bits** are required to represent one decimal digit in standard BCD.

---

**4. What are the valid BCD codes?**

**Answer:**

The valid BCD codes are:

**0000 to 1001**

These represent decimal digits:

**0 to 9**

---

**5. Which BCD codes are invalid?**

**Answer:**

The following six combinations are invalid in standard 8421 BCD:

**1010, 1011, 1100, 1101, 1110, 1111**

---

**6. What is the BCD representation of decimal 25?**

**Answer:**

**2 → 0010**

**5 → 0101**

Therefore:

**25₁₀ = 0010 0101 (BCD)**

---

**7. What is the difference between BCD and pure binary?**

**Answer:**

BCD represents each decimal digit separately using 4 bits, while pure binary converts the entire decimal number into a binary representation.

For example:

**25₁₀ = 11001₂**

But:

**25₁₀ = 0010 0101 (BCD)**

---

**8. Why are 1010 to 1111 invalid in BCD?**

**Answer:**

A 4-bit number can represent values from 0 to 15, but a decimal digit can only have values from 0 to 9. Therefore, values 10 to 15 are not valid BCD digit representations.

---

**9. Why is 0110 added during BCD addition?**

**Answer:**

If the binary addition result is greater than 9 or produces a carry, the result is not a valid BCD digit. Adding **0110₂** corrects the result and produces a valid BCD representation.

---

**10. What is the BCD representation of decimal 59?**

**Answer:**

**5 → 0101**

**9 → 1001**

Therefore:

**59₁₀ = 0101 1001 (BCD)**

---

**11. What is the BCD representation of decimal 100?**

**Answer:**

**1 → 0001**

**0 → 0000**

**0 → 0000**

Therefore:

**100₁₀ = 0001 0000 0000 (BCD)**

---

**12. Why does BCD require more bits than pure binary?**

**Answer:**

BCD uses 4 bits for every decimal digit, even though some of the 4-bit combinations are unused. Therefore, BCD requires more storage than pure binary.

---

**13. Where is BCD commonly used?**

**Answer:**

BCD is commonly used in digital clocks, calculators, digital meters, counters, seven-segment displays, and decimal-oriented digital systems.

---

**14. What are the common types of BCD codes?**

**Answer:**

Common BCD-related codes include:

**8421 BCD, 2421 BCD, 5211 BCD, and Excess-3 Code.**

---

* **Quick Revision**
  - Main Topic → **Binary Codes**
  - Subtopic → **BCD Code**
  - Full Form → **Binary-Coded Decimal**
  - Common Type → **8421 BCD**
  - Bits per Digit → **4**
  - Decimal Digits → **0 to 9**
  - Valid Codes → **0000 to 1001**
  - Invalid Codes → **1010 to 1111**
  - Weights → **8, 4, 2, 1**
  - BCD Addition Correction → **0110**
  - Main Advantage → **Easy Decimal Display**
  - Main Limitation → **More Storage Required**
  - Main Applications → **Clock, Calculator, Display, Counter**

---

* **Summary**

**BCD (Binary-Coded Decimal)** is a binary coding technique in which each decimal digit is represented separately using four bits. The most common form is **8421 BCD**, which uses the weights 8, 4, 2, and 1. Only the combinations from **0000 to 1001** are valid because they represent decimal digits 0 through 9. BCD is especially useful in systems that need direct decimal representation and display, although it requires more storage than pure binary.

---

* **References**
  - M. Morris Mano – *Digital Design*.
  - Thomas L. Floyd – *Digital Fundamentals*.
  - Ronald J. Tocci – *Digital Systems: Principles and Applications*.
  - Stephen Brown & Zvonko Vranesic – *Fundamentals of Digital Logic with Verilog Design*.
  - Neso Academy – Digital Electronics.
