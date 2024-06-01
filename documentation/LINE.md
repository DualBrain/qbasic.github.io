# LINE

To draw lines and boxes on the screen.

## Syntax

`LINE [(x1,y1)]-(x2,y2) [,[attribute][,B[F]][,style]]`

## Comments

*x1,y1* and *x2,y2* specify the end points of a line.

Resolution mode is determined by the [SCREEN](SCREEN) statement.

*attribute* specifies color or intensity of the displayed pixel (see the [COLOR](COLOR) and [PALETTE](PALETTE) statements).

`B` (box) draws a box with the points (*x1,y1*) and (*x2,y2*) at opposite corners.

`BF` (filled box) draws a box (as `,B`) and fills in the interior with points.

## Note

If attribute is not specified, two commas must be used before `B` or `BF`.

`LINE` supports the additional argument *style*. *style* is a 16-bit integer mask used when putting down pixels on the screen. This is called line-styling.

Each time `LINE` stores a point on the screen, it uses the current circulating bit in *style*. If that bit is 0, no store will be done. If the bit is a 1, then a normal store is done. After each point, the next bit position in *style* is selected.

Since a 0 bit in *style* does not clear out the old contents, you may wish to draw a background line before a styled line, in order to force a known background.

*style* is used for normal lines and boxes, but is illegal for filled boxes.

If the `BF` parameter is used with the *style* parameter, a "Syntax" error will occur.

When out-of-range values are given in the `LINE` statement, the coordinates that are out of range are not visible on the screen. This is called line-clipping.

In the syntax shown here, the coordinate form `STEP (x offset, y offset)` is not shown. However, this form can be used wherever a coordinate is used.

In a `LINE` statement, if the relative form is used on the second coordinate, it is relative to the first coordinate.

After a `LINE` statement, the last referenced point is *x2*, *y2*.

The simplest form of `LINE` is the following:

`LINE -(xz,yz)`

This draws a line from the last point referenced to the point (*x2,y2*) in the foreground color.

## Examples

```vb
LINE (0,100)-(639,100)
```

Draws a horizontal line which divides the screen in half from top to bottom in [SCREEN](SCREEN) `2`.

```vb
LINE (160,0)-(160,199)
```

Draws a vertical line which divides the screen in half from left to right in [SCREEN](SCREEN) `1`; makes a one-quarter/three-quarter division in [SCREEN](SCREEN) `2`.

```vb
LINE (0,0)-(319,199)
```

Draws a diagonal line from the top left to lower right corner of the screen in [SCREEN](SCREEN) `1`, and from the upper left corner to the center bottom of the screen in [SCREEN](SCREEN) `2`.

```vb
LINE (10,10)-(20,20),2
```

Draws a line in color 2 if [SCREEN](SCREEN) `1` is previously specified (see the [COLOR](COLOR) statement).

```vb
10 CLS
20 LINE -(RND*319,RND*199),RND*4
30 GOTO 20
```

Draw lines forever using random attributes.

```vb
10 FOR X=0 TO 319
20 LINE (X,0)-(X,199),X AND 1
30 NEXT
```

Draws an alternating pattern: line on, line off.

```vb
10 CLS
20 LINE -(RND*639,RND*199),RND*2,BF
30 GOTO 20
```

Draws lines all over the screen.

```vb
LINE (0,0)-(100,175),,B
```

Draws a square box in the upper left corner of the screen.

```vb
LINE (0,0)-(100,175),,BF
```

Draws the same box and fills it in.

```vb
LINE (0,0)-(100,175),2,BF
```

Draws the same filled box in magenta in [SCREEN](SCREEN) `1`.

```vb
LINE (0,0)-(100,350),,B
```

Draws the same box if [SCREEN](SCREEN) `2` is specified.

```vb
400 SCREEN 1
410 LINE(160,100)-(160,199),,,&HCCCC
```

Draws a vertical dotted line down the center of the screen in [SCREEN](SCREEN) `1`.

```vb
220 SCREEN 2
230 LINE(300,100)-(400,50),,B,&HAAAA
```

Draws a rectangle with a dotted line in [SCREEN](SCREEN) `2`.

```vb
LINE (0,0)-(160,100),3,,&HFF00
```

Draws a dotted line from the upper left corner to the screen center.
