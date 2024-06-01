# COS

To return the cosine of the range of `1x1`.

## Syntax

`COS(x)`

## Comments

`x` must be the radians. `COS` is the trigonometric cosine function. To convert from degrees to radians, multiply by `π/180`. `COS(x)` is calculated in single precision.

## Examples

```vb
10 X=2*COS(.4)
20 PRINT X
```

```text
 1.842122
```

```vb
10 PI=3.141593
20 PRINT COS(PI)
30 DEGREES=180
40 RADIANS=DEGREES*PI/180
50 PRINT COS(RADIANS)
```

```text
 -1
 -1
```

## See Also

* [PRINT](PRINT)
