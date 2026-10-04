# **Static Timing Analysis (STA)**

* **Overview:**

Static Timing Analysis (STA) is a timing verification method used to determine whether a digital design meets its required timing constraints **without applying simulation vectors**.

STA analyzes timing paths between sequential elements and checks whether signals arrive within the required time for correct operation.

It is mainly used to check **setup, hold, clock, delay, and slack** requirements throughout the design.

---

* **Definition:**

Static Timing Analysis is the process of analyzing the timing behavior of a digital design using its timing paths, cell delays, interconnect delays, clocks, and timing constraints to determine whether the design satisfies required timing requirements.

The word **Static** means that STA does not require functional input patterns to evaluate timing paths.

A simplified concept is:

```text
RTL / Gate-Level Design
          |
          v
    Timing Constraints
          |
          v
    Timing Analysis
          |
          v
     Timing Reports
          |
          v
   Pass / Timing Violation
```

---

* **Why is STA needed?**

A digital circuit must not only produce the correct logical result; it must also produce that result **within the required time**.

For example:

```text
Launch FF
    |
    v
Combinational Logic
    |
    v
Capture FF
```

If the data arrives too late at the capture flip-flop, a **setup violation** can occur.

If the data arrives too early after the clock edge, a **hold violation** can occur.

STA is needed to:

- Verify timing requirements
- Detect setup violations
- Detect hold violations
- Identify critical paths
- Calculate slack
- Analyze clock relationships
- Estimate timing performance
- Support timing closure
- Verify timing constraints

---

* **Core Concept:**

The fundamental timing path is:

```text
Launch Register
      |
      | Clock-to-Q
      v
Combinational Logic
      |
      | Combinational Delay
      v
Capture Register
      |
      | Setup Time
      v
   Next Clock Edge
```

The data must travel from the launch register to the capture register within the available clock period.

A simplified setup relationship is:

```text
Clock Period
    ≥
Clock-to-Q Delay
+
Combinational Delay
+
Setup Time
+
Timing Margin
```

For hold timing, the data must not arrive too early:

```text
Minimum Data Path Delay
    ≥
Required Hold Time
```

The exact STA equations include clock latency, skew, uncertainty, library timing information, and other effects.

---

* **Timing Path:**

A timing path is a logical and physical path through which a signal travels between timing points.

A basic register-to-register path is:

```text
          Data Path
FF1 ─────────────────────> FF2
 |                         |
 |                         |
Clock                   Clock
 |                         |
 +-----------+-------------+
             |
          Clock Path
```

Common timing path types include:

1. Input → Register
2. Register → Register
3. Register → Output
4. Input → Output

The **register-to-register path** is particularly important in synchronous digital designs.

---

* **Timing Points:**

Important timing points include:

- Primary inputs
- Primary outputs
- Flip-flop clock pins
- Flip-flop data pins
- Latch pins
- Generated clock points
- Other timing endpoints

STA analyzes timing paths between these points.

---

* **Launch and Capture:**

In a register-to-register path:

```text
Launch FF
    |
    | Data
    v
Combinational Logic
    |
    v
Capture FF
```

The first flip-flop is called the **launch register**.

The second flip-flop is called the **capture register**.

The launch register launches data after the active clock edge.

The capture register samples the data at the required clock edge.

---

* **Timing Diagram:**

A simplified setup timing diagram:

```text
Clock:
       ↑                 ↑
       |                 |
       |<--- Period ---->|

       |                 |
Data:
       ────────\________________
                \               |
                 \              |
                  \_____________|
                         ^
                         |
                   Data must
                 arrive before
                  capture edge
```

For setup timing, data must become stable sufficiently before the capture clock edge.

A simplified hold concept:

```text
Clock:
       ↑
       |
       |

Data:
       ────────────────\________
                       |
                       |
                Must remain
                stable for
                hold time
```

---

* **Important Parameters:**

### 1. Clock Period

The time between two active clock edges.

```text
Clock Period = 1 / Clock Frequency
```

For example:

```text
Frequency = 1 GHz

Clock Period = 1 ns
```

---

### 2. Clock-to-Q Delay

The time required for a flip-flop output to change after the active clock edge.

```text
Clock Edge
    |
    | Clock-to-Q
    v
Q changes
```

---

### 3. Combinational Delay

The time required for data to propagate through combinational logic.

Examples include:

- AND gates
- OR gates
- MUXes
- Adders
- Comparators
- Decoders

