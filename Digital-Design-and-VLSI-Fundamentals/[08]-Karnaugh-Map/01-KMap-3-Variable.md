# **3-Variable K-Map**

* **Overview**

A 3-variable Karnaugh Map (K-Map) is a graphical method used to simplify Boolean expressions with three variables.

It helps reduce the number of logic gates and inputs required to implement a digital circuit.

* **Definition**

A 3-variable K-Map represents all possible combinations of three Boolean variables in a grid of **8 cells**.

For three variables:

    Number of cells = 2³ = 8

* **Purpose**

The main purpose of a K-Map is to simplify a Boolean expression by grouping adjacent **1s** for **SOP (Sum of Products)** or adjacent **0s** for **POS (Product of Sums)**.

* **Why is it important?**

K-Map simplification can:

- Reduce the number of logic gates.
- Reduce the number of inputs to gates.
- Reduce circuit complexity.
- Reduce propagation delay.
- Make RTL and digital hardware more efficient.

* **Core Concept**

For three variables, let the variables be:

    A, B, C

A 3-variable K-Map contains:

    2³ = 8 cells

The map is arranged using **Gray code order**, not normal binary order.

Gray code order:

    00
    01
    11
    10

Only one variable changes between adjacent cells.

* **K-Map Structure**

A common 3-variable K-Map is:

                  BC
                00   01   11   10
              ┌────┬────┬────┬────┐
          A=0 │    │    │    │    │
              ├────┼────┼────┼────┤
          A=1 │    │    │    │    │
              └────┴────┴────┴────┘

There are:

    2 rows × 4 columns = 8 cells

Each cell represents one minterm.

* **Minterm Mapping**

For variables A, B, C:

| A | B | C | Minterm |
|---|---|---|---|
| 0 | 0 | 0 | m0 |
| 0 | 0 | 1 | m1 |
| 0 | 1 | 0 | m2 |
| 0 | 1 | 1 | m3 |
| 1 | 0 | 0 | m4 |
| 1 | 0 | 1 | m5 |
| 1 | 1 | 0 | m6 |
| 1 | 1 | 1 | m7 |

Therefore:

    K-Map cells = m0, m1, m2, m3, m4, m5, m6, m7

* **K-Map Layout with Minterms**

                  BC
                00   01   11   10
              ┌────┬────┬────┬────┐
          A=0 │ m0 │ m1 │ m3 │ m2 │
              ├────┼────┼────┼────┤
          A=1 │ m4 │ m5 │ m7 │ m6 │
              └────┴────┴────┴────┘

Notice the order:

    00 → 01 → 11 → 10

This is Gray-code ordering.

* **Grouping Rules**

When simplifying SOP expressions, group the cells containing **1s**.

Important rules:

1. Groups must contain a power of 2 cells.
2. Valid group sizes are:

       1, 2, 4, 8

3. Groups must be rectangular.
4. Diagonal cells cannot be grouped.
5. Groups should be as large as possible.
6. Every required 1 must be covered.
7. Groups may overlap.
8. The left and right edges are adjacent.
9. The map wraps around at the edges.

For example:

    2 cells → eliminate 1 variable
    4 cells → eliminate 2 variables
    8 cells → eliminate 3 variables

* **Adjacent Cells**

In a K-Map, adjacency is based on Gray-code ordering.

For example:

    00 → 01 → 11 → 10

Each neighboring position differs in only one variable.

The first and last columns are also adjacent:

    00 ↔ 10

Therefore, the K-Map wraps around.

* **Simple Example**

Simplify:

    F(A,B,C) = Σm(1,3,5,7)

Place 1s in:

    m1, m3, m5, m7

K-Map:

                  BC
                00   01   11   10
              ┌────┬────┬────┬────┐
          A=0 │ 0  │ 1  │ 1  │ 0  │
              ├────┼────┼────┼────┤
          A=1 │ 0  │ 1  │ 1  │ 0  │
              └────┴────┴────┴────┘

Group the four 1s:

    ┌────┬────┐
    │ 1  │ 1  │
    ├────┼────┤
    │ 1  │ 1  │
    └────┴────┘

In this group:

    A changes → eliminate A
    B changes → eliminate B
    C remains 1 → keep C

Therefore:

    F = C

* **Another Example**

Simplify:

    F(A,B,C) = Σm(0,1,2,3)

K-Map:

                  BC
                00   01   11   10
              ┌────┬────┬────┬────┐
          A=0 │ 1  │ 1  │ 1  │ 1  │
              ├────┼────┼────┼────┤
          A=1 │ 0  │ 0  │ 0  │ 0  │
              └────┴────┴────┴────┘

Group the four 1s in the first row.

Here:

    A = 0 → remains constant
    B changes
    C changes

Therefore:

    F = A'

* **Essential Prime Implicant**

