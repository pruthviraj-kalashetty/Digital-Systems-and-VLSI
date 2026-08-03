# PMOS (P-Channel Metal-Oxide-Semiconductor)

## 📖 What is PMOS?

**PMOS (P-Channel MOSFET)** is a type of MOSFET used as an **electronic switch**.

It turns **ON** when a **LOW voltage (Logic 0)** is applied to its **Gate** terminal and turns **OFF** when the gate is **HIGH (Logic 1)**.

**Simple Definition:**

> **PMOS is a voltage-controlled electronic switch that turns ON with a LOW gate voltage and allows current to flow.**

---

# Full Form

**PMOS = P-Channel Metal-Oxide-Semiconductor**

| Word | Meaning |
|------|---------|
| P | P-Type channel (holes are the charge carriers) |
| MOS | Metal-Oxide-Semiconductor |
| FET | Field-Effect Transistor |

---

# Why is it called P-Channel?

The current flows through a **P-type channel** that is created when the gate voltage is LOW.

The main charge carriers are **holes**.

Since holes move more slowly than electrons, **PMOS is slower than NMOS**.

---

# PMOS Symbol

PMOS has four terminals.

```text
        Gate (G)
           |
           |
Drain (D)     Source (S)
      \       /
       \_____/
          |
       Body (B)
```

In most digital ICs, the **Body (B)** is internally connected to the **Source (S)**.

So, we usually use only:

- Gate (G)
- Drain (D)
- Source (S)

---

# PMOS Terminals

## 1. Gate (G)

- Controls the PMOS.
- Applying voltage here turns the PMOS ON or OFF.
- Almost no current flows into the gate.

---

## 2. Drain (D)

Current enters or leaves through the drain depending on the circuit.

---

## 3. Source (S)

Current enters or leaves through the source.

---

## 4. Body (B)

Usually connected to the source inside digital ICs.

---

# How Does PMOS Work?

Think of PMOS as a switch.

## Gate = HIGH (1)

```text
Gate = HIGH

PMOS = OFF

No Current Flow
```

The switch is **OPEN**.

---

## Gate = LOW (0)

```text
Gate = LOW

PMOS = ON

Current Flows
```

The switch is **CLOSED**.

---

# Truth Table

| Gate Input | PMOS State |
|------------|------------|
| 0 | ON |
| 1 | OFF |

---

# Water Tap Analogy

Imagine a water pipe.

- Gate = Tap handle
- Current = Water
- PMOS = Valve

### Tap Closed

```text
Gate = HIGH

Water Flow = NO
```

---

### Tap Open

```text
Gate = LOW

Water Flow = YES
```

PMOS works in the same way.

---

# Why Does PMOS Turn ON?

When a LOW voltage is applied to the gate:

- An electric field is created.
- A **P-type channel** forms between the drain and source.
- Holes move through this channel.
- Current can flow.

When the gate voltage is HIGH:

- No channel is formed.
- Current cannot flow.

---

# Why is PMOS Slower than NMOS?

PMOS uses **holes** to carry current.

Holes move more slowly than electrons.

Therefore:

- Lower switching speed
- Lower performance compared to NMOS

---

# Where is PMOS Used?

PMOS is used in:

- CMOS Logic Gates
- NOT Gates
- NAND Gates
- NOR Gates
- Flip-Flops
- Registers
- Counters
- Memories
- CPUs
- GPUs
- ASICs
- FPGAs

---

# PMOS in a CMOS Inverter

A CMOS inverter uses:

- 1 PMOS
- 1 NMOS

```text
      VDD (1)
         |
       PMOS
         |
Input ----+---- Output
         |
       NMOS
         |
      GND (0)
```

### Input = 0

- PMOS = ON
- NMOS = OFF
- Output = 1

### Input = 1

- PMOS = OFF
- NMOS = ON
- Output = 0

The PMOS connects the output to **VDD (Logic 1)** when it is ON.

---

# Advantages of PMOS

- Good at providing a strong Logic 1 (HIGH).
- Low leakage current.
- Essential for CMOS circuits.
- Helps reduce power consumption in digital ICs.

---

# Disadvantages of PMOS

- Slower than NMOS.
- Larger size is often needed to match NMOS performance.
- Cannot pull the output strongly to LOW by itself.

---

# Applications

PMOS is used in:

- Digital Logic Gates
- Microprocessors
- Memory Chips
- Embedded Systems
- ASIC Design
- FPGA Design
- VLSI Chips
- Communication Devices

---

# Interview Questions

### 1. What is PMOS?

PMOS is a P-channel MOSFET that turns ON when the gate voltage is LOW and works as an electronic switch.

---

### 2. What does PMOS stand for?

P-Channel Metal-Oxide-Semiconductor.

---

### 3. When does PMOS turn ON?

When the gate voltage is LOW (Logic 0).

---

### 4. What is the main charge carrier in PMOS?

Holes.

---

### 5. Why is PMOS slower than NMOS?

Because holes move more slowly than electrons.

---

### 6. What is the role of PMOS in CMOS?

PMOS provides the **pull-up path**, connecting the output to **VDD (Logic 1)** when it turns ON.

---

# Quick Revision

- PMOS is a type of MOSFET.
- PMOS is an electronic switch.
- It turns **ON** with **LOW gate voltage**.
- It turns **OFF** with **HIGH gate voltage**.
- It uses **holes** as charge carriers.
- It is **slower than NMOS**.
- In CMOS, PMOS acts as the **pull-up transistor**.
- PMOS is used together with NMOS in almost every modern digital chip.

---

# NMOS vs PMOS

| Feature | NMOS | PMOS |
|---------|------|-------|
| Channel Type | N-Channel | P-Channel |
| Charge Carrier | Electrons | Holes |
| Turns ON | Gate = HIGH (1) | Gate = LOW (0) |
| Turns OFF | Gate = LOW (0) | Gate = HIGH (1) |
| Speed | Faster | Slower |
| Main Role in CMOS | Pull Output to GND (0) | Pull Output to VDD (1) |

---

# Key Takeaway

> **PMOS is a voltage-controlled electronic switch that turns ON with a LOW gate voltage. In CMOS circuits, it connects the output to VDD (Logic 1), making it an essential part of modern digital electronics and VLSI chips.**
