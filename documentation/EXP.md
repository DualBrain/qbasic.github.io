# EXP

To return `e` (the base of natural logarithms) to the power of `x`.

## Syntax

`EXP(x)`

## Comments

`x` must be less than `88.02969`.

If `EXP` overflows, the `Overflow` error message appears; machine infinity with the appropriate sign is supplied as the result, and execution continues.

`EXP(x)` is calculated in single precision.

## Example

```vb
10 X = 5 
20 PRINT EXP(X - 1) 
```

```text
 54.59815
```

Prints the value of `e` to the 4th power.
