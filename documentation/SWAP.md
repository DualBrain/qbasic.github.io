# SWAP

To exchange the values of two variables.

## Syntax

`SWAP variable1,variable2`

## Comments

Any type variable may be swapped (integer, single-precision, double-precision, string), but the two variables must be of the same type or a `Type mismatch` error results.

## Example

```vb
10 A$ = "ONE ": B$ = "ALL ": C$ = "FOR "
20 PRINT A$ C$ B$
30 SWAP A$, B$
40 PRINT A$ C$ B$
```

```text
ONE FOR ALL
ALL FOR ONE
```

Line 30 swaps the values in the *A$* and *B$* strings.