A **prime implicant** is a group that cannot be expanded further without including a 0.

An **essential prime implicant** covers at least one 1 that is not covered by any other possible prime implicant.

Essential groups should be selected first during simplification.

* **Don't-Care Conditions**

Sometimes certain input combinations are not important for the required circuit behavior.

These are represented as:

    X

or:

    d

Don't-care cells can be treated as either:

    0 or 1

depending on which choice produces a simpler expression.

They should only be included when they help create a larger useful group.

* **SOP Simplification**

For **Sum of Products**:

    Group 1s

Example:

    F = AB + AC

K-Map is used to find the minimum product terms.

General process:

    Boolean Expression
           ↓
    Find Minterms
           ↓
    Fill 1s
           ↓
    Make Groups
           ↓
    Eliminate Changing Variables
           ↓
    Simplified SOP

* **POS Simplification**

For **Product of Sums**:

    Group 0s

General process:

    Boolean Expression
           ↓
    Find Maxterms
           ↓
    Fill 0s
           ↓
    Make Groups
           ↓
    Eliminate Changing Variables
           ↓
    Simplified POS

* **Important Terms**

| Term | Meaning |
|---|---|
| K-Map | Graphical Boolean simplification method |
| Variable | Boolean input such as A, B, or C |
| Minterm | Product term representing one input combination |
| Maxterm | Sum term representing one input combination |
| Group | Adjacent K-Map cells combined together |
| Prime Implicant | Group that cannot be expanded further |
| Essential Prime Implicant | Required group covering a unique 1 |
| SOP | Sum of Products |
| POS | Product of Sums |
| Don't-Care | Input condition that can be treated as 0 or 1 |

* **Advantages**

- Easy visual simplification.
- Reduces Boolean expressions.
- Reduces hardware complexity.
- Useful for combinational logic design.
- Helps reduce logic levels and potentially propagation delay.

* **Limitations**

- Becomes difficult for a large number of variables.
- Manual K-Map simplification is usually practical for a small number of variables.
- For many variables, Boolean-algebra tools or logic-minimization software are more practical.

* **RTL Relevance**

K-Map concepts help build a strong foundation for understanding how Boolean logic becomes hardware.

For example, a simplified expression:

    F = AB + AC

can be implemented using AND and OR gates.

In RTL:

    assign F = (A & B) | (A & C);

Understanding the simplification helps an RTL designer recognize unnecessary logic and understand the resulting combinational hardware.

Modern synthesis tools can perform Boolean optimization automatically, but understanding K-Maps helps when analyzing RTL and synthesized logic.

* **Common Mistakes**

1. Using binary order instead of Gray-code order.
2. Grouping diagonal cells.
3. Forgetting that the edges wrap around.
4. Making groups with non-power-of-two sizes.
5. Making unnecessarily small groups.
6. Forgetting to cover required 1s.
7. Grouping 1s for POS instead of 0s.
8. Keeping a variable that changes inside the group.
9. Removing a variable that remains constant.

* **Interview Questions**

**Q1. How many cells are present in a 3-variable K-Map?**

    2³ = 8 cells

**Q2. Why is Gray code used in K-Maps?**

Gray code ensures that adjacent cells differ in only one variable, which allows that variable to be eliminated during simplification.

**Q3. What group sizes are allowed in a K-Map?**

    1, 2, 4, 8, ...

The group size must always be a power of 2.

**Q4. Can the first and last columns be grouped?**

Yes. K-Maps wrap around, so the first and last columns are considered adjacent.

**Q5. What do we group for SOP simplification?**

We group **1s**.

**Q6. What do we group for POS simplification?**

We group **0s**.

* **Quick Revision**

    3 Variables → 8 Cells

    Variables:
    A, B, C

    Gray Code:
    00 → 01 → 11 → 10

    SOP → Group 1s

    POS → Group 0s

    Valid Groups:
    1, 2, 4, 8

    Larger Group → More Variables Eliminated

    Edges → Wrap Around

    Diagonal → Not Adjacent

    Don't-Care → X

* **Summary**

A 3-variable K-Map contains **8 cells** representing all possible combinations of three Boolean variables.

The cells are arranged using Gray-code order so that adjacent cells differ in only one variable.

For SOP, group adjacent 1s. For POS, group adjacent 0s. Always try to form the largest valid groups because larger groups produce simpler Boolean expressions.

K-Maps are especially useful for understanding Boolean simplification and the basic logic optimization that underlies combinational RTL design.

* **References**

- *Digital Design* — M. Morris Mano and Michael D. Ciletti
- *Digital Design and Computer Architecture* — David Harris and Sarah Harris
- *Fundamentals of Digital Logic with Verilog Design* — Stephen Brown and Zvonko Vranesic
- Neso Academy — Digital Electronics / Karnaugh Maps
- All About Electronics — Karnaugh Map Simplification
