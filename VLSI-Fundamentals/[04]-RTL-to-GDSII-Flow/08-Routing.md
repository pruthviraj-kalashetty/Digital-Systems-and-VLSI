# **Routing**

* **Overview:**

Routing is a major **Physical Design** stage in which physical connections are created between placed standard cells, macros, clock elements, and I/O structures using available **metal layers and vias**.

After placement, cells have physical locations, but the required electrical connections still need to be physically created. Routing converts the logical connectivity of the design into actual physical interconnections while satisfying timing, congestion, signal integrity, and manufacturing rules.

---

* **Definition:**

Routing is the process of determining and creating physical **metal and via connections** between the pins of cells and other circuit elements according to the synthesized netlist and physical design constraints.

The main objective is to achieve complete and reliable connectivity while meeting:

- Timing requirements
- Routing constraints
- Design rules
- Signal integrity requirements
- Power requirements
- Congestion limits
- Manufacturability requirements

---

* **Why is it needed?*

After placement, the physical locations of cells are known, but their connections have not yet been completely created.

For example:

```text
Before Routing:

+-------+       +-------+
|  FF1  |       |  FF2  |
+-------+       +-------+

     Logical Connection
           |
           v
        FF1 → FF2
```

Routing creates the actual physical path:

```text
After Routing:

+-------+                         +-------+
|  FF1  |                         |  FF2  |
+---+---+                         +---+---+
    |                                 |
    +========= Metal ================+
              |
            Via
              |
          Metal Layer
```

Routing is therefore required to:

- Create physical connectivity
- Connect standard cells and macros
- Connect clock networks
- Connect data signals
- Provide power connections
- Satisfy design rules
- Control wirelength
- Reduce congestion
- Support timing closure
- Enable final physical verification

---

* **Working Principle:**

The routing process takes the placed design and determines physical paths for all required nets.

A simplified flow is:

```text
Placed Design
      |
      v
Routing Preparation
      |
      v
Global Routing
      |
      v
Detailed Routing
      |
      v
Design Rule Checking
      |
      v
Parasitic Extraction
      |
      v
Timing / Power Analysis
      |
      v
Optimization
      |
      v
Final Routed Design
```

The router considers:

- Cell locations
- Pin locations
- Available metal layers
- Routing tracks
- Vias
- Design rules
- Timing constraints
- Congestion
- Signal integrity
- Power requirements

The router must create a physical path between the source and destination pins of each net without causing unacceptable violations.

---

* **Routing Resources:**

Modern ICs use multiple metal layers for interconnections.

A simplified example:

```text
          Metal Layer 4
------------------------------------>

          Metal Layer 3
<------------------------------------

          Metal Layer 2
------------------------------------>

          Metal Layer 1
<------------------------------------

                |
               Via
                |
                |
             Lower Layer
```

Different metal layers may have preferred routing directions.

For example:

```text
Metal Layer 1 → Horizontal
Metal Layer 2 → Vertical
Metal Layer 3 → Horizontal
Metal Layer 4 → Vertical
```

The exact layer structure and preferred directions depend on the technology.

---

* **Metal Layers:**

Metal layers are conductive layers used to create physical interconnections.

A design may contain multiple metal layers such as:

```text
M1
M2
M3
M4
M5
...
Mn
```

Lower metal layers are commonly used for local connections, while higher metal layers can be useful for longer connections and important global networks.

The exact usage depends on the process technology and routing strategy.

---

* **Via:**

A via is a vertical connection that electrically connects two metal layers.

Example:

```text
Metal 3
====================
        |
       VIA
        |
Metal 2
====================
```

Vias allow a signal to change from one metal layer to another.

Without vias, signals would generally be restricted to a single metal layer.

---

* **Routing Types:**

Routing is commonly divided into:

1. Global Routing
2. Detailed Routing

---

* **Global Routing:**

Global routing determines the approximate routing paths and resources required for each net.

It does not usually create the final exact physical geometry.

Simplified example:

```text
Source
  |
  |       Routing Region
  v
+---+---+---+---+
|   |   |   |   |
+---+---+---+---+
|   |   |   |   |
+---+---+---+---+
|   |   |   |   |
+---+---+---+---+
              |
              v
           Destination
```

Global routing focuses on:

- Routing paths
- Routing resources
- Congestion
- Approximate wirelength
- Timing considerations

---

* **Detailed Routing:**

Detailed routing converts the global routing plan into actual physical wires and vias.

