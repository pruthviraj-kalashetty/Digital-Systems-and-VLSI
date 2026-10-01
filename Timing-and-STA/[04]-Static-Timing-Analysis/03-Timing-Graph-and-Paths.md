# **Timing Graph and Paths**

* **Overview**

A timing graph is a representation of a digital circuit used by Static Timing Analysis (STA) to understand how signals move through the design. Timing paths connect a starting point, such as a launch register or input port, to an ending point, such as a capture register or output port.

---

* **Definition**

A **timing graph** represents circuit elements and their timing relationships as connected nodes and edges.

A **timing path** is a complete path through the design from a timing startpoint to a timing endpoint.

---

* **Why is it needed?**

Timing graphs and paths help STA to:

- Identify how data travels through the circuit.
- Determine startpoints and endpoints.
- Calculate data arrival time.
- Calculate required arrival time.
- Analyze setup and hold timing.
- Identify critical timing paths.
- Report timing violations.

---

* **Core Concept**

A simple register-to-register timing path is:

    Launch Register
          │
          │ Clock-to-Q
          ▼
    Combinational Logic
          │
          │ Data Path
          ▼
    Capture Register

In STA, the circuit can be viewed as a graph:

    [Launch FF]
         │
         ▼
      [AND]
         │
         ▼
      [MUX]
         │
         ▼
     [Capture FF]

Each circuit element becomes part of the timing graph, and connections between elements represent possible signal propagation.

---

* **Timing Graph**

A simplified timing graph can be represented as:

    Startpoint
        │
        ▼
      Node A
        │
        ▼
      Node B
        │
        ▼
      Node C
        │
        ▼
     Endpoint

For example:

    FF1 Q
      │
      ▼
    INV1
      │
      ▼
    AND1
      │
      ▼
    MUX1
      │
      ▼
    FF2 D

The timing engine uses this graph to propagate timing information from one node to another.

---

* **Timing Path**

A timing path normally contains:

    Startpoint
        ↓
    Launch / Input
        ↓
    Combinational Logic
        ↓
    Interconnect
        ↓
    Endpoint
        ↓
    Capture / Output

For a register-to-register path:

    Launch FF ──► Logic ──► Capture FF
       │                         │
       │                         │
    Startpoint               Endpoint

The path delay is determined by the delays of the elements along the path.

---

* **Important Terms**

| Term | Meaning |
|---|---|
| **Timing Graph** | Graph representation used to model timing relationships in a design |
| **Node** | A point in the timing graph where timing information is evaluated |
| **Edge** | Connection between timing nodes representing signal propagation |
| **Startpoint** | Beginning point of a timing path |
| **Endpoint** | Ending point of a timing path |
| **Launch Register** | Register that launches data into the data path |
| **Capture Register** | Register that captures the data |
| **Data Path** | Logic and interconnect through which data travels |
| **Timing Path** | Complete timing route from startpoint to endpoint |
| **Critical Path** | Path with the most restrictive timing margin for the check being analyzed |
| **Arrival Time** | Time at which a signal reaches a point |
| **Required Time** | Time by which the signal is required to arrive |
| **Slack** | Difference between required time and arrival time |

---

* **Types of Timing Paths**

### 1. Register-to-Register Path

    Launch FF
        │
        ▼
    Combinational Logic
        │
        ▼
    Capture FF

This is one of the most common paths in synchronous ASIC designs.

---

### 2. Input-to-Register Path

    Input Port
        │
        ▼
    Combinational Logic
        │
        ▼
    Capture FF

The external input provides the starting point.

---

### 3. Register-to-Output Path

    Launch FF
        │
        ▼
    Combinational Logic
        │
        ▼
    Output Port

The register launches the data and the output port is the endpoint.

---

### 4. Input-to-Output Path

    Input Port
        │
        ▼
    Combinational Logic
        │
        ▼
    Output Port

This path has no internal launch and capture register pair.

---

* **Timing Path Example**

Consider:

    FF1
     │
     │ tCQ
     ▼
    AND
     │
     ▼
    OR
     │
     ▼
    MUX
     │
     │ tDATA
     ▼
    FF2

The complete timing path is:

    FF1 → AND → OR → MUX → FF2

Here:

    Startpoint = FF1
    Endpoint   = FF2

The total data arrival is influenced by:

    Clock-to-Q Delay
          +
    AND Delay
          +
    OR Delay
          +
    MUX Delay
          +
    Interconnect Delay

---

* **Timing Path and Setup Analysis**