---

### 4. Setup Time

Setup time is the minimum time for which data must be stable **before** the capture clock edge.

```text
Data Stable
     |
     |<-- Setup Time -->|
                       ↑
                  Clock Edge
```

---

### 5. Hold Time

Hold time is the minimum time for which data must remain stable **after** the capture clock edge.

```text
Clock Edge
     ↑
     |<-- Hold Time -->|
                       |
                    Data must
                    remain stable
```

---

### 6. Clock Skew

Clock skew is the difference in clock arrival time between two sequential elements.

```text
Clock arrives at FF1
        |
        |------>

Clock arrives at FF2
        |
        |---------->

Difference = Clock Skew
```

Clock skew can affect both setup and hold timing.

---

### 7. Clock Latency

Clock latency, also called insertion delay in many physical-design contexts, is the time required for the clock signal to travel from its source to a timing endpoint.

```text
Clock Source
     |
     | Clock Latency
     v
Flip-Flop
```

---

### 8. Clock Uncertainty

Clock uncertainty represents timing variation or margin associated with effects such as:

- Clock jitter
- Modeling uncertainty
- Variation
- Other clock-related margins

It reduces the timing margin available to the design.

---

### 9. Data Arrival Time

Arrival time is the time at which data reaches a timing endpoint.

```text
Launch
   |
   v
Logic + Interconnect
   |
   v
Data Arrival
```

---

### 10. Required Arrival Time

Required arrival time is the latest or earliest time at which data must arrive to satisfy a timing requirement, depending on the timing check.

---

### 11. Slack

Slack represents the difference between the required timing and the actual timing.

For setup timing:

```text
Setup Slack
=
Required Arrival Time
-
Actual Arrival Time
```

Interpretation:

```text
Positive Slack → Timing Met

Zero Slack → Exactly Meets Requirement

Negative Slack → Timing Violation
```

---

* **Setup Analysis:**

Setup analysis checks whether data arrives early enough before the capture clock edge.

Simplified path:

```text
Launch FF
   |
   | Clock-to-Q
   v
Combinational Logic
   |
   | Data Delay
   v
Capture FF
```

A simplified setup requirement is:

```text
Clock Period
≥
Clock-to-Q
+
Combinational Delay
+
Setup Time
+
Timing Margin
```

If the data arrives too late:

```text
Setup Slack < 0
```

A setup violation occurs.

---

* **Hold Analysis:**

Hold analysis checks whether data remains stable for the required time after the capture clock edge.

The basic concept is:

```text
Launch FF
   |
   v
Minimum Data Path Delay
   |
   v
Capture FF
```

A simplified relationship is:

```text
Minimum Data Path Delay
≥
Hold Time
+
Timing Margin
```

If new data reaches the capture register too early:

```text
Hold Slack < 0
```

A hold violation occurs.

---

* **Setup vs Hold:**

| Setup | Hold |
|---|---|
| Checks data arriving too late | Checks data arriving too early |
| Related to maximum delay | Related to minimum delay |
| Usually associated with the next capture edge | Usually checked around the same capture edge |
| Can often be improved by reducing path delay | Can require increasing minimum path delay |
| Negative setup slack = violation | Negative hold slack = violation |

---

* **Setup and Hold Timing Diagram:**

```text
                One Clock Period
       <------------------------------>

Clock:
       ↑                              ↑
       |                              |
       |                              |
       +------------------------------+

Launch FF
       ↑
       |
       +---- Data launches

Data:
       |--------------------------->

                             |<---- Setup ---->|
                                             ↑
                                      Capture Edge
```

For hold:

```text
Capture Edge
      ↑
      |
      |<--- Hold Time --->|
                          |
                     Data must
                     remain stable
```

---

* **Arrival Time and Required Time:**

STA compares when data **actually arrives** with when it is **required to arrive**.

```text
                    Timing Path

Launch FF
    |
    v
Data Path
    |
    v
Capture FF

Actual Arrival Time
          |
          v
      Compare
          ^
          |
Required Arrival Time
```

For setup:

```text
If Arrival Time ≤ Required Time
        |
        v
    Timing Pass
```

If:

```text
Arrival Time > Required Time
        |
        v
    Timing Violation
```

---

* **Slack Analysis:**

Slack is one of the most important STA results.

### Positive Slack

```text
Required Time = 10 ns
Arrival Time  = 8 ns

Slack = 10 - 8
      = +2 ns
```

