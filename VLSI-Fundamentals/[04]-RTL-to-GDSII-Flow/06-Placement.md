# **Placement**

* **Overview:**  
Placement is a major stage of Physical Design in which the physical locations of standard cells and other implementation cells are determined within the floor-planned core area. The goal is to create a physically valid and optimized arrangement that supports **timing, routing, power, area, and overall PPA**.

---

* **Definition:**  
Placement is the process of assigning physical locations to standard cells and other required cells in the available placement region after floor planning. The placement tool attempts to optimize **timing, wirelength, congestion, power, and area** while satisfying physical and design constraints.

---

* **Why is Placement Needed?**

Placement is needed because the synthesized gate-level netlist describes logical connectivity but does not yet define the exact physical locations of the cells.

Placement is used to:

- Assign physical locations to standard cells.
- Reduce unnecessary wirelength.
- Improve timing.
- Reduce routing congestion.
- Support clock-tree implementation.
- Improve power characteristics.
- Maintain legal cell placement.
- Support efficient routing.
- Improve overall PPA.
- Prepare the design for Clock Tree Synthesis and routing.

---

* **Where Does Placement Fit?**

```text id="m4p3x2"
Specification
      ↓
Architecture
      ↓
RTL Design
      ↓
Functional Verification
      ↓
Logic Synthesis
      ↓
Gate-Level Netlist
      ↓
Floor Planning
      ↓
Placement
      ↓
Clock Tree Synthesis
      ↓
Routing
      ↓
Parasitic Extraction
      ↓
Timing / Power Analysis
      ↓
Physical Verification
      ↓
Signoff
      ↓
Tapeout
```

Placement follows **Floor Planning** and generally precedes **Clock Tree Synthesis (CTS)**.

---

* **Working Principle:**

Placement takes the floor-planned design and determines suitable physical locations for the cells.

```text id="w3x1cj"
Gate-Level Netlist
        +
Floor Plan
        +
Technology Information
        +
Design Constraints
        ↓
     Placement
        ↓
Cell Locations
        ↓
Timing / Congestion / Wirelength Analysis
        ↓
Placement Optimization
        ↓
Optimized Placement
```

The placement process must consider both **logical connectivity** and **physical constraints**.

---

* **Basic Placement Structure:**

```text id="s7z9pw"
             Floor-Planned Core
┌──────────────────────────────────────┐
│                                      │
│  ┌───────┐                           │
│  │ Macro │                           │
│  └───────┘                           │
│                                      │
│  ────────────────────────────────    │
│  Standard Cell Rows                  │
│  [ ][ ][ ][ ][ ][ ][ ][ ][ ][ ]      │
│  [ ][ ][ ][ ][ ][ ][ ][ ][ ]         │
│  [ ][ ][ ][ ][ ][ ][ ][ ][ ][ ]      │
│  [ ][ ][ ][ ][ ][ ][ ][ ][ ]         │
│                                      │
│                  ┌───────┐           │
│                  │ Macro │           │
│                  └───────┘           │
│                                      │
└──────────────────────────────────────┘
```

Standard cells are placed into predefined rows while respecting physical constraints and blockages.

---

* **Standard Cells:**

Standard cells are pre-designed logic cells available in a technology library.

Examples include:

- Inverters
- Buffers
- NAND gates
- NOR gates
- AND gates
- OR gates
- XOR gates
- Multiplexers
- Flip-flops
- Latches

A synthesized netlist contains instances of such cells, and placement determines where those instances are physically located.

---

* **Placement Rows:**

Standard cells are commonly placed in predefined rows within the core.

Conceptually:

```text id="9m6fbs"
Core
┌─────────────────────────────────────┐
│                                     │
│ Row 1: [ ][ ][ ][ ][ ][ ][ ][ ]     │
│                                     │
│ Row 2: [ ][ ][ ][ ][ ][ ][ ][ ]     │
│                                     │
│ Row 3: [ ][ ][ ][ ][ ][ ][ ][ ]     │
│                                     │
│ Row 4: [ ][ ][ ][ ][ ][ ][ ][ ]     │
│                                     │
└─────────────────────────────────────┘
```

The placement tool determines which cell goes into which location while maintaining legal physical placement.

---

* **Placement Objectives:**

The main placement objectives include:

### 1. Timing

Place timing-critical cells and logic so that critical paths can meet timing requirements.

### 2. Wirelength

Reduce unnecessary physical distance between connected cells.

### 3. Congestion

Avoid excessive concentration of routing demand in particular regions.

