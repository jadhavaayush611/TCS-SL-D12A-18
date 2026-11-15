# Practical 04: DFA Minimization – Strings Ending with 01

**Student:** Aayush Jadhav  
**Roll No.:** 18  
**Class / Division:** D12A  
**Subject:** Theory of Computer Science (26CMPC51)  
**Institution:** Vivekanand Education Society's Institute of Technology (VESIT)  
**Date of Submission:** 16 November 2026  
**JFLAP File:** `18_Aayush_Jadhav_DFA_Original_Ends_with_01_16-11-2026.jff and 18_Aayush_Jadhav_DFA_Minimized_Ends_with_01_16-11-2026.jff`

## Aim
To minimize a five-state DFA using state-equivalence partitioning and obtain an equivalent three-state DFA.

## Language
All binary strings ending in `01`: \(L=(0+1)^*01\).

## Original DFA
The five states are q0–q4. q0 is initial. q2 and q4 are accepting. The transition table is:

| State | 0 | 1 | Final? |
|---|---|---|---|
| q0 | q1 | q0 | No |
| q1 | q3 | q2 | No |
| q2 | q3 | q0 | Yes |
| q3 | q1 | q4 | No |
| q4 | q1 | q0 | Yes |

## Minimization by partitioning
**Initial partition:** separate final and non-final states:
\(P_0=\{\{q_0,q_1,q_3\},\{q_2,q_4\}\}\).

**Refinement:** q0 separates from q1 and q3 because on input `1`, q0 goes to a non-final class, while q1 and q3 go to a final class. q1 and q3 remain equivalent because their transitions lead to the same equivalence classes. q2 and q4 also remain equivalent for the same reason.

Stable partition:
\(P=\{\{q_0\},\{q_1,q_3\},\{q_2,q_4\}\}\).

## Minimized DFA transition table
| Merged state | 0 | 1 | Final? |
|---|---|---|---|
| A = [q0] | B | A | No |
| B = [q1,q3] | B | C | No |
| C = [q2,q4] | B | A | Yes |

## Test cases
| Input | Expected result |
|---|---|
| 01 | Accept |
| 001 | Accept |
| 1101 | Accept |
| 1001 | Accept |
| 0 | Reject |
| 010 | Reject |
| 11 | Reject |
| 011 | Reject |

## Procedure in JFLAP
Open the original DFA and use the state minimization command under **Convert**. Compare the generated result with the supplied minimized machine. Verify test cases on both machines.

## Conclusion
The original five-state DFA reduces to three equivalence classes. The minimized DFA accepts the same language, while no two of its remaining states are equivalent.
