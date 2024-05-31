# WIDTH

To set the printed line width in number of characters for the screen and line printer.

## Syntax

`WIDTH size`

`WIDTH file number, size`

`WIDTH "dev", size`

## Comments

*size*, an integer within the range of 0 to 255, is the new width.

*file number* is the number of the file that is open.

*dev* is a valid string expression identifying the device. Valid devices are `SCRN:`, `LPT1:`, `LPT2:`, `LPT3:`, `COM1:`, and `COM2:`.

### Changing Screen Width

The following statements are used to set the screen width. Only a 40- or 80-column width is allowed.

```vb
WIDTH size
WIDTH "SCRN:", size
```

See the [SCREEN](SCREEN) statement for more information.

Changing [SCREEN](SCREEN) mode affects screen width only when moving between [SCREEN](SCREEN) `2` and [SCREEN](SCREEN) `1` or [SCREEN](SCREEN) `0`.

> Changing the screen width clears the screen and sets the border screen color to black.

### Changing Line printer Width

The following `WIDTH` statement is used as a deferred width assignment for the line printer. This statement stores the new width value without actually changing the current width setting:

```vb
WIDTH "LPT1:", size
```

A statement of the following form recognizes this stored width value:

```vb
OPEN "LPT1:" FOR OUTPUT AS number
```

and uses it while the file is open:

```vb
WIDTH file number, size
```

If the file is open to `lpt1:`, line printer width is immediately changed to the new size specified. This allows the width to be changed at will while the file is open. This form of `WIDTH` has meaning only for `lpt1:`. After outputting the indicated number of characters from the open file, BASIC inserts a carriage return at the end of the line and wraps the output, if the width is less than the length of the record.

Valid widths for the line printer are 1 through 255.

Specifying `WIDTH 255` for the line printer (`lpt1:`) enables line wrapping. This has the effect of infinite width.

Any value entered outside of these ranges results in an "Illegal function call" error. The previous value is retained.

Using the `WIDTH` statement on a communications file causes a carriage return to be sent after the number of characters specified by the size attribute. It does not alter either the receive or transmit buffer.

## Example

```vb
10 WIDTH "LPT1:", 75
20 OPEN "LPT1:" FOR OUTPUT AS #1
.
.
.
6020 WIDTH #1, 40
```

Line 10 stores a line printer width of 75 characters per line.

Line 20 opens file #1 to the line printer and sets the width to 75 for subsequent PRINT #1, statements.

Line 6020 changes the current line printer width to 40 characters per line.
