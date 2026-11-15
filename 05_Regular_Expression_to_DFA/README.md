# Practical 05: Regular Expression to DFA – Strings Ending with abb

**Student:** Aayush Jadhav  
**Roll No.:** 18  
**Class / Division:** D12A  
**Subject:** Theory of Computer Science (26CMPC51)  
**Institution:** Vivekanand Education Society's Institute of Technology (VESIT)  
**Date of Submission:** 16 November 2026  
**JFLAP File:** `18_Aayush_Jadhav_Regular_Expression_abb_16-11-2026.jff and 18_Aayush_Jadhav_DFA_from_abb_16-11-2026.jff`

## Aim
To express the language of strings ending in `abb` as a regular expression and construct an equivalent DFA.

## Regular expression
Alphabet: \(\Sigma=\{a,b\}\). Expression: \(R=(a+b)^*abb\). It describes any prefix over a and b followed by the required suffix `abb`.

## DFA state meaning
The DFA tracks the longest suffix of the input read so far that is also a prefix of `abb`:
- q0: no non-empty prefix matched
- q1: suffix `a`
- q2: suffix `ab`
- q3: suffix `abb` (accepting)

## Transition table
| State | a | b | Final? |
|---|---|---|---|
| q0 | q1 | q0 | No |
| q1 | q1 | q2 | No |
| q2 | q1 | q3 | No |
| q3 | q1 | q0 | Yes |

## Test cases
| Input | Ends with abb? | Expected |
|---|---|---|
| abb | Yes | Accept |
| aabb | Yes | Accept |
| babb | Yes | Accept |
| abababb | Yes | Accept |
| ab | No | Reject |
| abba | No | Reject |
| abbb | No | Reject |
| bba | No | Reject |

## Procedure in JFLAP
Open the regular-expression file in JFLAP's Regular Expression module. Use the conversion option to generate a finite automaton and compare it with the provided DFA. Run all listed inputs on the converted DFA.

## Conclusion
The expression `(a+b)*abb` and the supplied DFA describe the same set of strings: all strings over `{a,b}` that end with `abb`.