The path meets the timing requirement.

### Zero Slack

```text
Required Time = 10 ns
Arrival Time  = 10 ns

Slack = 0 ns
```

The path exactly meets the requirement.

### Negative Slack

```text
Required Time = 10 ns
Arrival Time  = 12 ns

Slack = 10 - 12
      = -2 ns
```

The path violates timing.

---

* **Critical Path:**

The critical path is the timing path with the worst timing margin, typically the path with the most negative slack in a violating design or the smallest slack among analyzed paths.

Example:

```text
Path 1 → Slack = +0.8 ns
Path 2 → Slack = +0.2 ns
Path 3 → Slack = -0.4 ns
Path 4 → Slack = +0.5 ns
```

Path 3 is the critical violating path.

Critical paths are important because they often limit the maximum operating frequency.

---

* **Maximum Operating Frequency:**

The clock period determines the operating frequency.

```text
Frequency = 1 / Clock Period
```

For example:

```text
Clock Period = 10 ns

Frequency = 1 / 10 ns
          = 100 MHz
```

If timing optimization allows the clock period to decrease while still satisfying setup timing, the maximum operating frequency can increase.

---

* **Timing Constraints:**

STA requires timing constraints to know what timing behavior is expected.

Common constraints include:

- Clock definitions
- Clock period
- Input delays
- Output delays
- Clock uncertainty
- Input transition
- Output load
- False paths
- Multicycle paths
- Generated clocks
- Timing exceptions

A simplified example:

```text
Clock
  |
  v
create_clock
  |
  v
Timing Analysis
```

Incorrect or incomplete constraints can produce incorrect timing conclusions.

---

* **False Path:**

A false path is a path that exists logically but is not required to meet normal timing analysis because of the design's functional behavior.

Example:

```text
Logic A
   |
   +----------> Logic B
   |
   +----------> Logic C
```

If a particular path can never be active in the required operating conditions, it may be treated as a false path when correctly identified and constrained.

False paths must be used carefully because incorrectly excluding a real timing path can hide timing problems.

---

* **Multicycle Path:**

A multicycle path is a path intentionally allowed more than one clock cycle to transfer data.

Example:

```text
Cycle 1        Cycle 2        Cycle 3
   |              |              |
Launch --------------------------> Capture
```

Such paths require appropriate timing constraints.

---

* **STA Flow:**

A simplified STA flow is:

```text
Gate-Level Netlist
        |
        v
Timing Libraries
        |
        v
Physical / Parasitic Information
        |
        v
Timing Constraints
        |
        v
Timing Graph
        |
        v
Arrival Time Analysis
        |
        v
Required Time Analysis
        |
        v
Slack Calculation
        |
        v
Timing Reports
        |
        v
Pass / Violation
```

---

* **Timing Graph:**

STA represents the design as a timing graph.

A simplified graph:

```text
FF1
 |
 v
AND
 |
 v
MUX
 |
 v
FF2
```

The timing engine analyzes paths through this graph.

Each path contains timing information associated with:

- Cells
- Pins
- Nets
- Delays
- Clock relationships
- Constraints

---

* **Cell Delay and Interconnect Delay:**

A timing path contains both cell and interconnect effects.

```text
      Cell Delay
         ↓
FF ──> Logic ──> Logic ──> FF
        ↑            ↑
        |            |
 Interconnect    Interconnect
    Delay           Delay
```

Simplified:

```text
Total Delay
=
Cell Delay
+
Interconnect Delay
```

In modern physical implementation, interconnect delay can be a significant part of total path delay.

---

* **Pre-Layout and Post-Layout Timing:**

### Pre-Layout Timing

Before physical implementation is complete, interconnect information may be estimated.

```text
RTL / Netlist
     |
     v
Estimated Timing
```

### Post-Layout Timing

After placement and routing, more accurate physical information can be extracted.

```text
Placed + Routed Design
          |
          v
Parasitic Extraction
          |
          v
More Accurate Timing
```

Post-layout timing is therefore important for final timing closure.

---

* **STA and Physical Design:**

STA is closely connected to Physical Design.

```text
Floor Planning
      |
      v
Placement
      |
      v
CTS
      |
      v
Routing
      |
      v
Parasitic Extraction
      |
      v
STA
      |
      v
Timing Closure
```

Physical implementation changes:

- Wirelength
- Resistance
- Capacitance
- Clock latency
- Clock skew
- Signal transition
- Timing paths

