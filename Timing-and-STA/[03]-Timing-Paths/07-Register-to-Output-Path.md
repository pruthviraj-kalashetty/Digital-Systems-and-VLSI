# **Register-to-Output Path**

* **Overview**

A register-to-output path is a timing path in which data starts from a register inside the design and ends at an output port.

It is important in STA because the data must reach the external output within the required timing window.

* **Definition**

A **register-to-output path** is a timing path that starts at the Q output of a launch register and ends at an output port of the design.

The basic structure is:

    Launch Register
          │
          │ Q
          ▼
    Combinational Logic
          │
          ▼
      Output Port

* **Why is it needed?**

STA analyzes register-to-output paths to verify that data reaches the external destination at the expected time.

It helps check:

- Output data arrival time
- Register clock-to-Q delay
- Combinational logic delay
- Output delay requirements
- Timing slack
- Timing violations

This path is important when the ASIC communicates with another device or external system.

* **Core Concept**

A simple register-to-output path looks like:

                 Clock
                   │
                   ▼
               ┌───────┐
               │  FF   │
               │       │
               └───┬───┘
                   │ Q
                   ▼
             ┌───────────┐
             │Combinational│
             │   Logic   │
             └─────┬─────┘
                   │
                   ▼
              Output Port
                   │
                   ▼
             External Device

The register launches the data.

The data travels through the combinational logic.

The resulting signal reaches the output port.

* **Timing Diagram**

A simplified register-to-output timing relationship is:

    Launch Clock Edge
           │
           ▼
    ───────┼────────────────────────────────
           │
           │ Clock-to-Q Delay
           │<──────────>
           ▼
        Data Changes
           │
           │
           │ Combinational Delay
           │<────────────────>
           ▼
       Output Changes
           │
           ▼
      External Device

The output data must become available within the timing requirement of the external interface.

* **Important Terms**

**Launch Register**

The register that launches data toward the output.

**Clock-to-Q Delay**

The delay between the active clock edge and the corresponding change at the register's Q output.

**Combinational Logic**

Logic between the launch register and the output port.

**Output Port**

The external boundary through which the design sends data.

**Output Delay**

The timing requirement describing when the output data is expected to be available relative to the reference clock.

**Output Arrival Time**

The time at which data reaches the output port.

**Output Constraint**

A timing constraint that specifies the required timing relationship between the design output and the external receiving environment.

* **Formula**

For a simplified register-to-output path:

    Output Arrival Time
    =
    tCQ + tDATA

Where:

- `tCQ` = clock-to-Q delay of the launch register
- `tDATA` = internal combinational data-path delay

In real STA, an output-delay constraint is used to describe the external timing requirement.

A simplified timing check can be viewed as:

    tCQ + tDATA + tOUTPUT
    ≤
    TCLK

Where:

- `tOUTPUT` = external/output timing requirement
- `TCLK` = clock period

* **Simple Example**

Assume:

    Clock Period      = 10 ns
    Clock-to-Q Delay  = 1 ns
    Logic Delay       = 4 ns
    Output Requirement = 2 ns

Internal output arrival:

    Arrival Time
    = tCQ + tDATA
    = 1 + 4
    = 5 ns

Total timing requirement:

    Required Time
    = 10 - 2
    = 8 ns

Therefore:

    Slack
    = 8 - 5
    = +3 ns

The simplified register-to-output path satisfies the timing requirement.

* **STA Connection**

STA analyzes the path from the launch register to the output port.

A simplified view is:

              Clock Source
                   │
                   ▼
              Launch Clock
                   │
                   ▼
               Launch FF
                   │ Q
                   ▼
              Data Path
                   │
                   ▼
              Output Port
                   │
                   ▼
            External Device

The output-delay constraint tells STA how much timing is available for the internal design to deliver the output data.

For this type of path, STA considers:

1. Launch clock arrival.
2. Launch register clock-to-Q delay.
3. Internal data-path delay.
4. Output timing requirement.
5. Timing slack.

* **RTL Relevance**

Register-to-output paths are commonly created when registered signals are sent outside the design.

For example:

    always @(posedge clk) begin
        data_out <= data_in;
    end

Here:

    data_out → Output Port

The register launching `data_out` creates the start of the register-to-output timing path.

If combinational logic is present:

    Register
       │
       ▼
      Logic
       │
       ▼
    data_out

that logic contributes to the output timing delay.

* **Common Mistakes**

- Forgetting the launch register's clock-to-Q delay.
- Ignoring combinational logic between the register and output.
- Confusing output delay with internal data-path delay.
- Assuming the output changes exactly at the clock edge.
- Forgetting that the external receiving device has its own timing requirements.
- Treating an output port as a capture register.
- Assuming RTL simulation alone verifies external interface timing.

* **Interview Questions**

**1. What is a register-to-output path?**

It is a timing path from the Q output of an internal register to an output port of the design.

**2. What is the basic structure?**

    Launch Register → Combinational Logic → Output Port

**3. What delays affect the output arrival time?**

The main internal delays are the launch register's clock-to-Q delay and the combinational data-path delay.

**4. What is an output-delay constraint?**

It describes the timing requirement of the external environment relative to the reference clock and is used by STA to analyze output timing.

**5. Why is the external device important?**

The external device determines when it expects the output data to be available or stable, so the ASIC must meet the corresponding interface timing requirement.

* **Quick Revision**

- Register-to-output = Register → Logic → Output Port.
- The register is the launch element.
- Clock-to-Q contributes to output arrival time.
- Combinational logic adds additional delay.
- Output-delay constraints model the external timing requirement.
- STA checks whether the output reaches the external interface in time.

* **Summary**

A register-to-output path starts at an internal launch register and ends at an output port. The output timing depends on the launch register's clock-to-Q delay, internal combinational logic, and the timing requirement of the external receiving environment. STA uses output-delay constraints to verify that the design produces its output within the required timing window.

* **References**

- David Money Harris and Sarah L. Harris — *Digital Design and Computer Architecture*
- Neil H. E. Weste and David Money Harris — *CMOS VLSI Design: A Circuits and Systems Perspective*
- Synopsys — Static Timing Analysis documentation
- Cadence — Digital Design and Timing Analysis documentation
