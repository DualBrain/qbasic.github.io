# PEN

To read the light pen.

## Syntax

As a statement:

`PEN ON`

`PEN OFF`

`PEN STOP `

As a function:

`x = PEN(n)`

## Comments

`PEN ON` enables the `PEN` read function.

`PEN OFF` disables the `PEN` read function.

`PEN STOP` disables trapping. It remembers the event so immediate trapping occurs when `PEN ON` is executed.

The `PEN` function is initially off. A `PEN ON` statement must be executed before any `PEN` read function calls can be made, or a `PEN` read function call results in an "Illegal function call" error.

`x = PEN(n)` reads the light pen coordinates.

*x* is the numeric variable receiving the `PEN` value.

*n* is an integer within the range of 0 to 9.

Light pen coordinates:

* `n = 0` If `PEN` was down since last poll, returns -1; if not, returns 0.
* `n = 1` Returns the x-pixel coordinate when `PEN` was last activated. The range is within 0 to 319 for medium resolution; 0 to 639, for high resolution.
* `n = 2` Returns the y-pixel coordinate when `PEN` was last activated. The range is within 0 to 199.
* `n = 3` Returns the current `PEN` switch value. Returns -1 if down; 0 if up.
* `n = 4` Returns the last known valid x-pixel coordinate. The range is within 0 to 319 for medium resolution; or 0 to 639 for high resolution.
* `n = 5` Returns the last known valid y-pixel coordinate. The range is within 0 to 199.
* `n = 6` Returns the character row position when `PEN` was last activated. The range is within 1 to 24.
* `n = 7` Returns the character column position when `PEN` was last activated. The range is within 1 to 40, or 1 to 80, depending on the screen width.
* `n = 8` Returns the last known valid character row. The range is within 1 to 24.
* `n = 9` Returns the last known valid character column position. The range is within 1 to 40, or 1 to 80, depending on the screen width.

For execution speed improvements, turn the pen off with a `PEN OFF` statement for those programs not using the light pen.

When the pen is in the border area of the screen, the values returned will be inaccurate.

## Example

```vb
50 PEN ON
60 FOR I=1 to 500
70 X=PEN(0): X1=PEN(3)
80 PRINT X, X1
90 NEXT
100 PEN OFF
```

This example prints the pen value since the last poll and the current value.
