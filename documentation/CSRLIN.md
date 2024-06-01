# CSRLIN

To return the current line (row) position of the cursor.

## Syntax

`y=CSRLIN`

## Comments

*y* is a numeric variable receiving the value returned. The value returned is within the range of 1 to 25.

The `CSRLIN` variable returns the vertical coordinate of the cursor on the active page (see the [SCREEN](SCREEN) statement).

`x=POS(0)` returns the column location of the cursor. The value returned is within the range of 1 to 40, or 1 to 80, depending on the current screen width (see the [POS](POS) function).

## Examples

```vb
10 Y=CSRLIN
20 X=POS(0)
30 LOCATE 24, 1
40 PRINT "HELLO"
50 LOCATE Y, X
```

```text
 HELLO
```

The `CSRLIN` variable in line 10 records the current line.

The [POS](POS) function in line 20 records the current column.

In line 40, the [PRINT](PRINT) statement displays the comment "HELLO" on the 24th line of the screen.

The [LOCATE](LOCATE) statement in line 50 restores the position of the cursor to the original line and column.

## See Also

* [POS](POS), [PRINT](PRINT), [LOCATE](LOCATE)
