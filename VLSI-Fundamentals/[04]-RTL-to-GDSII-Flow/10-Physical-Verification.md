# **Physical Verification**

* **Overview:**

Physical Verification is the process of checking the physical layout of an integrated circuit to ensure that it satisfies **manufacturing rules, electrical connectivity requirements, and physical design constraints** before final signoff and tapeout.

It verifies that the implemented layout is physically valid and that the physical implementation correctly represents the intended circuit.

The major physical verification checks include:

- Design Rule Checking (DRC)
- Layout Versus Schematic (LVS)
- Antenna checking
- Electrical Rule Checking (ERC)
- Additional technology- and design-specific signoff checks

---

* **Definition:**

Physical Verification is the process of analyzing the final physical layout of an IC against technology manufacturing rules and the intended circuit connectivity to identify physical, geometric, connectivity, and electrical violations before manufacturing.

A simplified concept is:

```text
RTL
 |
 v
Synthesis
 |
 v
Gate-Level Netlist
 |
 v
Physical Design
 |
 v
Placed + Routed Layout
 |
 v
Physical Verification
 |
 +----> DRC
 |
 +----> LVS
 |
 +----> ERC
 |
 +----> Antenna Checks
 |
 v
Signoff
 |
 v
Tapeout
```

---

* **Why is it needed?**

A design can be logically correct and still contain physical problems that make it difficult or impossible to manufacture correctly.

For example:

```text
Logical Design
      |
      v
Functionally Correct
      |
      v
Physical Layout
      |
      v
Physical Violation
      |
      v
Manufacturing Problem
```

Physical verification is needed to:

- Detect manufacturing-rule violations
- Verify physical connectivity
- Detect unintended shorts
- Detect opens
- Verify layout against the intended netlist
- Check antenna conditions
- Detect electrical rule violations
- Improve manufacturability
- Support signoff
- Reduce the risk of silicon failure

---

* **Working Principle:**

Physical verification compares and analyzes different representations of the design.

A simplified flow is:

```text
Final Layout
     |
     +--------------------+
     |                    |
     v                    v
Geometry Checks       Connectivity Checks
     |                    |
     v                    v
    DRC                  LVS
     |                    |
     +---------+----------+
               |
               v
       Additional Checks
               |
               v
            Signoff
```

The verification tools analyze the physical database and technology rules to determine whether the layout satisfies the required conditions.

---

* **Physical Verification Flow:**

```text
Completed Routing
        |
        v
Design Rule Checking
        |
        v
LVS / Connectivity Verification
        |
        v
Antenna Checking
        |
        v
Electrical Rule Checking
        |
        v
Timing / Power / Signal Integrity Signoff
        |
        v
Final Signoff
        |
        v
Tapeout
```

The exact order and number of checks can vary depending on the technology and design methodology.

---

* **Design Rule Checking (DRC):**

DRC is one of the most important physical verification checks.

DRC verifies whether the physical layout follows the manufacturing rules defined by the semiconductor process.

Examples include:

- Minimum metal width
- Minimum metal spacing
- Minimum via size
- Via spacing
- Metal enclosure
- Layer overlap
- Well spacing
- Diffusion spacing
- Contact rules
- Density rules
- Other technology-specific requirements

Simplified example:

```text
Valid:

====================
<---- Metal ---->


Invalid:

======
    ======
     ^
     |
  Too little
   spacing
```

The actual rules depend on the semiconductor technology.

---

* **Why DRC is Important:**

A layout can be electrically logical but physically impossible to manufacture reliably.

For example:

```text
Logical Connectivity
       |
       v
      PASS
       |
       v
Physical Geometry
       |
       v
      DRC
       |
       v
Violation
```

Therefore:

```text
Logical Correctness ≠ Physical Correctness
```

Both must be verified.

---

* **Common DRC Violations:**

### 1. Minimum Width Violation