### 4. Power

Reduce unnecessary switching-related and interconnect-related power where possible.

### 5. Area

Use the available core area efficiently.

### 6. Routability

Create a placement that can be successfully connected during routing.

---

* **Wirelength:**

Wirelength is the physical distance of interconnect between connected cells.

Example:

```text id="r9f5a7"
Poor Placement:

Cell A ───────────────────── Cell B
             Long Wire


Better Placement:

Cell A ───── Cell B
        Shorter Wire
```

Shorter interconnect can help reduce:

- Delay
- Capacitance
- Routing demand
- Dynamic power

Therefore, wirelength is an important placement objective.

---

* **Timing Optimization:**

Placement directly affects timing because physical distance contributes to interconnect delay.

Simplified path:

```text id="d4v6cc"
Register
   ↓
Logic Cell
   ↓
Wire
   ↓
Logic Cell
   ↓
Register
```

If cells are physically far apart:

```text id="2a9u4k"
Long Distance
     ↓
Longer Interconnect
     ↓
Higher Parasitic Effects
     ↓
Higher Delay
     ↓
Possible Timing Violation
```

Placement therefore tries to position cells to support timing-critical paths.

---

* **Critical Path Placement:**

Consider:

```text id="z3m3az"
FF1 → Logic1 → Logic2 → Logic3 → FF2
```

If this is a timing-critical path, placement should avoid unnecessary physical distance between the cells involved.

Conceptually:

```text id="af2h5n"
FF1
 ↓
Logic1
 ↓
Logic2
 ↓
Logic3
 ↓
FF2
```

A physically compact arrangement can reduce interconnect distance, although actual optimization depends on the complete design and routing environment.

---

* **Congestion:**

Congestion occurs when too much routing demand is concentrated in a physical region.

```text id="tq0lkl"
Many Connections
       ↓
High Routing Demand
       ↓
Limited Routing Resources
       ↓
Congestion
```

Example:

```text id="bq6v6f"
┌──────────────────────────────┐
│  → → → → → → → → → →        │
│  → → → → → → → → → →        │
│  → → → → → → → → → →        │
│       CONGESTED REGION       │
└──────────────────────────────┘
```

High congestion can make routing difficult and can negatively affect timing.

---

* **Placement Density:**

Placement density indicates how many cells are concentrated within a physical region.

Very high local density can cause:

```text id="r5v8c1"
High Density
     ↓
Less Routing Space
     ↓
Congestion
     ↓
Routing Difficulty
```

Therefore, placement tools attempt to distribute cells appropriately.

---

* **Global Placement:**

Global placement determines approximate locations of cells across the core.

At this stage, the placement may not yet satisfy all detailed physical legality requirements.

The primary goals are generally:

- Good overall distribution.
- Reduced wirelength.
- Controlled congestion.
- Better timing potential.

Conceptually:

```text id="9p9w4q"
Netlist
  ↓
Global Placement
  ↓
Approximate Cell Locations
  ↓
Optimization
```

---

* **Legalization:**

After global placement, cells may need to be adjusted to valid physical locations.

Legalization ensures that:

- Cells do not overlap.
- Cells remain within valid regions.
- Cells align with placement rows.
- Physical placement rules are respected.

Example:

```text id="h1g5eg"
Before Legalization:

[Cell A]
     [Cell B]
          [Cell C]
     ↑ Overlap / Invalid Position


After Legalization:

[Cell A][Cell B][Cell C]
```

Legalization makes the placement physically valid while attempting to minimize disruption to the optimized placement.

---

* **Detailed Placement:**

Detailed placement performs further local optimization after legalization.

It may adjust:

- Cell positions
- Cell ordering
- Local spacing
- Timing-critical cells
- Congested regions

The goal is to improve placement quality while maintaining legality.

---

* **Placement Optimization Flow:**

```text id="s2z5kw"
Initial Placement
       ↓
Global Placement
       ↓
Legalization
       ↓
Detailed Placement
       ↓
Timing / Congestion Analysis
       ↓
Placement Optimization
       ↓
Finalized Placement
```

The exact sequence varies between physical-design tools and flows.

---

* **High-Fanout Nets:**

A high-fanout net drives many loads.

Example:

```text id="e3n4k5"
             ┌── Cell 1
             │
Source ──────┼── Cell 2
             │
             ├── Cell 3
             │
             └── Cell 4
```

High fanout can cause:

- Large capacitance
- Increased delay
- Higher power
- Difficult timing closure

