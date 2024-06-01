# LOCATE

To move the cursor to the specified position on the active screen. Optional parameters cause the cursor to blink on and off, and define the start and stop raster lines for the cursor. A raster line is the vertical or horizontal distance between two adjacent, addressable points on your screen.

## Syntax

`LOCATE [row][,[col][,[cursor][,[start] [,stop]]]]`

## Comments

*row* is the screen line number, a numeric expression within the range of 1 to 25.

*col* is the screen column number, a numeric expression within the range of 1 to 40, or 1 to 80, depending upon screen width.

*cursor* is a Boolean value indicating whether the cursor is visible; zero is off, nonzero is on.

*start* is the cursor start scan line, a numeric expression within the range of 0 to 31.

*stop* is the cursor stop scan line, a numeric expression within the range of 0 to 31.

When the cursor is moved to the specified position, subsequent [PRINT](PRINT) statements begin placing characters at this location. Optionally, the `LOCATE` statement may be used to start the cursor blinking on or off, or change the size of the blinking cursor.

Any values entered outside of these ranges results in "Illegal function call" errors. Previous values are retained.

As you set up the parameters for the `LOCATE` statement, you may find that you do not wish to change one or more of the existing specifications. To omit a parameter from this `LOCATE` statement, insert a comma for the parameter that is being skipped. If the omitted parameter(s) occurs at the end of the statement, you do not have to type the comma.

If the start scan line parameter is given and the stop scan line parameter is omitted, stop assumes the start value.

## Examples

```vb
10 LOCATE 1,1
```

Moves cursor to the home position in the upper-left corner.

```vb
20 LOCATE ,,1
```

Makes the cursor visible. Its position remains unchanged. Notice that the first two parameters are not used. A comma has been inserted for each omitted parameter.

```vb
30 LOCATE ,,,7
```

Cursor position and visibility remain unchanged. Sets the cursor to appear at the bottom of the character starting and ending on scan line 7.

```vb
40 LOCATE 5,1,1,0,7
```

Moves the cursor to line 5, column 1, and turns the cursor on. The cursor covers an entire character cell, starting at scan line 0 and ending on scan line 7.
