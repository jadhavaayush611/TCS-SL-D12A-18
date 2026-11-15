# Validation log – RE to DFA

The DFA's final state represents a completed `abb` suffix. Check all cases through JFLAP Multiple Run.

| Input | Expected |
|---|---|
| `abb` | Accept |
| `aabb` | Accept |
| `babb` | Accept |
| `abababb` | Accept |
| `ab` | Reject |
| `abba` | Reject |
| `abbb` | Reject |
| `bba` | Reject |