Placement may consider the physical distribution of cells connected to high-fanout nets.

Buffers may also be inserted during implementation to improve signal delivery.

---

* **Buffer Placement:**

Buffers can be used to improve signal integrity and timing for long or heavily loaded connections.

Conceptually:

```text id="v1w5qm"
Without Buffer:

Driver ───────────────────── Loads


With Buffer:

Driver ───── Buffer ──────── Loads
```

For very large fanout:

```text id="s6f6ka"
             ┌── Load
             │
Driver ─ Buffer ─ Load
             │
             └── Load
```

Buffering decisions are made as part of implementation optimization.

---

* **Placement and Power:**

Placement can influence power because physical distance affects capacitance and interconnect activity.

Simplified relationship:

```text id="6y9j3m"
Longer Wires
     ↓
Higher Capacitance
     ↓
More Dynamic Power
```

A useful simplified dynamic power relationship is:

```text id="x6qjcz"
Pdynamic ≈ α × C × V² × f
```

where:

- `α` = switching activity
- `C` = capacitance
- `V` = supply voltage
- `f` = frequency

Placement can therefore influence power indirectly through interconnect characteristics.

---

* **Placement and Area:**

Placement must fit all required cells within the available core area.

If the design is too dense:

```text id="9v4s7m"
High Density
     ↓
Less Routing Space
     ↓
Congestion
     ↓
Timing / Routing Problems
```

If excessive area is used:

```text id="n7h1w3"
Larger Core
     ↓
Larger Physical Area
     ↓
Potentially Higher Cost
```

Therefore, placement attempts to balance area efficiency with routability and performance.

---

* **Placement and Routing:**

Placement determines **where cells are located**.

Routing determines **how those cells are physically connected**.

```text id="c4f8r1"
Placement
    ↓
Cell Locations
    ↓
Routing
    ↓
Metal + Via Connections
```

A placement is successful only when it provides a practical foundation for routing.

---

* **Placement Blockages:**

Placement blockages restrict where cells can be placed.

They may be used around:

- Macros
- Reserved routing regions
- Power structures
- Special physical regions

Example:

```text id="2l8qfs"
┌───────────────────────────────┐
│ Standard Cell Region          │
│                               │
│       ┌─────────────┐         │
│       │  BLOCKAGE   │         │
│       │  No Cells   │         │
│       └─────────────┘         │
│                               │
└───────────────────────────────┘
```

Blockages help control placement and congestion.

---

* **Placement Constraints:**

Placement must respect various constraints, including:

- Core boundaries
- Placement rows
- Macros
- Blockages
- Keep-out regions
- Power structures
- Timing requirements
- Clock-related requirements
- Design rules

The exact constraints depend on the technology and implementation flow.

---

* **Timing Closure and Placement:**

Placement is one of the major stages involved in achieving timing closure.

Simplified flow:

```text id="j9z5wl"
Placement
    ↓
Physical Interconnect
    ↓
Parasitic Effects
    ↓
Timing Analysis
    ↓
Slack
    ↓
Optimization
```

If timing violations exist, implementation tools may optimize:

- Cell locations
- Cell sizes
- Buffering
- Logic paths
- Routing-related structures

---

* **Placement Reports:**

Physical-design tools can generate reports containing information such as:

### Timing

- Setup slack
- Hold slack
- Critical paths
- Path delay

### Congestion

- Routing demand
- Congested regions
- Available routing resources

### Area

- Cell area
- Core area
- Utilization

### Power

- Power estimates
- Switching activity
- Cell/interconnect contribution

These reports help designers evaluate placement quality.

---

* **Placement Quality:**

A good placement should provide:

```text id="3q8c4x"
Good Timing
     +
Low/Controlled Congestion
     +
Reasonable Wirelength
     +
Good Routability
     +
Acceptable Power
     +
Efficient Area
     ↓
Good Placement
```

No single metric is sufficient to judge placement quality.

---

* **Placement vs Floor Planning:**

| Floor Planning | Placement |
|---|---|
| Plans overall physical organization | Determines detailed cell locations |
| Defines core and die dimensions | Places standard cells |
| Places major macros | Optimizes cell distribution |
| Plans I/O locations | Optimizes timing and congestion |
| Plans initial power structure | Prepares for CTS and routing |
| Earlier stage | Follows floor planning |

Simplified:

```text id="b8r4g2"
Floor Planning
      ↓
Macro / Core / I/O Organization
      ↓
Placement
      ↓
Standard Cell Locations
```

---

* **Placement vs Clock Tree Synthesis:**

