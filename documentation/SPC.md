# SPC

To skip a specified number of spaces in a [PRINT](PRINT) or an [LPRINT](PRINT) statement.

## Syntax

`SPC(n)`

## Comments

*n* must be within the range of 0 to 255.

If *n* is greater than the defined width of the printer or the screen, the value used will be *n* [MOD](MOD) width.

A semicolon is assumed to follow the `SPC(n)` command.

`SPC` may only be used with [PRINT](PRINT), [LPRINT](LPRINT) and [PRINT#](PRINT-FILE) statements (see the [SPACE$](SPACE$) function).

## Example

```vb
PRINT "OVER" SPC(15) "THERE"
```

```text
 OVER               THERE
```