It must follow detailed manufacturing and design rules.

```text
Global Route
     |
     v
Detailed Route
     |
     v
Exact Metal + Via Geometry
```

Detailed routing checks issues such as:

- Minimum spacing
- Minimum width
- Via rules
- Layer restrictions
- Metal overlap
- Design-rule compliance
- Connectivity

---

* **Routing Congestion:**

Routing congestion occurs when too many nets require routing resources in the same physical region.

Example:

```text
Available Routing Tracks:

====================
====================
====================

Required Connections:

||||||||||||||||||||
||||||||||||||||||||
||||||||||||||||||||
||||||||||||||||||||
```

If routing demand becomes greater than available resources, congestion occurs.

High congestion can cause:

- Routing failures
- Longer detours
- Increased wirelength
- Increased delay
- Timing violations
- Higher power
- More design-rule violations

Therefore, congestion must be controlled during placement and routing.

---

* **Routing and Wirelength:**

The physical distance of a routed connection affects its electrical characteristics.

Longer wires generally introduce:

- Higher resistance
- Higher capacitance
- Greater propagation delay
- Higher dynamic power
- Greater signal integrity concerns

Simplified relationship:

```text
Longer Wire
     |
     +----> Higher R
     |
     +----> Higher C
     |
     +----> Higher Delay
     |
     +----> Potentially Higher Power
```

Therefore, routing optimization attempts to avoid unnecessary wirelength.

---

* **Routing and Timing:**

Routing has a direct impact on timing because physical wires contribute resistance and capacitance.

A simplified timing path is:

```text
Launch FF
    |
    v
Logic
    |
    v
Routing
    |
    v
Capture FF
```

The total path delay includes both logic delay and interconnect delay.

A simplified relationship is:

```text
Total Path Delay
      =
Logic Delay + Interconnect Delay
```

After routing, more accurate parasitic information can be extracted and used for timing analysis.

---

* **Routing Parasitics:**

Physical wires introduce parasitic resistance and capacitance.

```text
Driver ---- R ---- R ---- Receiver
             |     |
             C     C
             |     |
            GND   GND
```

These parasitics affect:

- Signal delay
- Transition time
- Dynamic power
- Signal integrity
- Timing margins

Therefore, routing and parasitic extraction are closely connected.

---

* **Signal Integrity:**

Routing can also affect signal integrity.

Important effects include:

- Crosstalk
- Coupling capacitance
- Noise
- Delay variation
- Transition degradation

When neighboring wires switch, electromagnetic coupling can influence each other.

Simplified example:

```text
Aggressor
======================>

        Coupling

Victim
======================>
```

The aggressor can affect the victim signal through coupling capacitance.

Routing tools may therefore adjust:

- Wire spacing
- Routing layers
- Shielding
- Buffering
- Wire sizing

to improve signal integrity where required.

---

* **Routing of Clock Signals:**

Clock routing is particularly important because the clock connects a large number of sequential elements.

```text
              Clock Source
                   |
                   v
              Clock Network
              /     |     \
             /      |      \
           FF1     FF2     FF3
```

Clock routing must consider:

- Clock skew
- Clock latency
- Transition
- Fanout
- Clock power
- Timing

Clock Tree Synthesis creates the clock distribution structure before final routing, and clock routing physically implements the required connections.

---

* **Routing of Power Networks:**

Power and ground networks also require physical metal connections.

Simplified structure:

```text
        VDD
========================
 |      |      |      |
 |      |      |      |
========================
        Power Rails

------------------------
        VSS
------------------------
```

Power routing must provide reliable supply connections while controlling:

- IR drop
- Electromigration
- Current density
- Voltage variation

Power routing is therefore different from ordinary signal routing, although both use physical interconnect resources.

---

* **Routing Constraints:**

Routing must satisfy several constraints.

| Constraint | Purpose |
|---|---|
| Minimum Width | Prevent manufacturing problems |
| Minimum Spacing | Avoid shorts and manufacturing violations |
| Via Rules | Ensure reliable layer transitions |
| Routing Direction | Improve routing efficiency |
| Layer Restrictions | Control where nets can route |
| Timing Constraints | Meet setup/hold requirements |
| Fanout Constraints | Control excessive loading |
| Signal Integrity | Reduce noise/crosstalk |
| Congestion | Maintain routability |
| Power Constraints | Maintain reliable power delivery |

---

* **Routing Blockages:**

Some physical regions cannot be used for normal signal routing.

Examples include:

