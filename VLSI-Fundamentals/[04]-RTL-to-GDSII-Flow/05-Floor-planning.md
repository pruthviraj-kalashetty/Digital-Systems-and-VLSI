# **Floor Planning**

* **Overview:**  
Floor Planning is one of the first major stages of Physical Design in which the overall physical organization of a chip is planned. It determines the **chip/core area, aspect ratio, placement of major blocks and macros, I/O locations, power distribution structure, and available regions for standard cells** before detailed placement and routing.

---

* **Definition:**  
Floor Planning is the process of deciding the physical arrangement and initial dimensions of the major components of an IC within the available chip area. It establishes the physical foundation for **placement, clock-tree synthesis, routing, timing, power distribution, and physical verification**.

---

* **Why is Floor Planning Needed?**

Floor Planning is needed because the physical location of blocks strongly affects the quality of the final chip implementation.

It is used to:

- Determine the initial chip and core dimensions.
- Define the core aspect ratio.
- Place large macros and memory blocks.
- Plan I/O and pad locations.
- Define standard-cell placement regions.
- Plan the initial power distribution network.
- Reduce routing congestion.
- Improve timing.
- Reduce unnecessary wirelength.
- Provide a suitable physical structure for later implementation stages.
- Support better Power, Performance, and Area (PPA) optimization.

---

* **Where Does Floor Planning Fit?**

```text
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

Floor Planning is an early and important stage of **Physical Design / Back-End Design**.

---

* **Working Principle:**

Floor Planning starts with the synthesized design information and determines how the major physical components should be organized inside the chip.

```text
Gate-Level Netlist
        +
Technology Information
        +
Design Constraints
        +
Macro Information
        +
I/O Requirements
        ↓
   Floor Planning
        ↓
Chip/Core Organization
        ↓
Placement
```

The main planning activities include:

1. Chip and core size definition.
2. Aspect ratio selection.
3. Macro placement.
4. I/O planning.
5. Standard-cell region planning.
6. Power planning.
7. Placement and routing region definition.
8. Initial congestion and timing consideration.

---

* **Basic Floor Plan Structure:**

```text
                  CHIP / DIE
┌───────────────────────────────────────────┐
│                                           │
│  I/O Pads                                 │
│                                           │
│    ┌─────────────────────────────────┐    │
│    │             CORE                │    │
│    │                                 │    │
│    │  ┌──────┐          ┌────────┐  │    │
│    │  │Macro │          │ Memory │  │    │
│    │  │      │          │        │  │    │
│    │  └──────┘          └────────┘  │    │
│    │                                 │    │
│    │       Standard Cell Region      │    │
│    │                                 │    │
│    │  ┌────────┐                     │    │
│    │  │ Macro  │                     │    │
│    │  └────────┘                     │    │
│    │                                 │    │
│    └─────────────────────────────────┘    │
│                                           │
│  I/O Pads                                 │
│                                           │
└───────────────────────────────────────────┘
```

The exact physical arrangement depends on the design requirements and technology.

---

* **Chip / Die Area:**

The **die** is the physical piece of semiconductor containing the integrated circuit.

The die area includes the regions required for:

- Core logic
- Memories
- Macros
- I/O structures
- Power distribution
- Routing
- Physical spacing and margins

A simplified representation is:

```text
┌─────────────────────────────┐
│           DIE               │
│                             │
│      ┌───────────────┐      │
│      │     CORE      │      │
│      │               │      │
│      │ Standard      │      │
│      │ Cells +       │      │
│      │ Macros        │      │
│      └───────────────┘      │
│                             │
└─────────────────────────────┘
```

---

* **Core Area:**

The **core** is the main internal region where standard cells and other implementation structures are placed.

The core is generally surrounded by I/O and other peripheral structures depending on the chip architecture.

Core dimensions are selected based on:

- Required logic area
- Macro area
- Routing requirements
- Power requirements
- Placement utilization
- Timing requirements
- Future optimization margin

---

* **Aspect Ratio:**

Aspect ratio describes the relationship between the width and height of the core or die.

```text
Aspect Ratio = Width / Height
```

For example:

```text
Width = 1000 µm
Height = 1000 µm

