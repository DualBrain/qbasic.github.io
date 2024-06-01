# STR$

To return a string representation of the value of *x*.

## Syntax

`STR$(x)`

## Comments

`STR$(x)` is the complementary function to [VAL](VAL)`(x$)` (see the [VAL](VAL) function).

## Example

```vb
5 REM ARITHMETIC FOR KIDS
10 INPUT "TYPE A NUMBER"; N
20 ON LEN(STR$(N)) GOSUB 30, 40, 50
```

This program branches to various subroutines, depending on the number of characters typed before the RETURN key is pressed.