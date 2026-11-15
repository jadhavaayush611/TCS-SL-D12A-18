# Validation log – NFA to DFA

Run each string against both source and converted machines in JFLAP. The two result columns should match.

| String | Expected result |
|---|---|
| `ab` | Accept |
| `aab` | Accept |
| `bab` | Accept |
| `abbab` | Accept |
| `a` | Reject |
| `aba` | Reject |
| `abb` | Reject |
| `b` | Reject |
