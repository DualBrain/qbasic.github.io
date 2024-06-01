# SQR

Returns the square root of *x*.

## Syntax

`SQR(x)`

## Comments

*x* must be greater than or equal to 0.

`SQR(x)` is computed in single-precision unless the `/d` switch is used when BASIC is executed.

## Example

```vb
10 FOR X=10 TO 25 STEP 5
20 PRINT X; SQR(X)
30 NEXT
```

```text
 10 3.162278
 15 3.872984
 20 4.472136
 25 5
```
