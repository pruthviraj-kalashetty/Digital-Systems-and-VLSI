# **Launch and Capture Elements**

* **Overview**

In a synchronous digital circuit, data usually moves from one flip-flop to another.

The flip-flop that sends the data is called the **launch element**.

The flip-flop that receives the data is called the **capture element**.

Understanding these two elements is essential for setup and hold timing analysis.

* **Definition**

**Launch Element:** The sequential element that launches data into a timing path at a clock edge.

**Capture Element:** The sequential element that captures the data at a later clock edge.

In a basic register-to-register path:

    Launch FF → Combinational Logic → Capture FF

* **Why is it needed?**

STA uses launch and capture elements to determine:

- When data starts traveling.
- When data should arrive.
- Which clock edges are involved.
- Whether setup time is satisfied.
- Whether hold time is satisfied.
- The timing slack of the path.

Without identifying the launch and capture elements, the timing path cannot be analyzed correctly.

* **Core Concept**

Consider two flip-flops:

    Clock
      │
      ├──────────────┐
      │              │
      ▼              ▼
    ┌─────┐        ┌─────┐
    │ FF1 │        │ FF2 │
    │     │        │     │
    └──┬──┘        └──▲──┘
       │ Q             │ D
       │               │
       └── Data Path ──┘

    FF1 = Launch Element
    FF2 = Capture Element

When the active clock edge arrives:

1. FF1 launches data from its Q output.
2. Data travels through the combinational logic.
3. Data reaches FF2.
4. FF2 captures the data at the next active clock edge.

* **Timing Diagram**

A simplified timing relationship is:

    Clock
          ↑                         ↑
          │                         │
    ──────┼─────────────────────────┼──────
          │                         │
       Launch                    Capture
        Edge                      Edge
          │                         │
          ▼                         │
       FF1 launches                 │
          │                         │
          └─── Data Path ──────────►│
                                    │
                              FF2 captures

The launch and capture edges define the timing window available for the data.

* **Important Terms**

**Launch Clock Edge**

The clock edge that causes the launch element to send new data.

**Capture Clock Edge**

The clock edge at which the capture element samples the incoming data.

**Launch Element**

Usually the source flip-flop or register.

**Capture Element**

Usually the destination flip-flop or register.

**Data Path**

The logic and interconnect between the launch and capture elements.

**Clock Path**

The path through which the clock reaches the launch and capture elements.

**Clock-to-Q Delay**

The time between the active clock edge at the launch flip-flop and the corresponding change at its Q output.

**Setup Time**

The minimum time for which data must be stable before the capture edge.

**Hold Time**

The minimum time for which data must remain stable after the capture edge.

* **Formula**

For a basic setup check:

    tCQ + tDATA + tSETUP ≤ TCLK

Where:

- `tCQ` = launch flip-flop clock-to-Q delay
- `tDATA` = data-path delay
- `tSETUP` = capture flip-flop setup time
- `TCLK` = clock period

Basic setup slack:

    Setup Slack = Required Time - Arrival Time

* **Simple Example**

Assume:

    Clock Period = 10 ns
    Launch FF Clock-to-Q = 1 ns
    Data Path Delay = 6 ns
    Capture FF Setup Time = 1 ns

Data arrival:

    Arrival Time = 1 + 6
                 = 7 ns

Latest allowed arrival:

    Required Time = 10 - 1
                  = 9 ns

Therefore:

    Setup Slack = 9 - 7
                = +2 ns

The data reaches the capture element 2 ns before the latest allowed time.

* **STA Connection**

STA identifies the launch and capture elements first.

Then it analyzes:

    Launch FF
       │
       │ Clock-to-Q
       ▼
    Data Path
       │
       │ Data Delay
       ▼
    Capture FF
       │
       │ Setup/Hold Requirement
       ▼
    Timing Check

For **setup analysis**, STA mainly considers the maximum delay through the timing path.

For **hold analysis**, STA mainly considers the minimum delay through the timing path.

Clock arrival at both elements is also important because clock skew can change the available timing margin.

* **RTL Relevance**

RTL designers frequently create launch and capture elements using registers or flip-flops.

For example:

    always @(posedge clk)
        q1 <= d;

    always @(posedge clk)
        q2 <= q1;

Here:

- `q1` acts as the launch register.
- `q2` acts as the capture register.
- Logic between them forms the data path.

The RTL structure determines how much combinational logic exists between the registers, which can directly affect timing.

* **Common Mistakes**

- Confusing the launch element with the capture element.
- Thinking the launch flip-flop immediately sends data at its D input.
- Forgetting the clock-to-Q delay.
- Ignoring the combinational logic between registers.
- Assuming launch and capture always use different clocks.
- Confusing launch/capture elements with input/output ports.
- Checking setup timing without considering the capture element's setup requirement.
- Checking hold timing without considering the capture element's hold requirement.

* **Interview Questions**

**1. What is a launch element?**

A launch element is the sequential element that launches data into a timing path, usually at an active clock edge.

**2. What is a capture element?**

A capture element is the sequential element that receives and samples the data at the destination of the timing path.

**3. What is the typical register-to-register timing path?**

    Launch FF → Data Path → Capture FF

**4. Why is clock-to-Q delay important?**

The launch flip-flop does not change its output immediately after the clock edge. Clock-to-Q delay determines when the launched data becomes available to the data path.

**5. What determines whether the capture flip-flop can correctly receive the data?**

The data must arrive early enough to satisfy setup time and must remain stable long enough to satisfy hold time.

* **Quick Revision**

- Launch element → sends data.
- Capture element → receives data.
- Typical path → Launch FF → Data Path → Capture FF.
- Launch timing includes clock-to-Q delay.
- Capture timing includes setup and hold requirements.
- Setup → data must arrive early enough.
- Hold → data must remain stable long enough.

* **Summary**

Launch and capture elements define the beginning and end of a synchronous timing path. The launch element sends data after a clock edge, while the capture element samples the data at a later clock edge. STA uses these elements to calculate arrival time, required time, setup slack, and hold slack. Understanding launch and capture elements is therefore fundamental to STA and timing analysis.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
