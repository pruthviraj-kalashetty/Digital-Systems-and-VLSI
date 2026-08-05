# CMOS Inverter

## 📖 Overview

A **CMOS Inverter** is the simplest and most fundamental CMOS logic gate. It is also called a **NOT Gate** because it produces the **opposite (inverted)** output of the input.

A CMOS inverter is built using **one PMOS transistor** and **one NMOS transistor** connected in a complementary way. It is the basic building block of all CMOS digital circuits.

---

# Definition

> **A CMOS Inverter is a logic circuit made using one PMOS transistor and one NMOS transistor that produces the opposite logic value of its input.**

---

# Why is it Needed?

A CMOS inverter is needed because it:

- Performs the NOT operation.
- Generates stable Logic 0 and Logic 1.
- Consumes very low power.
- Provides high switching speed.
- Acts as the basic building block for all CMOS logic gates.

Without the CMOS inverter, complex digital circuits such as NAND, NOR, XOR, processors, and memory chips cannot be built.

---

# Working Principle

A CMOS inverter uses:

- **One PMOS transistor** connected to **VDD**.
- **One NMOS transistor** connected to **GND**.
- Both transistor gates are connected to the same input.
- The output is taken from the connection between the two transistors.

### Input = 0

- PMOS turns **ON**.
- NMOS turns **OFF**.
- Output is connected to **VDD**.
- Output becomes **1 (HIGH)**.

### Input = 1

- PMOS turns **OFF**.
- NMOS turns **ON**.
- Output is connected to **GND**.
- Output becomes **0 (LOW)**.

The output is always the opposite of the input.

---

# Circuit Diagram

```text
              VDD
               │
            ┌─────┐
 Input ─────│ PMOS│
            └─────┘
               │
               ├──────── Output (Y)
               │
            ┌─────┐
 Input ─────│ NMOS│
            └─────┘
               │
              GND
```

---

# Truth Table

| Input (A) | Output (Y) |
|:---------:|:----------:|
| 0 | 1 |
| 1 | 0 |

---

# Boolean Expression

```text
Y = A̅
```

Where:

- **A** = Input
- **Y** = Output

---

# Input & Output Description

| Signal | Description |
|---------|-------------|
| Input (A) | Controls both the PMOS and NMOS transistors. |
| Output (Y) | Produces the inverted value of the input. |
| VDD | Positive power supply (Logic 1). |
| GND | Ground connection (Logic 0). |

---

# Working Example

Suppose the input is **0**.

- PMOS turns ON.
- NMOS turns OFF.
- The output is connected to **VDD**.
- Therefore, the output is **1**.

Now change the input to **1**.

- PMOS turns OFF.
- NMOS turns ON.
- The output is connected to **GND**.
- Therefore, the output is **0**.

This is why the CMOS inverter is also called a **NOT Gate**.

---

# Applications

CMOS inverters are used in:

- NOT Gates
- NAND Gates
- NOR Gates
- Flip-Flops
- Registers
- Counters
- Memory Circuits
- CPUs
- GPUs
- ASICs
- FPGAs
- Microcontrollers

---

# Advantages

- Very low static power consumption.
- High switching speed.
- High noise immunity.
- Simple circuit design.
- High reliability.
- Easy to integrate into complex digital circuits.

---

# Limitations

- Dynamic power consumption increases with switching frequency.
- Delay occurs during switching.
- Sensitive to electrostatic discharge (ESD).

---

# Real-World Example

When you press a key on your keyboard, billions of CMOS inverters inside the processor switch between HIGH and LOW states to process information quickly and efficiently.

---

# Key Points

- CMOS inverter is the simplest CMOS logic gate.
- It is built using **one PMOS** and **one NMOS** transistor.
- PMOS connects the output to **VDD**.
- NMOS connects the output to **GND**.
- Output is always the opposite of the input.
- It is also called a **NOT Gate**.
- It is the basic building block of CMOS digital circuits.

---

# Interview Questions

### 1. What is a CMOS inverter?

A CMOS inverter is a logic circuit that uses one PMOS and one NMOS transistor to produce the opposite of the input.

---

### 2. Why is it called an inverter?

Because it inverts the input logic. A LOW input produces a HIGH output, and a HIGH input produces a LOW output.

---

### 3. Which transistors are used in a CMOS inverter?

One PMOS transistor and one NMOS transistor.

---

### 4. What happens when the input is LOW?

PMOS turns ON, NMOS turns OFF, and the output becomes HIGH.

---

### 5. Why is the CMOS inverter important?

It is the basic building block used to design all CMOS logic gates and modern digital integrated circuits.

---

# Quick Revision

- CMOS inverter = NOT Gate.
- Uses one PMOS and one NMOS transistor.
- Input 0 → Output 1.
- Input 1 → Output 0.
- PMOS pulls the output HIGH.
- NMOS pulls the output LOW.
- Foundation of all CMOS logic circuits.

---

# Summary

A CMOS inverter is the simplest CMOS logic circuit and the foundation of modern digital electronics. It uses one PMOS and one NMOS transistor working in a complementary manner to produce the opposite of the input signal. Because of its low power consumption, high speed, and reliable operation, the CMOS inverter is widely used as the basic building block for digital integrated circuits.

---

# References

1. Neil H. E. Weste & David Harris – *CMOS VLSI Design: A Circuits and Systems Perspective*
2. Jan M. Rabaey – *Digital Integrated Circuits*
3. R. Jacob Baker – *CMOS Circuit Design, Layout, and Simulation*
4. Sedra & Smith – *Microelectronic Circuits*
