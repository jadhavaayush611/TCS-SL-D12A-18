# Validation log – DFA divisible by 3

Expected-result checks are derived from the remainder transition rule. Re-run these cases using JFLAP Input → Multiple Run before submission.

| Input | State trace | Expected |
|---|---|---|
| `ε` | q0 | Accept |
| `0` | q0 → q0 | Accept |
| `1` | q0 → q1 | Reject |
| `10` | q0 → q1 → q2 | Reject |
| `11` | q0 → q1 → q0 | Accept |
| `110` | q0 → q1 → q0 → q0 | Accept |
| `1001` | q0 → q1 → q2 → q1 → q0 | Accept |
| `1111` | q0 → q1 → q0 → q1 → q0 | Accept |
| `101` | q0 → q1 → q2 → q2 | Reject |
| `100` | q0 → q1 → q2 → q1 | Reject |
| `1100` | q0 → q1 → q0 → q0 → q0 | Accept |
| `1010` | q0 → q1 → q2 → q2 → q1 | Reject |
