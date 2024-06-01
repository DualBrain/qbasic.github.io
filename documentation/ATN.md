# ATN

To return the arctangent of `x`, when `x` is expressed in radians.

## Syntax

`ATN(x)`

## Comments

The result is within the range of `-π/2` to `π/2`. The expression `x` may be any numeric type. The evaluation of `ATN` is performed in single precision.

To convert from degrees to radians, multiply by `π/180`.

## Example

```vb
10 X = 3
20 PRINT ATN(X)
```

```text
 ? 3
 1.249046
```

Prints the arctangent of `3` radians (`1.249046`).

## See Also

* [PRINT](PRINT)