- Macros
- IP blocks
- Reserved regions
- Power structures
- Keep-out areas
- Special routing regions

Example:

```text
+--------------------------------+
|                                |
|       +-------------+          |
|       |    MACRO    |          |
|       |             |          |
|       +-------------+          |
|                                |
|   Routing Area                 |
|                                |
+--------------------------------+
```

The router must route around restricted regions.

---

* **Routing Optimization:**

After routing, the design may require optimization.

Common optimization techniques include:

- Wirelength reduction
- Buffer insertion
- Cell resizing
- Layer optimization
- Route restructuring
- Congestion reduction
- Crosstalk reduction
- Timing optimization
- Transition improvement

The goal is to obtain a routed design that satisfies required constraints.

---

* **Routing and Timing Closure:**

Routing can reveal timing problems that were not fully visible earlier because actual interconnect parasitics become more accurate after physical implementation.

Typical flow:

```text
Placement
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
   +----> Timing Pass
   |
   +----> Timing Violation
                |
                v
            Optimization
                |
                v
             Re-route
```

Timing closure may involve:

- Reducing critical-path delay
- Improving cell drive strength
- Adding buffers
- Optimizing placement
- Improving routing
- Adjusting clock distribution
- Reducing congestion

---

* **Routing Reports:**

Important routing-related reports can include:

- Routing completion
- Number of routed nets
- Wirelength
- Via count
- Congestion
- Design-rule violations
- Timing
- Transition
- Capacitance
- Signal integrity
- Power

A good routed design should have complete connectivity and acceptable physical, timing, and electrical characteristics.

---

* **Routing Violations:**

Common routing problems include:

### 1. Short

Two electrically different nets become unintentionally connected.

```text
Net A =========
              X
Net B =========
```

### 2. Open

A required connection is incomplete.

```text
Net A =========     ========= Net B
                 GAP
```

### 3. Spacing Violation

Two wires are too close according to technology rules.

### 4. Width Violation

A metal segment does not satisfy the required minimum width.

### 5. Via Violation

A via arrangement violates technology-specific rules.

### 6. Antenna Violation

Long metal structures can accumulate charge during manufacturing and potentially damage sensitive gate structures.

Routing tools may use techniques such as antenna diodes, layer changes, or route adjustments to address antenna problems.

---

* **Routing Flow in Physical Design:**

```text
Synthesized Netlist
        |
        v
Floor Planning
        |
        v
Placement
        |
        v
Clock Tree Synthesis
        |
        v
Routing
   |         |
   v         v
Global     Detailed
Routing    Routing
   \         /
    \       /
     v     v
   Routed Design
        |
        v
Parasitic Extraction
        |
        v
Timing / Power Analysis
        |
        v
Physical Verification
        |
        v
Signoff
```

---

* **Routing Inputs:**

Typical routing inputs include:

- Placed gate-level netlist
- Floorplan
- Placement database
- Clock tree information
- Technology files
- Physical libraries
- Routing rules
- Timing constraints
- Power information
- Design-rule information
- Routing blockages

---

* **Routing Outputs:**

Typical outputs include:

- Routed physical database
- Metal geometries
- Via structures
- Routing information
- Connectivity information
- Routing reports
- Congestion reports
- Design-rule reports
- Timing information
- Data required for parasitic extraction and later signoff

---

* **Routing vs Placement:**

| Placement | Routing |
|---|---|
| Determines where cells are located | Determines how cells are physically connected |
| Works mainly with cell locations | Works mainly with metal and vias |
| Optimizes location and density | Optimizes physical connections |
| Controls wirelength indirectly | Creates actual interconnects |
| Precedes routing | Follows placement |
| Important for congestion | Directly resolves routing demand |

---

* **Routing vs Clock Tree Synthesis:**

| Routing | Clock Tree Synthesis |
|---|---|
| Routes signal and other required nets | Builds and optimizes clock distribution |
| Handles data connections and other networks | Primarily focuses on clock networks |
| Considers congestion and physical rules | Strongly focuses on skew, latency and clock transition |
| Uses metal and vias | Uses clock buffers and physical clock connections |
| Part of physical implementation | Specialized clock implementation stage |

---

* **Routing vs Parasitic Extraction:**

| Routing | Parasitic Extraction |
|---|---|
| Creates physical interconnections | Calculates electrical parasitics from physical interconnections |
| Uses metal and vias | Extracts resistance/capacitance information |
| Produces routed geometry | Produces parasitic data |
| Enables physical connectivity | Enables more accurate timing/power analysis |