STA analyzes these effects.

---

* **STA and Timing Closure:**

Timing closure means achieving the required timing targets across the required analysis conditions.

Simplified loop:

```text
Implementation
      |
      v
STA
      |
      v
Timing Violation?
   /          \
 Yes           No
 |              |
 v              v
Optimize      Timing
 |             Met
 v
Re-run STA
```

Possible optimization methods include:

- Cell sizing
- Buffer insertion
- Logic optimization
- Placement optimization
- Routing optimization
- Clock optimization
- Reducing critical-path delay

---

* **Common Timing Violations:**

### 1. Setup Violation

Data arrives too late.

```text
Setup Slack < 0
```

### 2. Hold Violation

Data arrives too early.

```text
Hold Slack < 0
```

### 3. Transition Violation

Signal transition is slower than the required limit.

### 4. Capacitance Violation

A net exceeds its allowed capacitive load.

### 5. Fanout Violation

A signal drives more loads than permitted by the relevant design constraints or library limits.

---

* **Common Causes of Setup Violations:**

- Long combinational path
- Excessive logic depth
- Large interconnect delay
- High capacitance
- Poor placement
- Routing congestion
- Clock skew
- High fanout
- Insufficient clock period

---

* **Common Causes of Hold Violations:**

- Very short data path
- Small combinational delay
- Clock skew
- Clock latency differences
- Fast cells
- Physical implementation effects

---

* **Timing Optimization:**

For setup violations, common approaches include:

```text
Reduce Logic Delay
       +
Reduce Interconnect Delay
       +
Optimize Cell Drive
       +
Improve Placement
       +
Optimize Routing
```

For hold violations, the goal is generally to prevent data from arriving too early.

Possible techniques include:

- Adding delay cells/buffers
- Increasing minimum path delay
- Clock optimization
- Physical optimization

The exact solution depends on the implementation flow and timing report.

---

* **STA Reports:**

A typical timing report provides information such as:

```text
Startpoint
Endpoint
Launch Clock
Capture Clock
Clock Path
Data Path
Cell Delays
Net Delays
Arrival Time
Required Time
Slack
```

Simplified example:

```text
Startpoint : FF1/Q
Endpoint   : FF2/D

Data Path Delay      : 7.5 ns
Required Arrival     : 10.0 ns
Arrival Time         : 9.0 ns

Slack                : +1.0 ns

Result               : PASS
```

---

* **STA vs Simulation:**

| STA | Simulation |
|---|---|
| Does not require functional input vectors | Requires stimulus/input vectors |
| Analyzes timing paths systematically | Observes behavior for applied scenarios |
| Checks timing constraints | Checks functional behavior and timing behavior in simulation |
| Can analyze many timing paths | Only exercises paths reached by simulation |
| Commonly used for timing verification | Commonly used for functional verification |
| Produces timing reports | Produces waveforms/logs/results |

STA and simulation complement each other; neither replaces the other.

---

* **STA vs Functional Verification:**

| Functional Verification | STA |
|---|---|
| Checks functional correctness | Checks timing correctness |
| Uses stimulus and test scenarios | Uses timing paths and constraints |
| Focuses on behavior | Focuses on timing |
| Uses simulation/testbench | Uses timing analysis engine |
| Finds functional bugs | Finds timing violations |

---

* **STA Relevance to RTL Design:**

An RTL Design Engineer should understand STA because RTL structure directly affects timing.

For example:

```text
RTL
 |
 v
Logic Depth
 |
 v
Combinational Delay
 |
 v
Timing Path Delay
 |
 v
Slack
 |
 v
Maximum Frequency
```

RTL decisions that can affect timing include:

- Deep combinational logic
- Large mux structures
- Long arithmetic paths
- High fanout control signals
- Poor pipeline boundaries
- Excessive logic between registers

A timing-aware RTL designer therefore considers both functionality and timing.

---

* **RTL Example:**

Consider:

```text
FF1
 |
 v
ADD
 |
 v
MUX
 |
 v
COMPARATOR
 |
 v
FF2
```

The path contains multiple combinational operations.

If the total delay becomes too large:

```text
Clock Period < Required Path Delay
```

then setup timing can fail.

One possible architectural solution is pipelining:

```text
FF1
 |
 v
ADD
 |
 v
FF2
 |
 v
MUX
 |
 v
COMPARATOR
 |
 v
FF3
```

The combinational work is divided across multiple clock cycles.