Aspect Ratio = 1000 / 1000
             = 1
```

An aspect ratio of `1` represents a square shape.

The selected aspect ratio should provide a suitable physical organization for the design.

---

* **Utilization:**

Utilization represents how much of the available core area is occupied by cells.

A simplified expression is:

```text
Utilization =
Standard Cell Area / Available Core Area
```

For example, if:

```text
Standard Cell Area = 60,000 µm²
Core Area          = 100,000 µm²
```

then:

```text
Utilization = 60%
```

Higher utilization can reduce area but may leave less space for routing and optimization.

Very high utilization can increase:

- Routing congestion
- Timing difficulty
- Placement difficulty
- Optimization difficulty

Therefore, suitable utilization is important.

---

* **Macro Placement:**

Macros are relatively large physical blocks that are treated differently from ordinary standard cells.

Examples include:

- SRAM
- ROM
- Large memories
- Analog blocks
- PLLs
- Large IP blocks
- Specialized hardware blocks

Example:

```text
┌──────────────────────────────────┐
│                                  │
│   ┌─────────┐      ┌─────────┐  │
│   │ SRAM    │      │ SRAM    │  │
│   │ Macro   │      │ Macro   │  │
│   └─────────┘      └─────────┘  │
│                                  │
│       Standard Cell Area         │
│                                  │
└──────────────────────────────────┘
```

Macro placement is important because poor macro locations can create long connections and routing congestion.

---

* **Macro Placement Considerations:**

When placing macros, designers consider:

- Connectivity between macros.
- Connection to standard-cell logic.
- Routing resources.
- Timing-critical paths.
- Power connections.
- Clock connections.
- Available channels.
- Congestion.
- Blockages.
- Physical spacing.

Macros that communicate heavily may need to be positioned appropriately to reduce unnecessary wirelength.

---

* **I/O Planning:**

I/O planning determines the physical locations of input/output connections.

Typical I/O structures may include:

- Input pads
- Output pads
- Bidirectional pads
- Power pads
- Ground pads
- Clock inputs
- Reset inputs

Simplified representation:

```text
       Input                  Output
         ↓                      ↓
┌────────────────────────────────────┐
│              CHIP                  │
│                                    │
│              CORE                  │
│                                    │
└────────────────────────────────────┘
 ↑                                  ↑
Power / Ground                  I/O
```

I/O locations must consider connectivity, timing, package requirements, power distribution, and routing.

---

* **Power Planning:**

Power planning establishes how power and ground will be distributed throughout the chip.

Typical concepts include:

- Power rings
- Power straps
- Power grids
- Power rails
- VDD
- VSS / Ground

Conceptually:

```text
        VDD Power Ring
┌──────────────────────────────┐
│ ════════════════════════════ │
│ ║      Power Straps       ║ │
│ ║                          ║ │
│ ║   Standard Cell Region   ║ │
│ ║                          ║ │
│ ║══════════════════════════║ │
│ ════════════════════════════ │
└──────────────────────────────┘
        VSS / Ground
```

The exact power distribution architecture depends on the technology and design requirements.

---

* **Power Integrity:**

A good floor plan should support reliable power delivery.

Poor power planning can cause problems such as:

- IR drop
- Electromigration
- Local voltage variations
- Power distribution problems

Therefore, power planning is considered during floor planning rather than being treated as an isolated final activity.

---

* **Routing Resources:**

Floor planning must leave sufficient physical resources for routing.

Connections require:

- Metal layers
- Vias
- Routing tracks
- Routing channels

Poor floor planning can cause:

```text
High Routing Demand
        ↓
Congestion
        ↓
Longer Routes
        ↓
Higher Delay
        ↓
Timing Problems
```

Therefore, routing feasibility is an important floor-planning consideration.

---

* **Congestion:**

Congestion occurs when the demand for routing resources becomes too high for the available routing capacity.

Example:

```text
Routing Demand
       ████████████████
       ████████████████
       ████████████████

Available Routing
       ████████████

Demand > Capacity
       ↓
   Congestion