A metal or other layout feature is narrower than allowed.

```text
Required:

====================

Too Narrow:

========
```

---

### 2. Minimum Spacing Violation

Two physical features are too close.

```text
Metal A
==========

     <--- insufficient spacing --->

Metal B
==========
```

---

### 3. Via Violation

A via does not satisfy technology-specific size, spacing, or enclosure requirements.

---

### 4. Enclosure Violation

A surrounding layer does not sufficiently enclose another required structure.

---

### 5. Density Violation

The density of certain physical layers does not satisfy manufacturing requirements.

---

* **Layout Versus Schematic (LVS):**

LVS verifies whether the connectivity represented by the physical layout matches the intended circuit representation.

In a digital ASIC flow, the extracted layout connectivity is commonly compared against the intended gate-level netlist.

Simplified concept:

```text
       Gate-Level Netlist
              |
              |
              v
             LVS
              ^
              |
              |
        Extracted Layout
```

The objective is to determine whether the physical implementation represents the intended circuit connectivity.

---

* **LVS Concept:**

Suppose the intended design contains:

```text
A ----> AND ----> Y
B ---->/
```

The physical layout should represent the same connectivity:

```text
A --------+
          |
          v
       AND Cell
          |
          v
Y <-------+
```

If the physical layout accidentally creates:

```text
A --------+
          |
          +------ B
```

or leaves a connection incomplete, LVS can identify the mismatch.

---

* **What LVS Can Detect:**

LVS can identify issues such as:

- Missing connections
- Extra connections
- Shorts
- Opens
- Missing devices/cells
- Extra devices/cells
- Incorrect connectivity
- Incorrect device or cell properties where applicable
- Mismatch between intended and extracted circuit representations

---

* **DRC vs LVS:**

| DRC | LVS |
|---|---|
| Checks physical geometry | Checks circuit connectivity |
| Compares layout against technology rules | Compares extracted layout against intended circuit |
| Finds width/spacing/via violations | Finds opens/shorts/connectivity mismatches |
| Focuses on manufacturability | Focuses on design equivalence/connectivity |
| Answers: “Is the layout physically legal?” | Answers: “Does the layout represent the intended circuit?” |

A simple way to remember:

```text
DRC → Is the layout physically legal?

LVS → Does the layout match the intended circuit?
```

---

* **Antenna Checking:**

Antenna checking identifies manufacturing-related conditions where charge can accumulate on long interconnect structures during fabrication and potentially damage sensitive gate structures.

Simplified concept:

```text
Long Metal
========================================
                     |
                     |
                  Gate
                   |
                  MOS
```

A long conductive structure connected to a gate can create an antenna-related manufacturing concern during certain fabrication steps.

Possible solutions include:

- Antenna diodes
- Layer changes
- Route modification
- Metal segmentation
- Process-specific antenna techniques

The exact solution depends on the technology and design flow.

---

* **Electrical Rule Checking (ERC):**

ERC checks electrical conditions that may not be fully covered by geometric DRC.

Examples can include:

- Improper power connections
- Floating signals
- Invalid connectivity
- Incorrect well/substrate connections
- Power/ground issues
- Electrical configuration problems

ERC rules depend on the technology and verification methodology.

---

* **Shorts and Opens:**

### Short

A short occurs when two nets that should be electrically separate become connected.

```text
Net A =========+
               |
               +========= Net B
```

This can cause incorrect circuit behavior.

### Open

An open occurs when a required connection is incomplete.

```text
Net A ==========      ========== Net B
                GAP
```

This can prevent the intended signal from reaching its destination.

Physical verification helps identify both types of problems.

---

* **Connectivity Verification:**

The physical layout contains many physical shapes:

```text
Metal
Via
Contact
Diffusion
Poly
Well
Standard Cells
Macros
```

These shapes must form the intended electrical connectivity.

A simplified flow is:

