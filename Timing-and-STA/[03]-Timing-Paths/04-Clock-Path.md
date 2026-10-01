# **Clock Path**

* **Overview**

The clock path is the path through which the clock signal travels from its source to the clock pins of sequential elements.

In a register-to-register timing path, there are two important clock paths:

- Clock path to the **launch element**
- Clock path to the **capture element**

The difference in their clock arrival times creates **clock skew**, which affects setup and hold timing.

* **Definition**

A **clock path** is the path followed by the clock signal from the clock source to the clock pin of a sequential element such as a flip-flop.

A simplified timing path contains:

    Clock Source
         │
         ├───────────────► Launch FF
         │
         └───────────────► Capture FF

The clock does not necessarily reach both flip-flops at exactly the same time.

* **Why is it needed?**

The clock path is important because STA must know when the clock reaches the launch and capture elements.

Clock-path analysis helps determine:

- Launch clock arrival time
- Capture clock arrival time
- Clock skew
- Setup timing
- Hold timing
- Timing slack
- Clock-related timing violations

* **Core Concept**

Consider a basic register-to-register path:

             CLOCK SOURCE
                  │
          ┌───────┴───────┐
          │               │
          ▼               ▼
       Clock Path      Clock Path
          │               │
          ▼               ▼
      Launch FF        Capture FF
          │ Q              ▲ D
          │                │
          └── Data Path ───┘

There are therefore two paths to consider:

    Clock Source → Launch FF
    Clock Source → Capture FF

The data path carries the data.

The clock paths carry the clock signal.

* **Timing Diagram**

A simplified clock-arrival relationship is:

    Clock Source
          │
          ├──────────────► Launch FF
          │                    │
          │                    │ Launch Edge
          │                    ▼
          │
          └──────────────► Capture FF
                               │
                               │ Capture Edge
                               ▼

If the clock reaches the capture flip-flop later than the launch flip-flop:

    Launch Clock Arrival  = 0 ns
    Capture Clock Arrival = 0.5 ns

Then:

    Clock Skew
    = Capture Arrival - Launch Arrival
    = 0.5 - 0
    = +0.5 ns

This is called **positive clock skew**.

* **Important Terms**

**Clock Source**

The point from which the clock signal originates for the timing analysis.

**Clock Path**

The route taken by the clock signal from its source to a sequential element.

**Launch Clock Path**

The clock path from the clock source to the clock pin of the launch element.

**Capture Clock Path**

The clock path from the clock source to the clock pin of the capture element.

**Clock Arrival Time**

The time at which the clock edge reaches a particular sequential element.

**Clock Skew**

The difference between capture-clock arrival and launch-clock arrival.

    Clock Skew
    = Capture Clock Arrival
    - Launch Clock Arrival

**Clock Network**

The overall clock distribution structure that delivers the clock to sequential elements.

* **Formula**

Basic clock skew:

    tSKEW = tCAPTURE_CLOCK - tLAUNCH_CLOCK

Where:

- `tSKEW` = clock skew
- `tCAPTURE_CLOCK` = capture clock arrival time
- `tLAUNCH_CLOCK` = launch clock arrival time

For a simplified setup relationship:

    tCQ + tDATA + tSETUP
    ≤
    TCLK + tSKEW

For positive skew:

    tSKEW > 0

the capture edge arrives later, generally providing more setup time.

For negative skew:

    tSKEW < 0

the capture edge arrives earlier, generally providing less setup time.

* **Simple Example**

Assume:

    Launch Clock Arrival  = 1 ns
    Capture Clock Arrival = 2 ns

Therefore:

    Clock Skew
    = 2 - 1
    = +1 ns

The capture clock arrives 1 ns later than the launch clock.

For a simplified setup analysis, this positive skew increases the available setup timing window.

However, positive skew can reduce hold margin.

* **STA Connection**

STA analyzes both the data path and clock paths.

A simplified STA view is:

                 Clock Source
                      │
             ┌────────┴────────┐
             │                 │
             ▼                 ▼
       Launch Clock       Capture Clock
          Path                Path
             │                 │
             ▼                 ▼
         Launch FF          Capture FF
             │
             │
             ▼
          Data Path
             │
             └──────────────► Capture FF

STA determines:

1. Launch clock arrival time.
2. Capture clock arrival time.
3. Data arrival time.
4. Required arrival time.
5. Setup or hold slack.

Clock-path differences are especially important when analyzing clock skew.

* **RTL Relevance**

RTL designers normally do not directly implement physical clock routing.

However, RTL structure can influence the number and type of sequential elements receiving a clock.

Good RTL clock practices include:

- Use dedicated clock signals properly.
- Avoid unnecessary generated or gated clocks.
- Prefer clock-enable logic where appropriate instead of creating unnecessary derived clocks.
- Avoid using ordinary combinational logic to modify clock signals.
- Keep clock-domain boundaries clear.

Physical implementation tools later build and optimize the actual clock network.

* **Common Mistakes**

- Confusing the clock path with the data path.
- Assuming the clock reaches every flip-flop at exactly the same time.
- Ignoring clock skew.
- Confusing clock skew with clock jitter.
- Thinking the clock path carries data.
- Assuming positive skew always improves timing.
- Forgetting that positive skew can help setup but hurt hold.
- Trying to solve physical clock-routing problems only through RTL changes.

* **Interview Questions**

**1. What is a clock path?**

A clock path is the path followed by the clock signal from its source to the clock pin of a sequential element.

**2. What are launch and capture clock paths?**

The launch clock path carries the clock to the launch element, while the capture clock path carries the clock to the capture element.

**3. What is clock skew?**

Clock skew is the difference between the arrival time of the capture clock and the launch clock.

**4. How does positive skew affect setup timing?**

Positive skew generally gives the data more time to reach the capture element, helping setup timing.

**5. How does positive skew affect hold timing?**

Positive skew generally reduces hold margin and can make hold timing more difficult.

* **Quick Revision**

- Clock path = path followed by the clock.
- Clock source → clock path → sequential element.
- There are launch and capture clock paths.
- Clock arrival time can differ between flip-flops.
- Clock skew = capture clock arrival − launch clock arrival.
- Positive skew generally helps setup.
- Positive skew generally hurts hold.
- Clock path and data path are different.

* **Summary**

The clock path carries the clock signal from its source to the sequential elements in a digital design. In a register-to-register timing path, STA analyzes both the launch and capture clock paths along with the data path. Differences in clock arrival time create clock skew, which directly affects setup and hold timing. Understanding the clock path is therefore essential for understanding clock skew and STA timing analysis.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