For a register-to-register setup check:

    Launch Edge
         │
         ▼
       FF1
         │
         │ Data Path
         ▼
       FF2
         │
         ▼
    Capture Edge

The data must reach the capture register early enough to satisfy its setup time.

Simplified:

    Arrival Time ≤ Required Time

Therefore:

    Setup Slack = Required Time − Arrival Time

A negative setup slack indicates a setup timing violation.

---

* **Timing Path and Hold Analysis**

Hold analysis focuses on the minimum delay through the data path.

    Launch Edge
         │
         ▼
       FF1
         │
         │ Minimum Data Delay
         ▼
       FF2
         │
         ▼
    Capture Edge

The newly launched data must not reach the capture register too early.

Therefore, hold analysis is strongly affected by:

- Minimum clock-to-Q delay
- Minimum combinational delay
- Clock skew
- Hold requirement

---

* **Simple Example**

Consider:

    FF1 → AND → OR → FF2

Suppose:

    Clock-to-Q Delay = 1 ns
    AND Delay        = 2 ns
    OR Delay         = 3 ns

Ignoring interconnect delay:

    Total Data Path Delay
    = 1 + 2 + 3
    = 6 ns

The timing path is:

    FF1 → AND → OR → FF2

The STA engine uses this path to calculate the arrival time and compare it with the required time.

---

* **STA Connection**

STA uses timing paths to perform timing analysis.

A simplified process is:

    Netlist
       │
       ▼
    Timing Graph
       │
       ▼
    Identify Timing Paths
       │
       ▼
    Calculate Arrival Time
       │
       ▼
    Calculate Required Time
       │
       ▼
    Calculate Slack
       │
       ▼
    Check Violations

STA analyzes many timing paths in the design rather than relying on a particular functional testbench.

---

* **RTL Relevance**

RTL structure determines the logic that later becomes part of the timing graph.

For example:

    always @(posedge clk)
        q <= a & b & c & d;

Synthesis may create a combinational logic structure between registers.

If too much logic is placed between two registers:

    FF1 → Logic → Logic → Logic → Logic → FF2

the data path can become long, increasing setup timing pressure.

Good RTL design therefore considers:

- Logic depth
- Register placement
- Combinational path length
- Clocked boundaries
- Timing-critical operations

---

* **Common Mistakes**

- Thinking a timing path is only the combinational logic.
- Forgetting the startpoint and endpoint.
- Confusing a timing graph with a functional block diagram.
- Assuming every path has the same delay.
- Ignoring input-to-register and register-to-output paths.
- Considering only setup paths and forgetting hold paths.
- Assuming the longest physical path is always the critical path for every timing check.

---

* **Interview Questions**

**1. What is a timing path?**

A timing path is a complete path from a timing startpoint to a timing endpoint through the circuit.

**2. What is a timing graph?**

A timing graph is a representation of circuit elements and their timing connections that allows STA tools to propagate timing information through the design.

**3. What are common timing path types?**

The common types are:

    Input → Register
    Register → Register
    Register → Output
    Input → Output

**4. What is a startpoint?**

A startpoint is the beginning of a timing path, such as a primary input or a register clock-to-Q output.

**5. What is an endpoint?**

An endpoint is the destination of a timing path, such as a register data input or a primary output.

---

* **Quick Revision**

    Timing Graph
    → Represents timing relationships.

    Timing Path
    → Route from startpoint to endpoint.

    Common paths:

    Input → Register
    Register → Register
    Register → Output
    Input → Output

    Register-to-register:

    Launch FF → Data Path → Capture FF

    STA uses timing paths to calculate:

    Arrival Time
    Required Time
    Slack

    Setup:
    Focuses mainly on maximum delay.

    Hold:
    Focuses mainly on minimum delay.

---

* **Summary**

A timing graph provides the structure that STA uses to model timing relationships in a digital design. Timing paths are the routes through this graph from startpoints to endpoints. Understanding timing graphs and path types is essential before learning setup analysis, hold analysis, arrival time, required time, and slack analysis.

---

* **References**

- Harris, S. L. & Harris, D. M., *Digital Design and Computer Architecture*, Morgan Kaufmann.
- Weste, N. H. E. & Harris, D. M., *CMOS VLSI Design: A Circuits and Systems Perspective*, Pearson.
- Synopsys, *PrimeTime Static Timing Analysis* documentation.
- Cadence, *Static Timing Analysis* technical documentation.
- Neso Academy, Digital Electronics and VLSI Design lectures.