This can improve timing at the cost of additional registers and potentially increased latency and area.

---

* **Timing vs PPA:**

Timing optimization can affect other design metrics.

```text
Timing
   |
   +----> Cell Size
   |
   +----> Buffering
   |
   +----> Area
   |
   +----> Power
```

For example, increasing cell drive strength may improve timing but can increase:

- Area
- Dynamic power
- Leakage power

Therefore, timing optimization must consider the overall **PPA trade-off**.

---

* **Common Mistakes:**

1. Assuming functional simulation proves timing correctness.
2. Ignoring setup and hold timing.
3. Looking only at the worst path without understanding the path.
4. Using incorrect clock constraints.
5. Ignoring clock skew.
6. Ignoring interconnect delay.
7. Assuming all timing problems are caused by RTL logic.
8. Ignoring physical implementation effects.
9. Using false-path constraints incorrectly.
10. Forgetting that hold timing is also important.
11. Treating positive slack as proof that every possible condition is safe without considering the analysis scope.
12. Ignoring timing corners and required analysis conditions in advanced signoff flows.

---

* **Best Practices:**

- Understand the clock requirements before analyzing timing.
- Define correct timing constraints.
- Understand launch and capture points.
- Check both setup and hold timing.
- Understand arrival and required times.
- Analyze slack rather than only delay.
- Identify critical paths.
- Consider logic and interconnect delay.
- Understand clock skew and uncertainty.
- Review timing reports carefully.
- Avoid incorrect timing exceptions.
- Consider timing during RTL architecture and coding.
- Use pipelining when appropriate for long combinational paths.
- Re-run timing analysis after implementation changes.

---

* **Applications:**

STA is widely used in:

- ASIC design
- SoC design
- CPU design
- GPU design
- Microcontroller design
- DSP design
- AI accelerator design
- Memory controller design
- High-speed interfaces
- Digital IP design
- Physical Design
- Timing closure
- Signoff analysis

---

* **Advantages:**

- Does not require functional simulation vectors.
- Systematically analyzes timing paths.
- Detects setup and hold violations.
- Identifies critical paths.
- Provides slack information.
- Supports timing closure.
- Helps determine achievable operating frequency.
- Can analyze timing under different timing conditions.
- Provides detailed timing reports.

---

* **Limitations:**

- Depends heavily on correct timing constraints.
- Does not verify functional correctness.
- Does not replace simulation.
- Timing results depend on library and physical information.
- Incorrect exceptions can hide real timing problems.
- Complex designs require many timing scenarios and analysis conditions.
- STA results alone do not prove complete chip correctness.

---

* **Real-World Example:**

Consider a processor operating at:

```text
Frequency = 1 GHz
```

Therefore:

```text
Clock Period = 1 ns
```

Suppose a register-to-register path has:

```text
Clock-to-Q       = 0.10 ns
Combinational    = 0.65 ns
Setup Time       = 0.10 ns
Timing Margin    = 0.05 ns
```

Total required path:

```text
0.10 + 0.65 + 0.10 + 0.05
= 0.90 ns
```

Available clock period:

```text
1.00 ns
```

Simplified setup margin:

```text
1.00 - 0.90
= +0.10 ns
```

Therefore, the simplified path meets setup timing with approximately:

```text
+0.10 ns slack
```

If routing later increases the interconnect delay by 0.15 ns, the path can become timing-critical or violate setup timing.

This demonstrates why **placement, routing, parasitics, and STA are closely connected.**

---

* **Key Points:**

- STA stands for **Static Timing Analysis**.
- STA checks timing without functional simulation vectors.
- It analyzes timing paths using delays, clocks, and constraints.
- Launch and capture registers define a common register-to-register timing path.
- Setup checks data arriving too late.
- Hold checks data arriving too early.
- Arrival time indicates when data reaches an endpoint.
- Required time indicates when data must arrive.
- Slack represents timing margin.
- Positive slack generally means the analyzed timing requirement is met.
- Negative slack indicates a timing violation.
- Critical paths have the worst timing margin.
- Clock skew and clock latency affect timing.
- Routing introduces resistance and capacitance.
- Parasitic extraction provides more accurate physical timing information.
- STA is essential for timing closure.
- RTL structure can strongly influence timing.
- STA complements functional verification; it does not replace it.

---

* **Interview Questions:**

### 1. What is STA?