| Placement | Clock Tree Synthesis |
|---|---|
| Determines cell locations | Builds clock distribution network |
| Focuses on placement, wirelength, timing, congestion | Focuses on clock skew, latency, transition, and clock connectivity |
| Primarily handles data-path physical organization | Handles clock-path physical organization |
| Occurs before CTS in a typical flow | Follows placement |

---

* **Placement vs Routing:**

| Placement | Routing |
|---|---|
| Determines where cells are located | Connects cells physically |
| Produces cell locations | Produces metal/via connections |
| Optimizes wirelength and congestion | Creates actual interconnect |
| Prepares design for routing | Follows placement and CTS |

---

* **Logic Synthesis vs Placement:**

| Logic Synthesis | Placement |
|---|---|
| Converts RTL to gate-level netlist | Places cells physically |
| Logical implementation | Physical implementation |
| Uses standard-cell library for mapping | Uses physical cell information and floor plan |
| Produces gate-level connectivity | Produces physical cell locations |
| Primarily logical optimization | Primarily physical optimization |

---

* **RTL Relevance:**

Placement is primarily a Physical Design activity, but it is highly relevant to an RTL Design Engineer.

RTL affects:

- Number of registers
- Number of combinational cells
- Logic depth
- Fanout
- Connectivity
- Datapath structure
- Multiplexer structure
- Memory interfaces
- Control logic

A simplified relationship is:

```text id="4xk9vb"
RTL Architecture
       ↓
Synthesized Logic
       ↓
Cell Count + Connectivity
       ↓
Placement
       ↓
Wirelength + Congestion
       ↓
Timing + Power + Area
```

Therefore, an RTL designer should understand that functionally correct RTL can still produce poor physical implementation results.

---

* **Common Placement Problems:**

### 1. High Congestion

Too many routing connections are concentrated in a region.

### 2. Poor Timing

Cells on critical paths may have unfavorable physical locations.

### 3. Excessive Wirelength

Connected cells may be physically far apart.

### 4. High Local Density

Too many cells are concentrated in a small region.

### 5. High Fanout

A single driver may need to reach many loads.

### 6. Placement Legality Problems

Cells may overlap or violate physical placement requirements.

### 7. Poor Routability

The placement may look acceptable but still be difficult to route.

---

* **Best Practices:**

- Start with a good floor plan.
- Understand major connectivity.
- Avoid excessive local cell density.
- Monitor congestion.
- Pay attention to timing-critical paths.
- Consider high-fanout nets.
- Keep routing feasibility in mind.
- Maintain legal placement.
- Evaluate timing, power, and area together.
- Leave sufficient room for later optimization.
- Revisit floor planning if placement repeatedly shows severe congestion.

---

* **Applications:**

Placement is used in the physical implementation of:

- ASICs
- SoCs
- CPUs
- GPUs
- Microcontrollers
- DSP processors
- AI accelerators
- Networking processors
- Memory controllers
- Communication ICs
- Automotive ICs
- Consumer electronics
- High-performance digital ICs

---

* **Advantages:**

- Converts logical connectivity into physical cell locations.
- Helps optimize timing.
- Helps reduce wirelength.
- Helps control congestion.
- Supports routing.
- Supports power optimization.
- Supports timing closure.
- Helps improve overall PPA.
- Provides the physical foundation for CTS and routing.

---

* **Limitations:**

- Placement alone cannot guarantee timing closure.
- Final interconnect characteristics are not known until routing and extraction are performed.
- Optimization can involve trade-offs between timing, power, area, and congestion.
- A placement that looks good for one metric may be poor for another.
- Poor floor planning can limit placement quality.
- Final physical behavior depends on later implementation stages.

---

* **Real-World Example:**

Consider a small processor subsystem:

```text id="m3f0u8"
CPU Core
   │
   ├──── Cache
   │
   ├──── Bus Controller
   │
   └──── Peripheral Logic
```

After synthesis, these blocks contain many standard cells.

During placement:

```text id="1j7b9a"
┌────────────────────────────────────┐
│              CORE                  │
│                                    │
│  ┌──────────┐      ┌──────────┐   │
│  │  Cache   │      │ Bus Ctrl │   │
│  └────┬─────┘      └────┬─────┘   │
│       │                  │         │
│       └──────┐  ┌────────┘         │
│              ▼  ▼                  │
│          ┌──────────┐              │
│          │ CPU Core │              │
│          └────┬─────┘              │
│               │                    │
│        ┌──────▼────────┐           │
│        │ Peripheral    │           │
│        │ Logic         │           │
│        └───────────────┘           │
│                                    │
└────────────────────────────────────┘
```