```

Congestion can lead to:

- Routing failures
- Longer wires
- Increased delay
- Timing violations
- More difficult optimization

Floor planning attempts to reduce severe congestion before detailed placement and routing.

---

* **Wirelength:**

Physical distance between connected blocks affects routing and timing.

For example:

```text
Poor Placement:

Block A ───────────────────────── Block B
              Long Wire

Better Placement:

Block A ───── Block B
          Shorter Wire
```

Longer interconnect can increase:

- Resistance
- Capacitance
- Propagation delay
- Dynamic power

Therefore, connectivity should be considered during floor planning.

---

* **Timing Considerations:**

Floor planning can affect timing because physical distance influences interconnect delay.

Simplified path:

```text
Register
   ↓
Logic
   ↓
Wire
   ↓
Logic
   ↓
Register
```

If the physical distance becomes large, the wire contribution to delay can increase.

Therefore:

```text
Floor Plan
    ↓
Physical Distance
    ↓
Wirelength
    ↓
Parasitics
    ↓
Timing
```

This is why physical design concepts are relevant even to RTL designers.

---

* **Placement Blockages:**

A blockage is a physical region where certain types of placement are restricted.

Blockages can be used to:

- Reserve space for routing.
- Protect macro regions.
- Control standard-cell density.
- Reduce congestion.
- Reserve space for future structures.

Conceptually:

```text
┌───────────────────────────────┐
│ Standard Cell Region          │
│                               │
│      ┌───────────────┐        │
│      │   BLOCKAGE    │        │
│      │   No Cells    │        │
│      └───────────────┘        │
│                               │
└───────────────────────────────┘
```

---

* **Placement Density:**

Placement density indicates how concentrated cells are within a region.

If too many cells are concentrated in one area:

```text
High Cell Density
       ↓
Less Routing Space
       ↓
Congestion
       ↓
Timing / Routing Problems
```

Therefore, floor planning aims for a balanced physical distribution.

---

* **Floor Planning and PPA:**

Floor planning has a direct influence on:

### Power

Poor placement can increase wirelength and switching-related power.

### Performance

Longer physical paths can increase interconnect delay.

### Area

Poor floor plans may require additional area to provide routing and placement resources.

Therefore:

```text
Floor Plan
     ↓
Wirelength + Congestion + Placement
     ↓
Timing + Power + Area
     ↓
PPA
```

---

* **Floor Planning Inputs:**

Typical inputs include:

- Synthesized gate-level netlist
- Technology libraries
- Physical libraries
- Design constraints
- Macro information
- I/O requirements
- Power requirements
- Clock requirements
- Floor-planning constraints

These inputs help determine the initial physical organization.

---

* **Floor Planning Outputs:**

Typical outputs include:

- Die dimensions
- Core dimensions
- Aspect ratio
- Macro locations
- I/O locations
- Placement regions
- Blockages
- Power planning structure
- Initial physical database
- Early congestion information

These outputs are used by subsequent physical implementation stages.

---

* **Floor Planning vs Placement:**

| Floor Planning | Placement |
|---|---|
| Determines overall physical organization | Determines locations of individual standard cells |
| Places major macros | Places standard cells and other cells |
| Defines core/die structure | Optimizes detailed cell locations |
| Plans I/O and power structure | Optimizes timing, congestion, and wirelength |
| Early physical-design stage | Follows floor planning |

Simplified:

```text
Floor Planning
      ↓
Macro / I/O / Core Organization
      ↓
Placement
      ↓
Standard Cell Locations
```

---

* **Floor Planning vs Routing:**

| Floor Planning | Routing |
|---|---|
| Plans physical organization | Creates physical connections |
| Decides macro locations | Connects pins using metal and vias |
| Defines regions and resources | Performs actual wire implementation |
| Considers congestion | Resolves routing connections |

---

* **Floor Planning vs Logic Synthesis:**

| Logic Synthesis | Floor Planning |
|---|---|
| Converts RTL to gate-level netlist | Organizes the netlist physically |
| Primarily logical implementation | Physical implementation |
| Uses timing/area/power constraints | Uses physical and implementation constraints |
| Produces gate-level netlist | Produces initial physical organization |
| Technology mapping is central | Macro/core/I/O/power planning is central |

---

* **RTL Relevance:**

Although floor planning is primarily a Physical Design activity, an RTL Design Engineer should understand it because RTL decisions influence the physical implementation.

For example:

```text
RTL Architecture
      ↓