```text
Physical Shapes
      |
      v
Layout Extraction
      |
      v
Connectivity Representation
      |
      v
Compare With Intended Netlist
      |
      v
LVS Result
```

---

* **Physical Verification Inputs:**

Typical inputs include:

- Final routed layout
- Gate-level netlist
- Standard-cell libraries
- Technology files
- Design rules
- Physical library information
- Layer definitions
- Extraction rules
- Power and ground information
- Verification rule decks

---

* **Physical Verification Outputs:**

Typical outputs include:

- DRC reports
- LVS reports
- ERC reports
- Antenna reports
- Violation markers
- Connectivity comparison results
- Extracted connectivity information
- Verification logs
- Clean/pass status or violation information

---

* **Verification Rule Deck:**

A rule deck contains technology-specific rules used by physical verification tools.

It defines conditions such as:

```text
Minimum Width
Minimum Spacing
Via Rules
Enclosure Rules
Density Rules
Antenna Rules
Connectivity Rules
```

The exact rules are specific to the semiconductor process technology.

Therefore, physical verification cannot be performed correctly using generic rules alone.

---

* **DRC Violation Debugging:**

When DRC reports a violation, the designer must:

```text
DRC Violation
      |
      v
Locate Violation
      |
      v
Understand Rule
      |
      v
Identify Root Cause
      |
      v
Modify Layout
      |
      v
Re-run DRC
```

Example:

```text
Metal Spacing Violation
        |
        v
Check Nearby Nets
        |
        v
Increase Spacing / Modify Route
        |
        v
Re-run DRC
```

The process may require multiple iterations.

---

* **LVS Debugging:**

A simplified LVS debugging flow is:

```text
LVS Mismatch
      |
      v
Check Report
      |
      v
Identify Mismatch
      |
      +----> Missing Connection
      |
      +----> Extra Connection
      |
      +----> Short
      |
      +----> Open
      |
      +----> Cell / Device Mismatch
      |
      v
Correct Physical Design
      |
      v
Re-run LVS
```

LVS reports should be carefully analyzed rather than simply treating a failure as a generic error.

---

* **Physical Verification and Routing:**

Routing directly affects physical verification.

```text
Placement
   |
   v
CTS
   |
   v
Routing
   |
   v
Physical Geometry
   |
   v
DRC / LVS / Other Checks
```

Routing mistakes can cause:

- Shorts
- Opens
- Spacing violations
- Width violations
- Via violations
- Antenna violations
- Connectivity mismatches

Therefore, routing and physical verification are closely connected.

---

* **Physical Verification and Parasitics:**

After routing, physical geometry can be used to extract parasitic information.

```text
Routed Layout
      |
      v
Parasitic Extraction
      |
      v
Resistance + Capacitance
      |
      v
Timing / Power Analysis
```

Physical verification and parasitic extraction serve different purposes.

```text
Physical Verification
→ Is the physical implementation valid?

Parasitic Extraction
→ What electrical parasitics does the physical implementation contain?
```

---

* **Physical Verification and STA:**

STA checks timing behavior, while physical verification checks physical correctness.

```text
Routed Design
      |
      +--------------------+
      |                    |
      v                    v
Physical Verification     STA
      |                    |
      v                    v
DRC / LVS / ERC        Timing Checks
      |                    |
      +---------+----------+
                |
                v
             Signoff
```

Both are required because:

```text
Timing Clean ≠ Physically Clean

Physically Clean ≠ Timing Clean
```

---

* **Physical Verification and Signoff:**

Physical verification is an important part of final signoff.

A simplified signoff flow is:

```text
Final Routed Design
        |
        v
Physical Verification
        |
        +----> DRC
        |
        +----> LVS
        |
        +----> ERC
        |
        +----> Antenna
        |
        v
Timing Signoff
        |
        v
Power / Signal Integrity Checks
        |
        v
Final Signoff
        |
        v
Tapeout
```

