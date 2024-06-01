# FIX

To truncate x to a whole number.

## Syntax

`FIX(x)`

## Comments

`FIX` does not round off numbers, it simply eliminates the decimal point and all characters to the right of the decimal point.

`FIX(x)` is equivalent to `SGN(x)*INT(ABS(x))`. The major difference between `FIX` and [INT](INT) is that `FIX` does not return the next lower number for negative *x*.

`FIX` is useful in modulus arithmetic.

## Examples

```vb
PRINT FIX(58.75)
```

```text
 58
```

```vb
PRINT FIX(-58.75)
```

```text
 -58
```
