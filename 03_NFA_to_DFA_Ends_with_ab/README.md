# Practical 03: NFA to DFA Conversion – Strings Ending in ab

**Student:** Aayush Jadhav  
**Roll No.:** 18  
**Class / Division:** D12A  
**Subject:** Theory of Computer Science (26CMPC51)  
**Institution:** Vivekanand Education Society's Institute of Technology (VESIT)  
**Date of Submission:** 16 November 2026  
**JFLAP File:** `18_Aayush_Jadhav_NFA_Source_Ends_with_ab_16-11-2026.jff and 18_Aayush_Jadhav_DFA_Converted_Ends_with_ab_16-11-2026.jff`

## Aim
To convert an NFA that recognizes strings over `{a,b}` ending in `ab` into an equivalent DFA by subset construction.

## Language
\(L=(a+b)^*ab\).

## Source NFA
States: \(q_0,q_1,q_2\). Start: \(q_0\). Final: \(q_2\). The NFA loops at q0 on `a` and `b`, and may also move from q0 to q1 on `a`; q1 moves to q2 on `b`.

### NFA transition table
| State | a | b |
|---|---|---|
| q0 | {q0,q1} | {q0} |
| q1 | ∅ | {q2} |
| q2 | ∅ | ∅ |

## Subset construction
Name the reachable DFA subsets:
- A = {q0} (initial)
- B = {q0,q1}
- C = {q0,q2} (final because it contains q2)

### DFA transition table
| DFA state | a | b | Final? |
|---|---|---|---|
| A = {q0} | B | A | No |
| B = {q0,q1} | B | C | No |
| C = {q0,q2} | B | A | Yes |

A DFA subset is accepting whenever it contains at least one accepting NFA state.

## Test cases
| Input | Ends with ab? | NFA | DFA |
|---|---|---|---|
| ab | Yes | Accept | Accept |
| aab | Yes | Accept | Accept |
| bab | Yes | Accept | Accept |
| abbab | Yes | Accept | Accept |
| a | No | Reject | Reject |
| aba | No | Reject | Reject |
| abb | No | Reject | Reject |
| b | No | Reject | Reject |

## Procedure in JFLAP
Open the source NFA. Use **Convert → Convert to DFA** (or the equivalent conversion option in your JFLAP version), follow the subset-construction steps, and compare the generated DFA with the supplied converted file. Run the test strings against both machines.

## Conclusion
Subset construction produces a DFA with three reachable subset states. The NFA and DFA recognize the same language of strings ending in `ab`.