Logic Structure
      ↓
Number / Size of Registers and Logic
      ↓
Physical Area
      ↓
Placement
      ↓
Wirelength / Congestion
      ↓
Timing / Power
```

RTL designers should therefore understand:

- Why large blocks matter physically.
- Why hierarchy can matter.
- Why excessive logic can increase area.
- Why long datapaths can create timing challenges.
- Why high fanout can create implementation challenges.
- Why PPA-aware RTL coding is important.

---

* **Common Floor Planning Problems:**

### 1. Poor Macro Placement

Can cause long connections and congestion.

### 2. Excessive Utilization

Can leave insufficient space for routing.

### 3. Poor I/O Placement

Can create unnecessary routing and timing challenges.

### 4. Routing Congestion

Can make detailed routing difficult or impossible.

### 5. Poor Power Distribution

Can lead to power integrity problems.

### 6. Long Critical Connections

Can increase interconnect delay and make timing closure difficult.

### 7. Unbalanced Density

Can create local congestion even when average utilization appears acceptable.

---

* **Best Practices:**

- Understand major block connectivity.
- Place large macros carefully.
- Keep important communicating blocks reasonably close when appropriate.
- Provide sufficient routing resources.
- Avoid unnecessarily high utilization.
- Consider timing-critical paths.
- Plan power distribution early.
- Consider I/O connectivity and package requirements.
- Check congestion during floor-plan refinement.
- Leave sufficient space for later optimization.
- Consider PPA throughout the physical implementation flow.

---

* **Applications:**

Floor planning is used in the physical implementation of:

- ASICs
- SoCs
- CPUs
- GPUs
- Microcontrollers
- DSP processors
- AI accelerators
- Networking chips
- Memory-intensive designs
- Communication ICs
- Automotive ICs
- Consumer electronics ICs
- High-performance computing chips

---

* **Advantages:**

- Provides an organized physical structure.
- Helps control chip and core dimensions.
- Supports better macro organization.
- Helps reduce routing congestion.
- Supports timing optimization.
- Supports power distribution planning.
- Helps improve physical implementation quality.
- Provides a foundation for placement and routing.
- Helps achieve better PPA.

---

* **Limitations:**

- A floor plan cannot guarantee final timing closure.
- Early estimates may change after placement and routing.
- Poor assumptions can require floor-plan iteration.
- Macro-heavy designs can be physically challenging.
- Congestion may appear later even when the initial floor plan looks acceptable.
- Floor planning depends on technology, design constraints, and architecture.

---

* **Real-World Example:**

Consider a processor subsystem containing:

```text
CPU Core
   +
SRAM
   +
Cache
   +
Bus Controller
   +