The exact signoff checklist varies by design, technology, and foundry requirements.

---

* **Manufacturability:**

Physical verification helps ensure that the design can be manufactured according to the process technology.

Important manufacturing concerns include:

- Geometric rules
- Layer spacing
- Feature dimensions
- Via reliability
- Pattern density
- Antenna effects
- Process-specific requirements

The goal is not simply to create a logically correct layout, but to create a layout that is physically manufacturable.

---

* **Physical Verification and PPA:**

Physical verification itself is primarily a correctness and manufacturability activity, but fixing violations can influence PPA.

For example:

```text
DRC Fix
  |
  +----> Additional Spacing
  |
  +----> Longer Route
  |
  +----> More Wirelength
  |
  +----> Timing / Power Impact
```

Similarly, fixing timing may require:

- Larger cells
- Additional buffers
- Different routing
- More physical resources

Therefore, physical correctness and PPA optimization can interact.

---

* **Physical Verification Flow in ASIC Design:**

```text
Specification
      |
      v
Architecture
      |
      v
RTL Design
      |
      v
Functional Verification
      |
      v
Logic Synthesis
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
      |
      v
Parasitic Extraction
      |
      v
STA / Power Analysis
      |
      v
Physical Verification
      |
      v
Signoff
      |
      v
Tapeout
```

---

* **Physical Verification vs Functional Verification:**

| Functional Verification | Physical Verification |
|---|---|
| Checks logical/functional behavior | Checks physical implementation |
| Uses simulation/testbench and other functional methods | Uses layout and technology-rule based checks |
| Checks whether RTL behaves correctly | Checks whether physical implementation is valid |
| Focuses on functionality | Focuses on geometry, connectivity and manufacturability |
| Example: counter produces correct sequence | Example: metal spacing satisfies DRC |

Both are necessary.

---

* **Physical Verification vs Logic Synthesis:**

| Logic Synthesis | Physical Verification |
|---|---|
| Converts RTL to gate-level netlist | Checks physical implementation |
| Focuses on logic representation | Focuses on physical correctness |
| Uses timing/area/power constraints | Uses technology and physical rules |
| Produces gate-level netlist | Produces verification results/reports |

---

* **Physical Verification vs STA:**

| Physical Verification | STA |
|---|---|
| Checks physical correctness | Checks timing correctness |
| DRC, LVS, ERC, antenna, etc. | Setup, hold, slack, timing paths |
| Focuses on geometry/connectivity | Focuses on timing behavior |
| Uses layout and physical rules | Uses netlist, libraries, constraints, and physical timing information |
| Finds physical violations | Finds timing violations |

---

* **RTL Relevance:**

Physical Verification occurs mainly in the Back-End/Physical Design flow, but RTL designers should understand its purpose.

RTL influences the downstream implementation:

```text
RTL
 |
 v
Logic Structure
 |
 v
Synthesis
 |
 v
Cell Connectivity
 |
 v
Placement + Routing
 |
 v
Physical Layout
 |
 v
Physical Verification
```

RTL design decisions can indirectly affect:

- Cell count
- Routing complexity
- Fanout
- Congestion
- Wirelength
- Timing
- Power
- Physical implementation difficulty

Therefore, a good RTL Design Engineer should understand that correct RTL is only the beginning of the complete ASIC implementation flow.

---

* **Common Physical Verification Problems:**

1. DRC violations
2. LVS mismatches
3. Shorts
4. Opens
5. Minimum-width violations
6. Minimum-spacing violations
7. Via violations
8. Enclosure violations
9. Antenna violations
10. Floating connections
11. Power/ground connectivity issues
12. Density violations
13. Incorrect physical connectivity
14. Technology-rule violations

---

* **Best Practices:**