---

* **Routing and PPA:**

Routing directly affects **Power, Performance, and Area (PPA)**.

### Power

Longer wires and larger capacitance can increase dynamic power.

### Performance

Wire resistance and capacitance contribute to interconnect delay.

### Area

Routing requires physical routing resources and may require additional spacing or optimization cells.

Therefore:

```text
Routing
   |
   +----> Wirelength
   |
   +----> Capacitance
   |
   +----> Resistance
   |
   +----> Delay
   |
   +----> Power
   |
   +----> Congestion
   |
   +----> PPA
```

---

* **RTL Relevance:**

Routing is a Back-End/Physical Design activity, but RTL designers should understand its effects.

RTL architecture influences:

```text
RTL
 |
 v
Logic Structure
 |
 v
Cell Count + Connectivity
 |
 v
Placement
 |
 v
Wirelength + Congestion
 |
 v
Routing
 |
 v
Parasitics
 |
 v
Timing + Power
```

RTL decisions can therefore influence routing quality.

For example:

- Excessive logic can increase cell count.
- High-fanout control signals can require additional buffering.
- Poorly structured datapaths can create long critical connections.
- Large mux structures can increase routing demand.
- Wide buses can increase routing resources.
- Unnecessary switching can increase power.

An RTL designer does not perform detailed physical routing, but should understand how RTL architecture can affect physical implementation.

---

* **Common Routing Problems:**

1. Routing congestion
2. Incomplete routing
3. Shorts
4. Opens
5. Design-rule violations
6. Excessive wirelength
7. High via count
8. Timing violations
9. High capacitance
10. Poor signal integrity
11. Antenna violations
12. Routing resource limitations

---

* **Best Practices:**

- Consider physical implications of RTL architecture.
- Avoid unnecessary logic and excessive fanout.
- Understand timing-critical paths.
- Keep interfaces and datapaths well structured.
- Consider congestion during physical implementation.
- Use appropriate routing constraints.
- Check design-rule violations.
- Analyze timing after routing.
- Analyze extracted parasitics.
- Check signal integrity where required.
- Optimize routing before signoff.
- Maintain complete connectivity.

---

* **Applications:**

Routing is required in almost every modern digital IC implementation, including:

- CPUs
- GPUs
- Microcontrollers
- SoCs
- DSP processors
- AI accelerators
- Memory controllers
- Communication controllers
- Network processors
- UART/SPI/I2C peripherals
- DMA controllers
- FPGA-related physical implementation flows
- ASIC designs
- High-performance digital systems

---

* **Advantages:**

- Creates physical connectivity between circuit elements.
- Enables the design to become physically implementable.
- Allows timing and power analysis with physical interconnect effects.
- Provides the physical database required for later verification and signoff.
- Helps optimize wirelength and routing resources.
- Supports final physical implementation.

---

* **Limitations:**

- Routing can become highly complex for large designs.
- Congestion can make routing difficult or impossible.
- Long interconnects can increase delay and power.
- Routing can introduce signal-integrity challenges.
- Physical design rules restrict available routing resources.
- Routing optimization can require multiple iterations.
- Timing closure may require repeated placement, routing, and optimization.

---

* **Real-World Example:**

Consider a processor pipeline:

```text
Instruction Register
        |
        v
     Decoder
        |
        v
   Register File
        |
        v
       ALU
        |
        v
  Result Register
```

After placement, these blocks and their internal cells have physical locations.

Routing creates the actual physical connections between:

- Registers
- ALU logic
- Multiplexers
- Control logic
- Data buses
- Clock network
- Power network

If the ALU result path becomes physically long, its interconnect delay can increase.

Therefore:

```text
RTL Datapath
     |
     v
Synthesized Logic
     |
     v
Placement
     |
     v
Physical Distance
     |
     v
Routing
     |
     v
Wire Parasitics
     |
     v
Timing
```

This demonstrates why RTL architecture and physical implementation are connected.

---

* **Key Points:**

- Routing is a major Physical Design stage.
- It creates physical connections using metal layers and vias.
- Global routing determines approximate paths and resource usage.
- Detailed routing creates final physical geometries.
- Routing must satisfy technology and design rules.
- Congestion occurs when routing demand exceeds available resources.
- Wire resistance and capacitance affect timing and power.
- Routing can affect signal integrity through coupling and crosstalk.
- Clock routing has special timing requirements.
- Power networks also require physical routing.
- Parasitic extraction follows routing to obtain more accurate electrical information.
- Routing quality directly affects PPA.
- RTL architecture can indirectly influence routing complexity.
- Routing must be clean enough for physical verification and signoff.

