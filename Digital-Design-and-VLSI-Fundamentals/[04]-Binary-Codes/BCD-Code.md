# Binary Codes

## Definition

A **Binary Code** is a method of representing numbers, letters, or symbols using only two binary digits:

- `0` = LOW / OFF
- `1` = HIGH / ON

Binary codes are used in digital electronics, computers, communication systems, and VLSI circuits because digital hardware understands only binary values.

---

# Classification of Binary Codes

```
Binary Codes
│
├── Numeric Codes
│   ├── Weighted Codes
│   ├── Non-Weighted Codes
│   ├── Sequential (Cyclic) Codes
│   ├── Self-Complementing Codes
│   └── Error Detection & Error Correction Codes
│
└── Alphanumeric Codes
```

---

# 1. Numeric Codes

## Definition

Numeric codes are binary codes used to represent **decimal numbers (0–9)**.

### Examples
- BCD (8421)
- Excess-3
- Gray Code

---

# A. Weighted Codes

## Definition

A **Weighted Code** is a binary code in which each bit position has a fixed weight.

The decimal value is obtained by adding the weights of all bits that are `1`.

### Examples
- 8421 BCD
- 2421 Code
- 5211 Code

---

## 8421 BCD Truth Table

| Decimal | Binary (8421 BCD) |
|---------:|:-----------------:|
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
| 8 | 1000 |
| 9 | 1001 |

---

# B. Non-Weighted Codes

## Definition

A **Non-Weighted Code** does not assign fixed weights to its bit positions.

The decimal value cannot be obtained by simply adding bit weights.

### Examples
- Gray Code
- Excess-3 Code

---

## Excess-3 Truth Table

| Decimal | Excess-3 Code |
|---------:|:-------------:|
| 0 | 0011 |
| 1 | 0100 |
| 2 | 0101 |
| 3 | 0110 |
| 4 | 0111 |
| 5 | 1000 |
| 6 | 1001 |
| 7 | 1010 |
| 8 | 1011 |
| 9 | 1100 |

---

# C. Sequential (Cyclic) Code

## Definition

A **Sequential (Cyclic) Code** is a binary code in which **only one bit changes between two consecutive numbers**.

This reduces transition errors in digital systems.

### Example
Gray Code

---

## Gray Code Truth Table

| Decimal | Gray Code |
|---------:|:---------:|
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0011 |
| 3 | 0010 |
| 4 | 0110 |
| 5 | 0111 |
| 6 | 0101 |
| 7 | 0100 |
| 8 | 1100 |
| 9 | 1101 |

---

# D. Self-Complementing Codes

## Definition

A **Self-Complementing Code** is a code in which the **9's complement** of a decimal number can be obtained simply by complementing all the bits.

### Examples
- Excess-3 Code
- 2421 Code

---

## Example

| Decimal | Excess-3 |
|---------:|:--------:|
| 2 | 0101 |
| 7 | 1010 |

Notice that:

```
0101 → 1010
```

Both are complements of each other.

---

# E. Error Detection and Error Correction Codes

## Definition

These codes help detect and correct errors that occur during data transmission or storage.

---

## Error Detection Code

### Definition

An **Error Detection Code** detects whether an error has occurred during data transmission.

### Example
Parity Code

---

### Even Parity Truth Table

| Data | Parity Bit | Transmitted Code |
|:----:|:----------:|:----------------:|
| 000 | 0 | 0000 |
| 001 | 1 | 0011 |
| 010 | 1 | 0101 |
| 011 | 0 | 0110 |
| 100 | 1 | 1001 |
| 101 | 0 | 1010 |
| 110 | 0 | 1100 |
| 111 | 1 | 1111 |

---

## Error Correction Code

### Definition

An **Error Correction Code** not only detects errors but also corrects them automatically.

### Example
- Hamming Code
- Reed-Solomon Code

Hamming Code can detect and correct a **single-bit error**.

---

# 2. Alphanumeric Codes

## Definition

Alphanumeric codes represent:

- Letters (A–Z)
- Numbers (0–9)
- Symbols
- Special characters

These codes are widely used in computers and communication systems.

---

## Examples

- ASCII
- Unicode
- EBCDIC

---

## ASCII Examples

| Character | ASCII (Binary) |
|:---------:|:--------------:|
| A | 01000001 |
| B | 01000010 |
| C | 01000011 |
| 0 | 00110000 |
| 1 | 00110001 |
| 2 | 00110010 |

