# **Clock Frequency and Period**

* **Overview**

Clock frequency and clock period describe the speed of a digital clock.

- **Clock Period** → Time taken for one complete clock cycle.
- **Clock Frequency** → Number of clock cycles occurring per second.

They are inversely related and are fundamental to synchronous ASIC and RTL design.

---

* **Definition**

**Clock Period (T)** is the time between two consecutive identical clock edges, such as two rising edges.

**Clock Frequency (f)** is the number of complete clock cycles occurring in one second.

---

* **Why is it needed?**

An ASIC RTL engineer needs to understand frequency and period because they determine:

- How fast synchronous logic operates.
- The time available for data to travel between registers.
- The target operating speed of a design.
- Basic setup and hold timing relationships.
- The maximum achievable operating frequency.

---

* **Core Concept**

Frequency and period are reciprocals:

**Higher Frequency → Smaller Period → Less Time for Data**

**Lower Frequency → Larger Period → More Time for Data**

Example:

    Clock:
    ____/‾‾‾‾\____/‾‾‾‾\____
        ↑          ↑
      Rising     Rising
       Edge       Edge

        <---- T ---->
         Clock Period

If the period is **10 ns**, the clock frequency is **100 MHz**.

---

* **Timing Diagram**

    Clock:
    ____/‾‾‾‾\____/‾‾‾‾\____
         ↑        ↑
       Rising   Rising
        Edge     Edge

         <------ T ------>

    One complete cycle = One Clock Period

The time between two consecutive rising edges is the clock period.

---

* **Important Terms**

- **Clock Period (T)** → Time for one complete clock cycle.
- **Clock Frequency (f)** → Number of cycles per second.
- **Rising Edge** → Clock transition from 0 to 1.
- **Falling Edge** → Clock transition from 1 to 0.
- **MHz** → Million cycles per second.
- **GHz** → Billion cycles per second.
- **ns** → Nanoseconds, commonly used for clock periods.

---

* **Formula**

**f = 1 / T**

**T = 1 / f**

Where:

- **f** = Frequency in Hz.
- **T** = Period in seconds.

Useful conversion:

**1 GHz = 1000 MHz**

**1 MHz = 10⁶ Hz**

**1 ns = 10⁻⁹ s**

For practical VLSI calculations:

**T(ns) = 1000 / f(MHz)**

---

* **Simple Example**

Given:

**Clock Frequency = 100 MHz**

Calculate the period.

**T = 1 / f**

**T = 1 / (100 × 10⁶)**

**T = 10 ns**

Therefore:

- Frequency = **100 MHz**
- Period = **10 ns**

Another example:

If:

**T = 5 ns**

Then:

**f = 1 / 5 ns**

**f = 200 MHz**

---

* **STA Connection**

In STA, the clock period defines the basic time available for data to travel from a launch register to a capture register.

Simplified setup relationship:

**Clock Period ≥ Clock-to-Q + Combinational Delay + Setup Time**

For example:

    Launch FF
       │
       ▼
    Combinational
       Logic
       │
       ▼
    Capture FF

If the clock period is too small for the data to reach the capture register in time, a **setup violation** can occur.

---

* **RTL Relevance**

RTL engineers usually design synchronous logic according to a target clock frequency.

For example:

```text
Target Clock = 500 MHz
Clock Period = 2 ns
