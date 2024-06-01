# TAN

To calculate the trigonometric tangent of *x*, in radians.

## Syntax

`TAN(x)`

## Comments

`TAN(x)` is calculated in single-precision.

If `TAN` overflows, the `Overflow` error message is displayed; machine infinity with the appropriate sign is supplied as the result, and execution continues.

To obtain `TAN(x)` when *x* is in degrees, use `TAN(x*pi/180)`.

## Example

```vb
10 Y = TAN(X)
```

When executed, `Y` will contain the value of the tangent of *X* radians.
