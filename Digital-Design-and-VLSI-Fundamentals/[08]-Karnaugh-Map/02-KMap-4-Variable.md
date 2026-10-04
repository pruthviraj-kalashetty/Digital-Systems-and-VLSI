# **4-Variable K-Map**

* **Overview**

A 4-variable Karnaugh Map (K-Map) is a graphical method used to simplify Boolean expressions with four variables.

It contains **16 cells**, representing all possible combinations of four Boolean variables.

* **Definition**

For four variables:

    A, B, C, D

the total number of possible input combinations is:

    2⁴ = 16

Therefore, a 4-variable K-Map contains **16 cells**.

* **Purpose**

The main purpose of a 4-variable K-Map is to simplify Boolean expressions by grouping adjacent **1s** for SOP or adjacent **0s** for POS.

It helps reduce:

- Number of logic gates.
- Number of gate inputs.
- Logic complexity.
- Propagation delay.
- Hardware resources.

* **Core Concept**

A 4-variable K-Map is arranged as:

    Rows    → AB
    Columns → CD

Both use Gray-code order:

    00 → 01 → 11 → 10

The complete map contains:

    4 rows × 4 columns = 16 cells

* **K-Map Structure**

                  CD
                00   01   11   10
              ┌────┬────┬────┬────┐
        AB=00 │    │    │    │    │
              ├────┼────┼────┼────┤
        AB=01 │    │    │    │    │
              ├────┼────┼────┼────┤
        AB=11 │    │    │    │    │
              ├────┼────┼────┼────┤
        AB=10 │    │    │    │    │
              └────┴────┴────┴────┘

Notice that the order is:

    00 → 01 → 11 → 10

This is Gray-code ordering.

* **Minterm Mapping**

The 16 cells correspond to minterms m0 to m15.

                  CD
                00   01   11   10
              ┌────┬────┬────┬────┐
        AB=00 │ m0 │ m1 │ m3 │ m2 │
              ├────┼────┼────┼────┤
        AB=01 │ m4 │ m5 │ m7 │ m6 │
              ├────┼────┼────┼────┤
        AB=11 │m12 │m13 │m15 │m14 │
              ├────┼────┼────┼────┤
        AB=10 │ m8 │ m9 │m11 │m10 │
              └────┴────┴────┴────┘

The order is not normal binary order because K-Maps use Gray code.

* **Grouping Rules**

For SOP simplification, group adjacent **1s**.

For POS simplification, group adjacent **0s**.

Valid group sizes are:

    1, 2, 4, 8, 16

Important rules:

1. Groups must contain a power of 2 cells.
2. Groups must be rectangular.
3. Diagonal cells cannot be grouped.
4. Make groups as large as possible.
5. Every required 1 must be covered for SOP.
6. Groups may overlap.
7. The K-Map wraps around at the edges.
8. The first and last rows are adjacent.
9. The first and last columns are adjacent.

* **Variable Elimination**

The size of the group determines how many variables are eliminated.

| Group Size | Variables Eliminated |
|---|---:|
| 1 | 0 |
| 2 | 1 |
| 4 | 2 |
| 8 | 3 |
| 16 | 4 |

Therefore:

    Larger group
        ↓
    More variables eliminated
        ↓
    Simpler expression

* **Adjacent Cells**

Two cells are adjacent when they differ in only **one variable**.

For example:

    00 → 01

Only one bit changes.

Also:

    01 → 11
    11 → 10

Only one bit changes in each transition.

The K-Map also wraps around:

    First Column ↔ Last Column

and:

    First Row ↔ Last Row

This makes edge grouping possible.

* **Simple Example 1**

Simplify:

    F(A,B,C,D) = Σm(0,1,2,3)

Place 1s at:

    m0, m1, m2, m3

K-Map:

                  CD
                00   01   11   10
              ┌────┬────┬────┬────┐
        AB=00 │ 1  │ 1  │ 1  │ 1  │
              ├────┼────┼────┼────┤
        AB=01 │ 0  │ 0  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=11 │ 0  │ 0  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=10 │ 0  │ 0  │ 0  │ 0  │
              └────┴────┴────┴────┘

Group the four 1s:

    ┌────┬────┬────┬────┐
    │ 1  │ 1  │ 1  │ 1  │
    └────┴────┴────┴────┘

Inside the group:

    A = 0 → constant
    B = 0 → constant
    C changes
    D changes

Therefore:

    F = A'B'

* **Simple Example 2**

Simplify:

    F(A,B,C,D) = Σm(0,2,8,10)

K-Map:

                  CD
                00   01   11   10
              ┌────┬────┬────┬────┐
        AB=00 │ 1  │ 0  │ 0  │ 1  │
              ├────┼────┼────┼────┤
        AB=01 │ 0  │ 0  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=11 │ 0  │ 0  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=10 │ 1  │ 0  │ 0  │ 1  │
              └────┴────┴────┴────┘

The four 1s form a group using the **left-right wrap-around**.

The constant variables are:

    B = 0
    D = 0

Therefore:

    F = B'D'

This example demonstrates why edge wrapping is important.

* **Simple Example 3**

Simplify:

    F(A,B,C,D) = Σm(0,1,4,5)

K-Map:

                  CD
                00   01   11   10
              ┌────┬────┬────┬────┐
        AB=00 │ 1  │ 1  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=01 │ 1  │ 1  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=11 │ 0  │ 0  │ 0  │ 0  │
              ├────┼────┼────┼────┤
        AB=10 │ 0  │ 0  │ 0  │ 0  │
              └────┴────┴────┴────┘