- Run physical verification regularly during implementation.
- Understand the reported rule before modifying the layout.
- Debug the root cause rather than blindly changing geometry.
- Maintain correct net connectivity.
- Check both DRC and LVS.
- Check antenna and electrical rules where applicable.
- Use the correct technology rule deck.
- Re-run verification after significant physical changes.
- Track and resolve violations systematically.
- Do not assume timing-clean means physically-clean.
- Do not assume DRC-clean means logically-equivalent.
- Perform complete signoff checks before tapeout.

---

* **Applications:**

Physical verification is used in:

- ASIC design
- SoC design
- CPU design
- GPU design
- Microcontroller design
- DSP processors
- AI accelerators
- Memory controllers
- High-speed digital interfaces
- Standard-cell based digital ICs
- Mixed-signal ICs
- Custom ICs
- Semiconductor manufacturing signoff

---

* **Advantages:**

- Detects manufacturing-rule violations.
- Verifies physical connectivity.
- Detects shorts and opens.
- Supports manufacturability.
- Helps prevent physical implementation errors from reaching fabrication.
- Provides confidence in final layout quality.
- Supports final ASIC signoff.
- Reduces the risk of costly silicon failures caused by physical implementation problems.

---

* **Limitations:**

- Does not replace functional verification.
- Does not replace STA.
- Does not guarantee complete silicon functionality by itself.
- Requires accurate technology-specific rules.
- Large designs can generate many violations.
- Debugging physical violations can require multiple iterations.
- Some physical problems require trade-offs with timing, power, area, and routing.

---

* **Real-World Example:**

Consider a processor core after routing:

```text
Processor Core
      |
      v
Placed + Routed Layout
      |
      +------------------+
      |                  |
      v                  v
     DRC                LVS
      |                  |
      v                  v
Physical Rules       Connectivity
      |                  |
      +--------+---------+
               |
               v
       Additional Checks
               |
               v
            Signoff
```

Suppose the routing accidentally creates insufficient spacing between two metal nets.

The circuit may still appear logically correct in simulation.

However:

```text
Simulation → PASS

DRC         → FAIL
```

The physical design must be corrected before tapeout.

Similarly, if a routing problem causes an unintended connection:

```text
DRC / LVS → FAIL
```

The issue must be debugged and corrected.

This demonstrates an important principle:

```text
Functional Correctness
        +
Timing Correctness
        +
Physical Correctness
        =
Reliable Final Design
```

---

* **Key Points:**

- Physical Verification checks the correctness of the physical layout.
- DRC checks whether the layout follows manufacturing rules.
- LVS checks whether the extracted physical connectivity matches the intended circuit.
- ERC checks electrical conditions that may not be fully covered by geometric rules.
- Antenna checking identifies manufacturing-related antenna conditions.
- Shorts connect nets that should remain separate.
- Opens indicate incomplete required connections.
- Physical verification uses technology-specific rule decks.
- DRC and LVS answer different questions.
- Timing-clean does not necessarily mean physically-clean.
- DRC-clean does not by itself prove functional correctness.
- Physical verification is an important part of signoff.
- Clean physical verification is required before final tapeout according to the applicable signoff methodology.
- RTL decisions can indirectly affect downstream physical implementation.
- Physical verification helps reduce the risk of manufacturing and physical implementation failures.

---

* **Interview Questions:**

### 1. What is Physical Verification?

Physical Verification is the process of checking an IC layout against manufacturing rules and intended circuit connectivity before signoff and tapeout.

### 2. What is DRC?

DRC stands for **Design Rule Checking**. It checks whether the physical layout satisfies technology-specific manufacturing rules.

### 3. What is LVS?

LVS stands for **Layout Versus Schematic**. It checks whether the connectivity extracted from the physical layout matches the intended circuit representation.

### 4. What is the difference between DRC and LVS?

```text
DRC → Checks physical geometry and manufacturing rules.

LVS → Checks physical connectivity against the intended circuit.
```

### 5. Can a design pass simulation but fail DRC?

