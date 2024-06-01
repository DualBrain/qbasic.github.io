# SCREEN (Function)

To return the ASCII code (0-255) for the character at the specified row (line) and column on the screen.

## Syntax

``x=SCREEN(row,col[,z])``

## Comments

*x* is a numeric variable receiving the ASCII code returned.

*row* is a valid numeric expression within the range 1 to 25.

*col* is a valid numeric expression 1 to 40, or 1 to 80, depending upon screen width setting. See the [WIDTH](WIDTH) statement.

*z* is a valid numeric expression with a true or false value. It may be used only in alpha mode.

The ordinal of the character at the specified coordinates is stored in the numeric variable. In alpha mode, if the optional parameter *z* is given and is true (nonzero), the color attribute for the character is returned instead of the ASCII code for the character (see the [COLOR](COLOR) statement).

Any values entered outside of the range indicated result in an "Illegal function call" error. Row 25 may be referenced only if the function key is off.

## Examples

```vb
100 X=SCREEN (10, 10)
```

If the character at 10,10 is A, then X is 65.

```vb
110 X=SCREEN (1, 1, 1)
```

Returns the color attribute of the character in the upper-left corner of the screen.