STA is a timing analysis method used to verify whether a digital design meets its timing constraints without applying functional simulation vectors.

### 2. Why is STA required?

STA is required to identify setup and hold violations, analyze timing paths, calculate slack, identify critical paths, and verify timing requirements.

### 3. What is a timing path?

A timing path is a logical/physical path through which a signal travels between timing points such as registers or I/O ports.

### 4. What is a launch register?

The launch register is the sequential element that launches data into a timing path after a clock edge.

### 5. What is a capture register?

The capture register is the sequential element that receives and samples the data at the required clock edge.

### 6. What is setup time?

Setup time is the minimum time for which data must be stable before the active capture clock edge.

### 7. What is hold time?

Hold time is the minimum time for which data must remain stable after the active capture clock edge.

### 8. What is setup violation?

A setup violation occurs when data arrives too late to satisfy the setup requirement.

### 9. What is hold violation?

A hold violation occurs when new data arrives too early and changes the capture register input before the required hold interval has elapsed.

### 10. What is slack?

Slack is the difference between required timing and actual timing.

For setup:

```text
Slack = Required Arrival Time - Actual Arrival Time
```

### 11. What does negative slack indicate?

Negative slack indicates that the corresponding timing requirement is violated.

### 12. What is a critical path?

A critical path is a path with the worst timing margin and therefore has a strong influence on the maximum achievable operating frequency.

### 13. What is clock skew?

Clock skew is the difference between clock arrival times at two sequential elements.

### 14. What is clock latency?

Clock latency is the delay from the clock source to a clock endpoint.

### 15. What is clock uncertainty?

Clock uncertainty represents timing margin associated with clock-related variations such as jitter and modeling uncertainty.

### 16. What is the difference between arrival time and required time?

Arrival time tells when data actually reaches an endpoint. Required time tells when the data must reach the endpoint to satisfy the timing requirement.

### 17. Why is routing important for STA?

Routing determines physical interconnects, which introduce resistance and capacitance. These parasitics affect path delay and therefore timing.

### 18. Can STA replace simulation?

No. STA checks timing, while simulation is used to verify functional behavior and specific simulated scenarios.

### 19. How can RTL affect timing?

RTL can affect timing through logic depth, arithmetic complexity, mux structures, fanout, pipeline structure, and register placement.

### 20. What is timing closure?

Timing closure is the process of optimizing the design until required timing constraints are satisfied across the required analysis conditions.

---

* **Quick Revision:**

```text
STA
 ↓
Static Timing Analysis
 ↓
Uses Netlist + Libraries + Constraints + Physical Information
 ↓
Build Timing Paths
 ↓
Calculate Arrival Time
 ↓
Calculate Required Time
 ↓
Calculate Slack
 ↓
Check Setup + Hold
 ↓
Identify Critical Paths
 ↓
Optimize
 ↓
Timing Closure
```

### Remember:

```text
Setup → Data must not arrive too late

Hold → Data must not arrive too early

Arrival Time → When data arrives

Required Time → When data must arrive

Slack → Timing Margin

Negative Slack → Timing Violation

Critical Path → Worst Timing Path
```

---

* **Summary:**

Static Timing Analysis is a fundamental timing verification technique used throughout ASIC implementation to determine whether a digital design satisfies its timing requirements.

STA analyzes timing paths using clock definitions, cell delays, interconnect delays, timing constraints, arrival times, required times, and slack. The two fundamental timing checks are **setup** and **hold**.

Routing and parasitic extraction make physical interconnect effects more accurate, allowing STA to provide more realistic timing information. Timing closure then uses these results to optimize the design.

For an RTL Design Engineer, STA knowledge is important because **RTL architecture, logic depth, pipeline structure, fanout, and datapath organization directly influence timing performance.**

The fundamental relationship to remember is:

```text
RTL
 ↓
Logic Structure
 ↓
Timing Path
 ↓
Physical Implementation
 ↓
Interconnect Parasitics
 ↓
STA
 ↓
Slack
 ↓
Timing Closure
```

---

* **References:**

1. Neso Academy — VLSI / Static Timing Analysis concepts  
2. All About Electronics — Digital Electronics and Timing concepts  
3. Neil H. E. Weste and David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*  
4. J. Bhasker and Rakesh Chadha — *Static Timing Analysis for Nanometer Designs*  
5. Jan M. Rabaey, Anantha Chandrakasan, and Borivoje Nikolić — *Digital Integrated Circuits: A Design Perspective*