Peripheral Controllers
```

A simplified floor plan could organize the large memories near the logic that accesses them:

```text
┌──────────────────────────────────────┐
│                CHIP                  │
│                                      │
│  ┌───────────┐     ┌─────────────┐  │
│  │   SRAM    │     │    Cache    │  │
│  │   Macro   │     │    Macro    │  │
│  └───────────┘     └─────────────┘  │
│          │               │           │
│          └───────┬───────┘           │
│                  │                   │
│          ┌───────▼───────┐           │
│          │    CPU Core   │           │
│          └───────┬───────┘           │
│                  │                   │
│          ┌───────▼────────┐          │
│          │ Bus / Peripheral│         │
│          │    Logic        │         │
│          └─────────────────┘         │
│                                      │
└──────────────────────────────────────┘
```

The actual placement would be determined using detailed physical-design analysis and tool optimization.

---

* **Key Points:**

- Floor Planning is an early stage of Physical Design.
- It determines the initial physical organization of the chip.
- Important decisions include **die size, core size, aspect ratio, macro placement, I/O placement, and power planning**.
- Macro placement has a strong influence on routing and timing.
- Utilization represents how much of the available core area is occupied by cells.
- Very high utilization can increase congestion.
- Poor floor planning can increase wirelength and delay.
- Power planning is considered during floor planning.
- Congestion occurs when routing demand exceeds available routing resources.
- Floor planning influences **Power, Performance, and Area (PPA)**.
- Placement follows floor planning.
- Routing follows placement and clock-tree implementation in the typical flow.
- Floor planning does not guarantee final timing closure.
- RTL designers should understand floor planning because RTL architecture can influence physical implementation.

---

* **Interview Questions:**

### 1. What is Floor Planning?

Floor Planning is the process of determining the initial physical organization of a chip, including core dimensions, macro locations, I/O locations, and power planning.

### 2. Where does Floor Planning occur?

It occurs after synthesis and before detailed placement in a typical ASIC physical-design flow.

### 3. What is the difference between die and core?

The die is the overall physical semiconductor area, while the core is the main internal region used for implementing the design logic and related structures.

### 4. What is aspect ratio?

Aspect ratio is the ratio of width to height of the die or core.

```text
Aspect Ratio = Width / Height
```

### 5. What is utilization?

Utilization represents the fraction of available core area occupied by standard-cell logic, usually expressed as a percentage.

### 6. Why is macro placement important?

Poor macro placement can increase wirelength, routing congestion, and timing problems.

### 7. What is congestion?

Congestion occurs when routing demand exceeds the available routing resources in a physical region.

### 8. How does floor planning affect timing?

Floor planning affects physical distances between connected blocks. Longer interconnects can increase parasitic delay and negatively affect timing.

### 9. Why is power planning performed during floor planning?

Because the physical power-distribution structure must provide reliable power and ground connections throughout the design.

### 10. What are typical floor-planning inputs?

Typical inputs include the synthesized netlist, technology information, physical libraries, design constraints, macro information, I/O requirements, and power requirements.

### 11. What are typical floor-planning outputs?

Typical outputs include core/die dimensions, macro locations, I/O locations, placement regions, blockages, and initial power-distribution structures.

### 12. What is the difference between floor planning and placement?

Floor planning determines the overall physical organization and major block locations, while placement determines detailed locations of standard cells and other implementation cells.

### 13. Can poor floor planning cause timing violations?

Yes. Poor macro placement, excessive wirelength, congestion, and poor physical organization can increase delay and contribute to timing violations.

### 14. Why should an RTL designer know about floor planning?

Because RTL architecture and coding decisions influence logic size, connectivity, timing, and area, which eventually affect physical implementation.

### 15. Does floor planning complete physical design?

No. It is only an early physical-design stage. Placement, CTS, routing, extraction, timing analysis, physical verification, and signoff still follow.

---

* **Quick Revision:**

```text
Gate-Level Netlist
        ↓
Floor Planning
        ↓
 ┌──────────────────────┐
 │ Die / Core Size      │
 │ Aspect Ratio         │
 │ Macro Placement      │
 │ I/O Planning         │
 │ Power Planning       │
 │ Placement Regions    │
 │ Blockages            │
 └──────────────────────┘
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
```

### Remember:

```text
Floor Planning = Physical Organization

Core       → Main implementation region
Macro      → Large physical block
Utilization→ Used core area / available core area
Congestion → Routing demand > routing capacity
Aspect Ratio → Width / Height
PPA        → Power + Performance + Area
```

---

* **Summary:**  
Floor Planning is an important early stage of Physical Design that establishes the physical organization of an integrated circuit. It determines the die and core dimensions, aspect ratio, macro and I/O locations, placement regions, and initial power-distribution structure. A good floor plan helps control wirelength, congestion, timing, power, and area and provides a strong foundation for placement and routing. For an RTL Design Engineer, understanding floor planning helps connect RTL architecture and coding decisions with their eventual physical implementation impact.

---

* **References:**

- Neso Academy — VLSI and Digital IC Design concepts.
- All About Electronics — Digital Electronics and VLSI-related concepts.
- Weste & Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*.
- Jan M. Rabaey, Anantha Chandrakasan, Borivoje Nikolić — *Digital Integrated Circuits: A Design Perspective*.
- Neil H. E. Weste, David Money Harris — *CMOS VLSI Design*.
