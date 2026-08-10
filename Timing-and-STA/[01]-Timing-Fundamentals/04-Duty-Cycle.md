# **Duty Cycle**

* **Overview**

Duty cycle describes the percentage of one clock period for which the clock signal remains HIGH.

It is an important clock characteristic because it determines the relationship between the clock's HIGH time and LOW time.

---

* **Definition**

Duty cycle is the ratio of the **HIGH time** of a periodic clock signal to its **total clock period**, expressed as a percentage.

---

* **Why is it needed?**

An ASIC RTL engineer needs to understand duty cycle because:

- It describes the shape of the clock waveform.
- It affects clock HIGH and LOW durations.
- Some sequential elements and clocked circuits have minimum HIGH/LOW time requirements.
- It helps understand real clock behavior during timing analysis.

---

* **Core Concept**

For one clock cycle:

**Clock Period = HIGH Time + LOW Time**

The duty cycle tells us how much of the total period the clock stays HIGH.

For example, with a **50% duty cycle**:

    HIGH Time = 50% of Period
    LOW Time  = 50% of Period

For a 10 ns clock:

    HIGH = 5 ns
    LOW  = 5 ns

---

* **Timing Diagram**

    Clock:

           HIGH = 5 ns
        <------------>
        ____/‾‾‾‾‾‾‾‾\________/‾‾‾‾‾‾‾‾\____
            ↑        ↑        ↑
          Rising   Falling  Rising
           Edge      Edge     Edge

        <------------- 10 ns -------------->
                 Clock Period

For a 50% duty cycle:

- HIGH time = 5 ns
- LOW time = 5 ns
- Clock period = 10 ns

---

* **Important Terms**

- **Clock Period** → Total time for one clock cycle.
- **HIGH Time** → Time during which the clock is HIGH.
- **LOW Time** → Time during which the clock is LOW.
- **Duty Cycle** → Percentage of the period spent HIGH.
- **Rising Edge** → Transition from 0 to 1.
- **Falling Edge** → Transition from 1 to 0.

---

* **Formula**

**Duty Cycle = (HIGH Time / Clock Period) × 100%**

Where:

- **HIGH Time** = Duration for which clock is HIGH.
- **Clock Period** = HIGH Time + LOW Time.

Therefore:

**T = T<sub>HIGH</sub> + T<sub>LOW</sub>**

---

* **Simple Example**

Given:

- Clock Period = **10 ns**
- HIGH Time = **6 ns**

Calculate duty cycle:

**Duty Cycle = (6 / 10) × 100%**

**Duty Cycle = 60%**

Therefore:

- HIGH time = 6 ns
- LOW time = 4 ns
- Duty cycle = **60%**

---

* **STA Connection**

Duty cycle is related to clock waveform timing.

In basic STA, the clock definition includes timing information such as its period and waveform.

For example, a clock with:

- Period = 10 ns
- Rising edge = 0 ns
- Falling edge = 5 ns

has a **50% duty cycle**.

The duty cycle becomes especially relevant when timing checks depend on particular clock edges or when minimum HIGH/LOW pulse-width requirements must be satisfied.

---

* **RTL Relevance**

At the RTL level, engineers generally describe the functional behavior of synchronous logic rather than physically implementing the clock waveform.

However, an RTL engineer should understand duty cycle because:

- Clocked logic depends on clock edges.
- Clock constraints define clock behavior for timing analysis.
- Clock-generation logic can affect waveform characteristics.
- Real hardware clocks may not have exactly 50% duty cycle.

---

* **Common Mistakes**

- Confusing duty cycle with clock frequency.
- Assuming every clock always has a 50% duty cycle.
- Using HIGH time instead of the complete clock period in the formula.
- Forgetting that HIGH time + LOW time = clock period.
- Assuming duty cycle alone determines the complete timing behavior of a clock.

---

* **Interview Questions**

**1. What is duty cycle?**

**Answer:**

Duty cycle is the percentage of one clock period for which the clock signal remains HIGH.

---

**2. What is the formula for duty cycle?**

**Answer:**

**Duty Cycle = (HIGH Time / Clock Period) × 100%**

---

**3. What is the duty cycle of a clock with 10 ns period and 5 ns HIGH time?**

**Answer:**

**Duty Cycle = (5 / 10) × 100 = 50%**

---

**4. Is a clock always required to have a 50% duty cycle?**

**Answer:**

No. A clock can have different duty cycles depending on the clock-generation and distribution circuitry and the requirements of the design.

---

**5. What is the relationship between clock period and duty cycle?**

**Answer:**

Clock period is the total cycle time, while duty cycle specifies what percentage of that period is spent in the HIGH state.

---

* **Quick Revision**

- **Duty Cycle** → Percentage of time the clock is HIGH.
- **Formula** → **(HIGH Time / Period) × 100%**
- **Period** → HIGH Time + LOW Time.
- **50% Duty Cycle** → HIGH and LOW times are equal.
- Duty cycle describes the clock waveform.
- It is different from clock frequency.
- Duty cycle can be relevant to clock pulse-width timing checks.

---

* **Summary**

Duty cycle describes how much of a clock period the signal remains HIGH. A 50% duty-cycle clock spends equal time HIGH and LOW.

For an ASIC RTL engineer, understanding duty cycle helps in understanding clock waveforms, clock constraints, and basic timing requirements.

---

* **References**

- David Harris and Sarah Harris – *Digital Design and Computer Architecture*.
- Neil H. E. Weste and David Harris – *CMOS VLSI Design*.
- Synopsys – Timing Constraints and Static Timing Analysis documentation.
- Neso Academy – Digital Electronics and VLSI concepts.
