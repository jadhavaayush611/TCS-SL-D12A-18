# Practical 01: Deterministic Finite Automaton (DFA) – Binary Divisible by 3

**Student:** Aayush Jadhav  
**Roll No.:** 18  
**Class / Division:** D12A  
**Subject:** Theory of Computer Science (26CMPC51)  
**Institution:** Vivekanand Education Society's Institute of Technology (VESIT)  
**Date of Submission:** 16 November 2026  
**JFLAP File:** `18_Aayush_Jadhav_DFA_Binary_Divisible_by_3_16-11-2026.jff`

## Aim
To design a DFA that accepts binary strings whose numerical value is divisible by 3.

## Language
\(L=\{w\in\{0,1\}^* : val_2(w)\equiv 0\pmod 3\}\).

## Theory and state meaning
When a new bit \(b\) is read, the value changes from \(v\) to \(2v+b\). Therefore the remainder changes according to \(r'=(2r+b)\bmod 3\). The machine needs three states, one for each possible remainder.

## Formal definition
\(M=(Q,\Sigma,\delta,q_0,F)\), where:
- \(Q=\{q_0,q_1,q_2\}\), \(\Sigma=\{0,1\}\)
- Initial state: \(q_0\); final states: \(F=\{q_0\}\)
- State meaning: \(q_i\) represents remainder \(i\) modulo 3.

## Transition table
| State | Input 0 | Input 1 |
|---|---|---|
| q0 | q0 | q1 |
| q1 | q2 | q0 |
| q2 | q1 | q2 |

## Test cases
| Input | Decimal value | Expected result |
|---|---:|---|
| 0 | 0 | Accept |
| 11 | 3 | Accept |
| 110 | 6 | Accept |
| 1001 | 9 | Accept |
| 1111 | 15 | Accept |
| 1 | 1 | Reject |
| 10 | 2 | Reject |
| 100 | 4 | Reject |
| 101 | 5 | Reject |
| 1010 | 10 | Reject |

## Procedure in JFLAP
Open the `.jff` file, choose **Input → Multiple Run**, enter the strings above and execute them. Confirm that strings representing multiples of 3 end in q0.

## Conclusion
The DFA tracks the remainder of the binary value modulo 3. It accepts exactly those strings whose final remainder is zero.