The actual physical tool may distribute individual cells differently to optimize timing, congestion, power, and routability.

---

* **Key Points:**

- Placement is a major stage of Physical Design.
- It follows Floor Planning.
- It determines physical locations of standard cells and other implementation cells.
- Placement attempts to optimize **timing, wirelength, congestion, power, area, and routability**.
- Global placement determines approximate cell locations.
- Legalization makes cell locations physically valid.
- Detailed placement performs further local optimization.
- Wirelength affects delay and power.
- High local density can cause congestion.
- High-fanout nets can create timing and power challenges.
- Placement must provide a good foundation for routing.
- Placement is strongly influenced by the quality of the floor plan.
- Placement affects overall PPA.
- RTL architecture and coding indirectly influence placement through logic structure and connectivity.

---

* **Interview Questions:**

### 1. What is Placement?

Placement is the process of assigning physical locations to standard cells and other implementation cells within the floor-planned design.

### 2. Where does placement occur?

Placement occurs after floor planning and before clock-tree synthesis in a typical ASIC implementation flow.

### 3. What are the major objectives of placement?

The major objectives include:

- Timing
- Wirelength
- Congestion
- Power
- Area
- Routability

### 4. What is global placement?

Global placement determines approximate locations for cells across the core while optimizing overall objectives such as wirelength, timing, and congestion.

### 5. What is legalization?

Legalization adjusts cell locations so that they satisfy physical placement rules, such as row alignment and non-overlap.

### 6. What is detailed placement?

Detailed placement performs further local optimization after legalization while maintaining legal cell placement.

### 7. Why is wirelength important?

Longer wires generally introduce more parasitic effects and can increase delay, power, and routing demand.

### 8. What is placement congestion?

Placement congestion occurs when too much routing demand is concentrated in a physical region relative to available routing resources.

### 9. How does placement affect timing?

Cell locations influence physical interconnect length and therefore parasitic delay, which affects timing.

### 10. What is a high-fanout net?

A high-fanout net is a net driven by one source that connects to many loads.

### 11. What is the difference between placement and routing?

Placement determines **where cells are located**, while routing determines **how those cells are physically connected using metal and vias**.

### 12. What is the relationship between floor planning and placement?

Floor planning establishes the overall physical organization and macro/core structure, while placement determines detailed locations of standard cells within that structure.

### 13. Can placement affect power?

Yes. Placement can affect wirelength and capacitance, which influence dynamic power.

### 14. Why should an RTL designer understand placement?

Because RTL structure determines logic count and connectivity, which eventually influence physical placement, wirelength, congestion, timing, and power.

### 15. Does placement guarantee successful routing?

No. Placement should create a routable design, but final routing determines whether all required physical connections can actually be completed.

---

* **Quick Revision:**

```text id="j8y3qz"
Gate-Level Netlist
        ↓
Floor Planning
        ↓
Placement
        ↓
Global Placement
        ↓
Legalization
        ↓
Detailed Placement
        ↓
Timing / Congestion Analysis
        ↓
Placement Optimization
        ↓
Clock Tree Synthesis
        ↓
Routing
        ↓
Parasitic Extraction
        ↓
Timing / Power Analysis
        ↓
Physical Verification
        ↓
Signoff
```

### Remember:

```text
Placement = Where should the cells go?

Wirelength → Physical distance of connections
Congestion → Routing demand vs available resources
Legalization → Make placement physically valid
Timing → Affected by physical interconnect
PPA → Power + Performance + Area
```

---

* **Summary:**  
Placement is the Physical Design stage in which standard cells and other implementation cells are assigned physical locations within the floor-planned core. It aims to create a legal, timing-aware, congestion-aware, and routable physical arrangement while balancing wirelength, power, area, and performance. Placement follows floor planning and provides the physical foundation for Clock Tree Synthesis and routing. For an RTL Design Engineer, understanding placement helps explain how RTL architecture, logic structure, and connectivity eventually influence physical implementation and PPA.

---

* **References:**

- Neso Academy — VLSI and Digital IC Design concepts.
- All About Electronics — Digital Electronics and VLSI-related concepts.
- Weste & Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*.
- Jan M. Rabaey, Anantha Chandrakasan, Borivoje Nikolić — *Digital Integrated Circuits: A Design Perspective*.
- Neil H. E. Weste, David Money Harris — *CMOS VLSI Design*.
