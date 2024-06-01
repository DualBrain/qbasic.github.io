# SWAP

To exchange the values of two variables.

## Syntax

`SWAP variable1,variable2`

## Comments

Any type variable may be swapped (integer, single-precision, double-precision, string), but the two variables must be of the same type or a `Type mismatch` error results.

## Example

```vb
a = 1
b = 2
SWAP a, b
PRINT a, b
```

```txt
2        1
```
