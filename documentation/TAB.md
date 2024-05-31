# TAB

Spaces to position n on the screen.

## Syntax

`TAB(n)`

## Comments

If the current print position is already beyond space *n*, `TAB` goes to that position on the next line.

Space 1 is the leftmost position. The rightmost position is the screen width.

*n* must be within the range of 1 to 255.

If the `TAB` function is at the end of a list of data items, BASIC will not return the cursor to the next line. It is as though the `TAB` function has an implied semicolon after it.

`TAB` may be used only in [PRINT](PRINT), [LPRINT](LPRINT), or [PRINT#](PRINT#) statements (see the [SPC](SPC) function).

## Examples

```vb
10 PRINT "NAME" TAB(25) "AMOUNT": PRINT
20 READ A$,B$
30 PRINT A$ TAB(25) B$
40 DATA "G. T. JONES","$25.00"
```

```text
 NAME           AMOUNT
 G. T. JONES    $25.00
```
