## Minterms
A minterm is a product (AND) term in which all variables appear exactely once,either in normal or complemented form the minterm output will be (1).

Minterm = AND of all inputs.

#### Standrad form 
(Sum Of Products) And it is denoted by the Symool *[summation 'm']* 

### Example 
For three variable = [A , B , C']

A = 1 , B = 0 , c = 0 

------------------------
## Maxterms
A maxterm ia a sum (OR) term it represents an unique input combinational which functional output will be (0).

Maxterm = OR of all inputs.

#### Standard form
(Product Of Sum) And it is denoted by the symbol of *[pai 'M']*

### Example 
For three vairiable = [A , B , c']

A = 0 , B = 0 , C = 1 

-------------------------
                                                                                             
### Truth Table: Minterms and Maxterms (3-Variable)

| Inputs (A B C) | Minterm (Product) | Symbol | Maxterm (Sum) | Symbol |
| :---: | :---: | :---: | :---: | :---: |
| 0 0 0 | A'B'C' | m0 | A + B + C | M0 |
| 0 0 1 | A'B'C | m1 | A + B + C' | M1 |
| 0 1 0 | A'BC' | m2 | A + B' + C | M2 |
| 0 1 1 | A'BC | m3 | A + B' + C' | M3 |
| 1 0 0 | AB'C' | m4 | A' + B + C | M4 |
| 1 0 1 | AB'C | m5 | A' + B + C' | M5 |
| 1 1 0 | ABC' | m6 | A' + B' + C | M6 |
| 1 1 1 | ABC | m7 | A' + B' + C' | M7 |                                                                           
-------------------------------------------

## Conical Sum Of Product
The conical (sop) is also called as the *sum of minterms* and the function of the conical sum of product is (OR) sum its minterms which output is '1'

### Example 
If a function f(A , B , c) it is minterm (m)

The conical so wiil be 

f(A , B , c) = (A' * B * c) + (A * B' * C) + (A * B * C')

Output = summation(3 , 5 , 6)

---------------------------------

## Conical product of sum  
The conical (POS) is also called as the *product of maxterm* and the function of thr conical product of sum is (AND) product its maxterm which putput will be '0'

### Example 
If a function f(A , B , C) it maxterm (M)

The conical pos will be 

f(A , B , c) = (A'+B+C) * (A+B'+C) * (A+B+C')

Output = pai(4 , 2 , 1)

                                                                     









