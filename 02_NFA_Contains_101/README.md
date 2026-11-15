# Practical 02: Nondeterministic Finite Automaton (NFA) – Strings Containing 101

**Student:** Aayush Jadhav  
**Roll No.:** 18  
**Class / Division:** D12A  
**Subject:** Theory of Computer Science (26CMPC51)  
**Institution:** Vivekanand Education Society's Institute of Technology (VESIT)  
**Date of Submission:** 16 November 2026  
**JFLAP File:** `18_Aayush_Jadhav_NFA_Contains_101_16-11-2026.jff`

## Aim
To construct an NFA that accepts every binary string containing `101` as a substring.

## Language
\(L=\{w\in\{0,1\}^*: w\text{ contains }101\}=(0+1)^*101(0+1)^*\).

## Theory and state meaning
The initial state scans any prefix. On reading a `1`, the NFA can either continue scanning or guess that this symbol begins the required pattern. The next two states check for `0` and `1`. Once the complete substring is found, the final state loops on both symbols so any suffix is allowed.

## Formal definition
\(M=(Q,\Sigma,\delta,q_0,F)\), where \(Q=\{q_0,q_1,q_2,q_3\}\), \(\Sigma=\{0,1\}\), start state is \(q_0\), and \(F=\{q_3\}\).

## Transition table
| State | Input 0 | Input 1 |
|---|---|---|
| q0 | {q0} | {q0,q1} |
| q1 | {q2} | ∅ |
| q2 | ∅ | {q3} |
| q3 | {q3} | {q3} |

## Test cases
| Input | Contains 101? | Expected result |
|---|---|---|
| 101 | Yes | Accept |
| 00101 | Yes | Accept |
| 11010 | Yes | Accept |
| 010110 | Yes | Accept |
| 1011 | Yes | Accept |
| 0000 | No | Reject |
| 1001 | No | Reject |
| 01001 | No | Reject |
| 111000 | No | Reject |

## Procedure in JFLAP
Open the `.jff` file and use **Input → Multiple Run** to test the positive and negative examples. For an NFA, a string is accepted when at least one computation path finishes in the final state.

## Conclusion
The NFA recognizes binary strings containing `101`. Its nondeterministic branch allows it to select a possible beginning of the target substring while continuing to scan the prefix.
