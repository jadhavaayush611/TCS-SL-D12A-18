# Practical 06: DFA to Regular Grammar – Strings Starting with 0 and Ending with 1

**Student:** Aayush Jadhav  
**Roll No.:** 18  
**Class / Division:** D12A  
**Subject:** Theory of Computer Science (26CMPC51)  
**Institution:** Vivekanand Education Society's Institute of Technology (VESIT)  
**Date of Submission:** 16 November 2026  
**JFLAP File:** `18_Aayush_Jadhav_DFA_Source_Start0_End1_16-11-2026.jff and 18_Aayush_Jadhav_Regular_Grammar_Start0_End1_16-11-2026.jff`

## Aim
To convert a DFA for strings that start with `0` and end with `1` into an equivalent right-linear regular grammar.

## Language
\(L=0(0+1)^*1\), over \(\Sigma=\{0,1\}\). The string must begin with 0 and must contain at least one further symbol so that its last symbol can be 1.

## DFA states
- q0: initial state, before the first input symbol.
- qd: dead state entered if the first symbol is 1.
- q1: valid first symbol was 0; current last symbol is 0.
- q2: valid first symbol was 0; current last symbol is 1 (accepting).

## DFA transition table
| State | 0 | 1 | Final? |
|---|---|---|---|
| q0 | q1 | qd | No |
| q1 | q1 | q2 | No |
| q2 | q1 | q2 | Yes |
| qd | qd | qd | No |

## Conversion rules
For each DFA transition \(q_i\xrightarrow{a}q_j\), add a grammar production \(V_i\to aV_j\). For each accepting state, add a production to epsilon. Map q0 to S, q1 to A and q2 to B. The dead state can be omitted because it cannot derive an accepted string.

## Equivalent right-linear grammar
- \(S\to 0A\)
- \(A\to 0A\mid 1B\)
- \(B\to 0A\mid 1B\mid\epsilon\)

## Example derivation
\(S\Rightarrow 0A\Rightarrow 01B\Rightarrow 010A\Rightarrow 0101B\Rightarrow 0101\).

## Test cases
| Input | Condition | Expected |
|---|---|---|
| 01 | Starts 0, ends 1 | Accept |
| 001 | Starts 0, ends 1 | Accept |
| 0111 | Starts 0, ends 1 | Accept |
| 0101 | Starts 0, ends 1 | Accept |
| 101 | Starts with 1 | Reject |
| 000 | Ends with 0 | Reject |
| 11 | Starts with 1 | Reject |
| 0 | Does not end in 1 | Reject |

## Procedure in JFLAP
Open the DFA source and use **Convert → Convert to Grammar**. Compare the generated grammar with the listed productions. If your JFLAP release uses a different grammar XML serialization, create the grammar through the Grammar editor and save it from JFLAP; use the source DFA file independently.

## Conclusion
The DFA is represented by a right-linear grammar. Both recognize strings beginning with 0 and ending with 1.