Group the four 1s.

Inside this group:

    A changes
    B = 0
    C = 0
    D changes

Therefore:

    F = B'C'

* **Don't-Care Conditions**

Some input combinations may not matter for the required circuit behavior.

These are represented by:

    X

or:

    d

A don't-care cell can be treated as either:

    0 or 1

Use it as 1 when it helps create a larger group and simplify the expression.

Do not include a don't-care unnecessarily.

* **SOP Simplification**

For **Sum of Products**:

    Group 1s

Process:

    Boolean Expression
           ↓
    Find Minterms
           ↓
    Fill 1s
           ↓
    Add useful Don't-Cares
           ↓
    Make Largest Groups
           ↓
    Eliminate Changing Variables
           ↓
    Simplified SOP

* **POS Simplification**

For **Product of Sums**:

    Group 0s

Process:

    Boolean Expression
           ↓
    Find Maxterms
           ↓
    Fill 0s
           ↓
    Add useful Don't-Cares
           ↓
    Make Largest Groups
           ↓
    Eliminate Changing Variables
           ↓
    Simplified POS

* **Prime Implicant**

A **prime implicant** is a group that cannot be expanded further without including an unwanted 0.

An **essential prime implicant** covers at least one required 1 that no other prime implicant covers.

Essential prime implicants should be selected first.

* **Important Terms**

| Term | Meaning |
|---|---|
| K-Map | Graphical Boolean simplification method |
| Minterm | Product term representing one input combination |
| Maxterm | Sum term representing one input combination |
| Group | Set of adjacent cells |
| Prime Implicant | Group that cannot be expanded further |
| Essential Prime Implicant | Required group covering a unique 1 |
| SOP | Sum of Products |
| POS | Product of Sums |
| Don't-Care | Input combination that can be treated as 0 or 1 |
| Gray Code | Ordering where adjacent values differ by one bit |

* **Advantages**

- Simple visual method for Boolean simplification.
- Reduces logic gates.
- Reduces number of gate inputs.
- Helps reduce combinational logic complexity.
- Useful for understanding digital circuit optimization.
- Useful for learning combinational RTL design.

* **Limitations**

- Becomes difficult as the number of variables increases.
- Manual K-Maps are mainly practical for small Boolean functions.
- Large designs are better handled using Boolean optimization and synthesis tools.

* **RTL Relevance**

K-Map simplification provides a foundation for understanding combinational RTL.

For example:

    F = AB + AC

can be written in Verilog as:

    assign F = (A & B) | (A & C);

A synthesis tool can optimize Boolean logic automatically, but understanding K-Maps helps an RTL designer:

- Understand combinational logic.
- Recognize redundant logic.
- Understand logic minimization.
- Analyze synthesized logic.
- Understand why logic depth affects timing.

A simpler Boolean expression can potentially result in simpler hardware, although the final synthesized implementation depends on the synthesis library and constraints.

* **Common Mistakes**

1. Using normal binary order instead of Gray-code order.
2. Grouping diagonal cells.
3. Forgetting edge wrapping.
4. Using group sizes other than powers of 2.
5. Making unnecessarily small groups.
6. Forgetting to cover required 1s.
7. Grouping 1s when performing POS simplification.
8. Keeping a variable that changes inside a group.
9. Removing a variable that remains constant.
10. Forgetting that the first and last rows are adjacent.
11. Forgetting that the first and last columns are adjacent.

* **Interview Questions**

**Q1. How many cells are present in a 4-variable K-Map?**

    2⁴ = 16 cells

**Q2. What is the Gray-code order used in a K-Map?**

    00 → 01 → 11 → 10

**Q3. What are the valid group sizes in a 4-variable K-Map?**

    1, 2, 4, 8, 16

**Q4. Can the first and last rows be grouped together?**

Yes. K-Maps wrap around, so the first and last rows are adjacent.

**Q5. Can diagonal cells be grouped?**

No. Diagonal cells differ in more than one variable and are not directly adjacent.

**Q6. What do we group for SOP?**

We group **1s**.

**Q7. What do we group for POS?**

We group **0s**.

**Q8. Why should we prefer larger groups?**

Larger groups eliminate more variables and generally produce a simpler Boolean expression.

* **Quick Revision**

    4 Variables → 16 Cells

    Variables:
    A, B, C, D

    Rows:
    AB

    Columns:
    CD

    Gray Code:
    00 → 01 → 11 → 10

    SOP → Group 1s

    POS → Group 0s

    Valid Groups:
    1, 2, 4, 8, 16

    Larger Group → More Variables Eliminated

    First Row ↔ Last Row

    First Column ↔ Last Column

    Diagonal → Not Adjacent

    Don't-Care → X

* **Summary**

A 4-variable K-Map contains **16 cells** and represents all possible combinations of four Boolean variables.

The rows and columns use Gray-code ordering so adjacent cells differ in only one variable.

For SOP simplification, group adjacent 1s. For POS simplification, group adjacent 0s.

The goal is to create the largest valid groups, because larger groups eliminate more variables and produce simpler Boolean expressions.

Understanding 4-variable K-Maps gives a strong foundation for Boolean simplification, combinational logic, and RTL design.

* **References**

- *Digital Design* — M. Morris Mano and Michael D. Ciletti
- *Digital Design and Computer Architecture* — David Harris and Sarah Harris
- *Fundamentals of Digital Logic with Verilog Design* — Stephen Brown and Zvonko Vranesic
- Neso Academy — Digital Electronics / Karnaugh Maps
- All About Electronics — Karnaugh Map Simplification
