# **Clock Skew**

* **Overview**

Clock skew is the difference in the arrival time of the same clock edge at two different sequential elements.

In a synchronous circuit, the clock may reach the launch flip-flop and capture flip-flop at slightly different times.

---

* **Definition**

**Clock Skew** is the difference between the clock arrival time at the capture element and the clock arrival time at the launch element.

**Clock Skew = Capture Clock Arrival Time − Launch Clock Arrival Time**

Types of clock skew:

- **Positive Skew** → Capture clock arrives later than launch clock.
- **Negative Skew** → Capture clock arrives earlier than launch clock.
- **Zero Skew** → Both clock edges arrive at the same time.

---

* **Why is it needed?**

An ASIC RTL engineer needs to understand clock skew because it:

- Affects setup timing.
- Affects hold timing.
- Changes the available timing margin.
- Is considered during Static Timing Analysis (STA).
- Helps explain timing behavior after synthesis and physical implementation.

---

* **Core Concept**

Consider a register-to-register timing path:

    Launch FF                         Capture FF
    ┌─────────┐       Data Path       ┌─────────┐
    │         │──────────────────────►│         │
    │  Launch │                       │ Capture │
    │   FF    │                       │   FF    │
    └─────────┘                       └─────────┘
         ▲                                  ▲
         │                                  │
    Launch Clock                       Capture Clock
         │                                  │
         └──────────── Clock Network ───────┘

The clock can reach the two flip-flops at different times.

Example:

    Launch Clock Arrival  = 0 ns
    Capture Clock Arrival = 0.5 ns

    Clock Skew = 0.5 − 0
              = +0.5 ns

Therefore, the circuit has **+0.5 ns positive clock skew**.

---

* **Timing Diagram**

Positive clock skew:

    Launch Clock:
    ____________/‾‾‾‾‾‾‾‾‾‾\____________
                ↑
            Launch Edge
              0 ns


    Capture Clock:
    ________________/‾‾‾‾‾‾‾‾‾‾\________
                    ↑
                Capture Edge
                  0.5 ns


    Clock Skew = Capture Arrival − Launch Arrival
               = 0.5 ns − 0 ns
               = +0.5 ns

Negative clock skew:

    Capture Clock:
    ____________/‾‾‾‾‾‾‾‾‾‾\____________
                ↑
            Capture Edge
              0 ns


    Launch Clock:
    ________________/‾‾‾‾‾‾‾‾‾‾\________
                    ↑
                Launch Edge
                  0.5 ns


    Clock Skew = 0 − 0.5
               = −0.5 ns

---

* **Important Terms**

- **Clock Skew** → Difference between clock arrival times.
- **Positive Skew** → Capture clock arrives later.
- **Negative Skew** → Capture clock arrives earlier.
- **Zero Skew** → Both clocks arrive at the same time.
- **Launch Clock** → Clock arriving at the launch flip-flop.
- **Capture Clock** → Clock arriving at the capture flip-flop.
- **Clock Arrival Time** → Time at which a clock edge reaches a sequential element.
- **Clock Network** → Network used to distribute the clock to sequential elements.

---

* **Formula**

**Clock Skew = Capture Clock Arrival Time − Launch Clock Arrival Time**

Where:

- **Capture Clock Arrival Time** = Time the clock reaches the capture flip-flop.
- **Launch Clock Arrival Time** = Time the clock reaches the launch flip-flop.

Example:

    Capture Clock Arrival = 2.5 ns
    Launch Clock Arrival  = 2.0 ns

    Clock Skew = 2.5 − 2.0
               = +0.5 ns

Therefore, the skew is **+0.5 ns**.

---

* **Simple Example**

Given:

- Launch clock arrival = **1.0 ns**
- Capture clock arrival = **1.3 ns**

Calculate clock skew:

    Clock Skew = Capture Arrival − Launch Arrival

               = 1.3 − 1.0

               = +0.3 ns

Therefore:

**Clock Skew = +0.3 ns**

The capture clock arrives **0.3 ns later** than the launch clock.

---

* **STA Connection**

Clock skew is directly considered during STA.

A typical register-to-register path is:

    Launch FF
        │
        │ Data Path
        ▼
    Capture FF

The clock reaches both flip-flops through clock paths:

    Clock Source
         │
         ├──────────────► Launch FF
         │
         └──────────────► Capture FF

If the two clock paths have different delays, clock skew occurs.

### Effect on Setup Timing

**Positive skew generally helps setup timing** because the capture clock arrives later.

This provides more time for data to travel from the launch flip-flop to the capture flip-flop.

### Effect on Hold Timing

**Positive skew generally hurts hold timing** because the capture clock arrives later, making the hold requirement harder to satisfy.

Basic relationship:

    Positive Skew → Helps Setup
                  Hurts Hold

    Negative Skew → Hurts Setup
                   Helps Hold

---

* **RTL Relevance**

Clock skew is mainly a physical clock-distribution effect rather than something directly written in RTL.

However, an RTL engineer should understand it because:

- RTL determines the sequential elements and timing paths.
- Register-to-register paths are analyzed using clock arrival times.
- Timing violations can depend on clock skew.
- RTL changes can change the paths that must meet timing.

Important idea:

**The same logical clock does not necessarily arrive at every flip-flop at exactly the same physical time.**

---

* **Common Mistakes**

- Assuming the clock reaches every flip-flop at exactly the same time.
- Thinking positive skew always improves timing.
- Forgetting that positive skew can hurt hold timing.
- Confusing clock skew with clock jitter.
- Treating clock skew as an RTL combinational logic delay.

---

* **Interview Questions**

**1. What is clock skew?**

**Answer:**

Clock skew is the difference between the clock arrival time at the capture element and the clock arrival time at the launch element.

---

**2. What is positive clock skew?**

**Answer:**

Positive clock skew occurs when the capture clock arrives later than the launch clock.

---

**3. What is negative clock skew?**

**Answer:**

Negative clock skew occurs when the capture clock arrives earlier than the launch clock.

---

**4. How does positive clock skew affect setup timing?**

**Answer:**

Positive skew generally helps setup timing because the capture clock arrives later, providing more time for the data to reach the capture flip-flop.

---

**5. How does positive clock skew affect hold timing?**

**Answer:**

Positive skew generally hurts hold timing because the later capture edge makes the minimum-delay requirement more difficult to satisfy.

---

* **Quick Revision**

- **Clock Skew = Capture Clock Arrival − Launch Clock Arrival**
- **Positive Skew → Capture clock arrives later**
- **Negative Skew → Capture clock arrives earlier**
- **Positive Skew → Generally helps Setup**
- **Positive Skew → Generally hurts Hold**
- **Negative Skew → Generally hurts Setup**
- **Negative Skew → Generally helps Hold**
- Clock skew is important in **STA**.
- Clock skew mainly results from differences in clock-path delays.

---

* **Summary**

Clock skew is the difference in clock arrival time between the launch and capture sequential elements.

It directly affects setup and hold timing. Positive skew generally improves setup timing but can make hold timing more difficult, while negative skew generally has the opposite effect.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Synopsys – Static Timing Analysis and Timing Constraints documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
