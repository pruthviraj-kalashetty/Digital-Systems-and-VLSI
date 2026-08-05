# NMOS (N-Channel Metal-Oxide-Semiconductor)

## 📖 What is NMOS?

**NMOS (N-Channel MOSFET)** is a type of MOSFET used as an **electronic switch**.

It turns **ON** when a **HIGH voltage (Logic 1)** is applied to its **Gate** terminal and turns **OFF** when the gate is **LOW (Logic 0)**.

**Simple Definition:**

> **NMOS is a voltage-controlled electronic switch that turns ON with a HIGH gate voltage and allows current to flow.**

---

# Full Form

**NMOS = N-Channel Metal-Oxide-Semiconductor**

| Word | Meaning |
|------|---------|
| N | N-Type channel (electrons are the charge carriers) |
| MOS | Metal-Oxide-Semiconductor |
| FET | Field-Effect Transistor |

---

# Why is it called N-Channel?

The current flows through an **N-type channel** that is created when the gate voltage is HIGH.

The main charge carriers are **electrons**.

Since electrons move very quickly, **NMOS is faster than PMOS**.

---

# NMOS Symbol

NMOS has four terminals.

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

# NMOS Terminals

## 1. Gate (G)

- Controls the NMOS.
- Applying voltage here turns the NMOS ON or OFF.
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

# How Does NMOS Work?

Think of NMOS as a switch.

## Gate = LOW (0)

```text
Gate = 0V

NMOS = OFF

No Current Flow
```

The switch is **OPEN**.

---

## Gate = HIGH (1)

```text
Gate = HIGH

NMOS = ON

Current Flows
```

The switch is **CLOSED**.

---

# Truth Table

| Gate Input | NMOS State |
|------------|------------|
| 0 | OFF |
| 1 | ON |

---

# Water Tap Analogy

Imagine a water pipe.

- Gate = Tap handle
- Current = Water
- NMOS = Valve

### Tap Closed

```text
Gate = LOW

Water Flow = NO
```

---

### Tap Open

```text
Gate = HIGH

Water Flow = YES
```

NMOS works in the same way.

---

# Why Does NMOS Turn ON?

When a HIGH voltage is applied to the gate:

- An electric field is created.
- An **N-type channel** forms between the drain and source.
- Electrons move through this channel.
- Current can flow.

When the gate voltage is LOW:

- No channel is formed.
- Current cannot flow.

---

# Why is NMOS Faster than PMOS?

NMOS uses **electrons** to carry current.

Electrons move faster than holes.

Therefore:

- Faster switching
- Better performance
- Higher speed

---

# Where is NMOS Used?

NMOS is used in:

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

# NMOS in a CMOS Inverter

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

The NMOS connects the output to **Ground (0)** when it is ON.

---

# Advantages of NMOS

- Faster switching
- High speed
- Small size
- Easy to manufacture
- Widely used in digital ICs
- Low cost

---

# Disadvantages of NMOS

- Cannot pull the output strongly to HIGH by itself.
- Consumes more power if used alone in logic circuits.
- Usually paired with PMOS to form CMOS circuits.

---

# Applications

NMOS is used in:

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

### 1. What is NMOS?

NMOS is an N-channel MOSFET that turns ON when the gate voltage is HIGH and works as an electronic switch.

---

### 2. What does NMOS stand for?

N-Channel Metal-Oxide-Semiconductor.

---

### 3. When does NMOS turn ON?

When the gate voltage is HIGH (Logic 1).

---

### 4. What is the main charge carrier in NMOS?

Electrons.

---

### 5. Why is NMOS faster than PMOS?

Because electrons move faster than holes.

---

### 6. What is the role of NMOS in CMOS?

NMOS provides the **pull-down path**, connecting the output to **Ground (Logic 0)** when it turns ON.

---

# Quick Revision

- NMOS is a type of MOSFET.
- NMOS is an electronic switch.
- It turns **ON** with **HIGH gate voltage**.
- It turns **OFF** with **LOW gate voltage**.
- It uses **electrons** as charge carriers.
- It is **faster than PMOS**.
- In CMOS, NMOS acts as the **pull-down transistor**.
- NMOS is used in almost every modern digital chip.

---

# Key Takeaway

> **NMOS is a fast, voltage-controlled electronic switch that turns ON with a HIGH gate voltage. In CMOS circuits, it connects the output to Ground (Logic 0), making it an essential building block of digital electronics and VLSI design.**