Yes. Simulation checks logical behavior for simulated scenarios, while DRC checks physical geometry and manufacturing rules.

### 6. Can a design pass DRC but fail LVS?

Yes. A layout can satisfy geometric manufacturing rules while still having incorrect electrical connectivity.

### 7. What is a short?

A short is an unintended electrical connection between two different nets.

### 8. What is an open?

An open is an incomplete electrical connection where a required connection is missing.

### 9. What is an antenna violation?

An antenna violation is a manufacturing-related condition where charge accumulation on an interconnect can potentially damage a gate during fabrication.

### 10. What is ERC?

ERC stands for **Electrical Rule Checking**. It checks electrical conditions such as invalid connections, floating signals, and certain power or well-related problems depending on the methodology.

### 11. What is a DRC rule deck?

A DRC rule deck contains technology-specific manufacturing rules used by physical verification tools.

### 12. Why is physical verification required before tapeout?

It helps ensure that the layout satisfies manufacturing rules and correctly represents the intended circuit before the design is released for fabrication.

### 13. What happens if DRC fails?

The reported physical violations must be analyzed, corrected, and the relevant physical verification checks must be run again.

### 14. What happens if LVS fails?

The LVS report is analyzed to identify connectivity or device/cell mismatches, the physical implementation is corrected, and LVS is rerun.

### 15. Does DRC verify functionality?

No. DRC primarily verifies physical geometry and manufacturing-rule compliance.

### 16. Does LVS verify timing?

No. LVS primarily verifies connectivity/equivalence between the extracted layout representation and the intended circuit representation.

### 17. Does Physical Verification replace STA?

No. Physical Verification and STA check different aspects of the design.

### 18. Why is Physical Verification important for an RTL Design Engineer?

It helps the RTL designer understand how RTL decisions eventually affect physical implementation, routing complexity, congestion, timing, power, and manufacturability.

### 19. What are the major physical verification checks?

Common checks include:

- DRC
- LVS
- ERC
- Antenna checks
- Technology-specific physical signoff checks

### 20. What is the relationship between routing and physical verification?

Routing creates the physical geometries, while physical verification checks whether those geometries satisfy physical and connectivity requirements.

---

* **Quick Revision:**

```text
Physical Verification
        |
        +----> DRC
        |       |
        |       +----> Manufacturing Rules
        |
        +----> LVS
        |       |
        |       +----> Connectivity Match
        |
        +----> ERC
        |       |
        |       +----> Electrical Rules
        |
        +----> Antenna
                |
                +----> Manufacturing-Related Checks
```

### Remember:

```text
DRC → Is the layout physically legal?

LVS → Does the layout match the intended circuit?

ERC → Are important electrical rules satisfied?

Antenna → Are manufacturing-related antenna conditions acceptable?
```

---

* **Summary:**

Physical Verification is a critical stage of the ASIC implementation flow that checks whether the final physical layout is **manufacturable and correctly represents the intended circuit**.

The two most fundamental checks are **DRC** and **LVS**. DRC verifies physical geometry against manufacturing rules, while LVS verifies physical connectivity against the intended circuit representation. Additional checks such as ERC and antenna verification address other electrical and manufacturing concerns.

Physical Verification does not replace functional verification or STA. Instead, these verification activities complement each other:

```text
Functional Verification
        ↓
Functional Correctness

STA
        ↓
Timing Correctness

Physical Verification
        ↓
Physical / Manufacturing Correctness
```

Together, they support a reliable final design before **signoff and tapeout**.

---

* **References:**

1. Neso Academy — VLSI / Physical Design concepts  
2. All About Electronics — Digital Electronics and VLSI concepts  
3. Neil H. E. Weste and David Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*  
4. Jan M. Rabaey, Anantha Chandrakasan, and Borivoje Nikolić — *Digital Integrated Circuits: A Design Perspective*  
5. Standard ASIC Physical Verification and Signoff methodologies