---

* **Interview Questions:**

### 1. What is routing in Physical Design?

Routing is the process of creating physical metal and via connections between the pins of cells and other circuit elements according to the netlist and physical constraints.

### 2. Why is routing required?

Placement determines where cells are located, but it does not create all physical interconnections. Routing creates the required physical connections.

### 3. What are the two major types of routing?

The two major types are:

1. Global Routing
2. Detailed Routing

### 4. What is global routing?

Global routing determines approximate routing paths and estimates the required routing resources for nets.

### 5. What is detailed routing?

Detailed routing creates the actual metal and via geometries while following detailed technology and design rules.

### 6. What is a via?

A via is a vertical electrical connection between different metal layers.

### 7. What is routing congestion?

Routing congestion occurs when the demand for routing resources in a region becomes too high compared with the available resources.

### 8. How does routing affect timing?

Routing introduces resistance and capacitance. These interconnect parasitics contribute to signal delay and can therefore affect setup and hold timing.

### 9. How does routing affect power?

Longer wires generally have higher capacitance, increasing the energy required to charge and discharge the interconnect.

### 10. What is parasitic extraction?

Parasitic extraction is the process of obtaining electrical parasitic information, mainly resistance and capacitance, from the physical implementation.

### 11. What is the difference between placement and routing?

Placement determines the physical locations of cells. Routing creates the physical connections between those cells.

### 12. What is a routing violation?

A routing violation occurs when the physical implementation violates a technology or design requirement, such as minimum spacing, width, via rules, or connectivity.

### 13. What is a short?

A short occurs when two electrically different nets become unintentionally connected.

### 14. What is an open?

An open occurs when a required electrical connection is incomplete.

### 15. What is antenna violation?

An antenna violation occurs when a manufacturing-related charge accumulation condition on a long interconnect can potentially damage a transistor gate during fabrication.

### 16. How does routing affect PPA?

Routing affects:

- **Power** through wire capacitance and switching
- **Performance** through interconnect delay
- **Area** through routing resources and spacing requirements

### 17. Why is routing important for timing closure?

After routing, physical interconnect parasitics become more accurate. These parasitics can change path delay and reveal timing violations that require optimization.

### 18. Does an RTL designer need to know routing?

An RTL designer does not normally perform detailed routing, but understanding routing helps explain how RTL architecture can influence wirelength, congestion, timing, power, and PPA.

### 19. What is signal integrity in routing?

Signal integrity refers to maintaining correct and reliable signal behavior despite effects such as noise, crosstalk, coupling, resistance, capacitance, and transition degradation.

### 20. What happens after routing?

A simplified flow is:

```text
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

---

* **Quick Revision:**

```text
Routing
   ↓
Creates Physical Connections
   ↓
Uses Metal + Vias
   ↓
Global Routing
   ↓
Detailed Routing
   ↓
Checks Congestion + Design Rules
   ↓
Parasitic Extraction
   ↓
Timing / Power Analysis
   ↓
Optimization
   ↓
Physical Verification
   ↓
Signoff
```

**Remember:**

```text
Placement = Where are the cells?

Routing = How are the cells physically connected?

Parasitic Extraction = What electrical effects do those physical connections create?
```

---

* **Summary:**

Routing is a critical Physical Design stage that converts logical connectivity into physical interconnections using metal layers and vias. It includes global and detailed routing and must satisfy routing resources, design rules, timing, congestion, signal integrity, and power requirements.

The physical wires created during routing introduce resistance and capacitance, which affect delay, power, and signal integrity. After routing, parasitic extraction provides more accurate electrical information for timing and power analysis.

For an RTL Design Engineer, detailed routing is a Back-End activity, but understanding routing is important because **RTL architecture influences logic structure, connectivity, placement, congestion, wirelength, timing, power, and ultimately PPA.**

---

* **References:**

1. Neso Academy — VLSI / Physical Design concepts  
2. All About Electronics — VLSI and Digital Electronics concepts  
3. Neil H. E. Weste and David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*  
4. Jan M. Rabaey, Anantha Chandrakasan, and Borivoje Nikolić — *Digital Integrated Circuits: A Design Perspective*  
5. Synthesis and Physical Design concepts from standard ASIC implementation methodologies
