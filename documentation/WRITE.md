# WRITE

To output data to the screen.

## Syntax

`WRITE[list of expressions]`

## Comments

If *list of expressions* is omitted, a blank line is output. If *list of expressions* is included, the values of the expressions are output at the terminal. The expressions in the list may be numeric and/or string expressions, and must be separated by commas or semicolons.

When printed items are output, each item will be separated from the last by a comma. Printed strings are delimited by double quotation marks. After the last item in the list is printed, BASIC inserts a carriage return/line feed.

The difference between `WRITE` and [PRINT](PRINT) is that `WRITE` inserts commas between displayed items and delimits strings with double quotation marks. Positive numbers are not preceded by blank spaces.

`WRITE` outputs numeric values using the same format as the [PRINT](PRINT) statement.

## Example

```vb
10 A=80: B=90: C$="THAT'S ALL"
20 WRITE A, B, C$
```

```text
 80, 90, "THAT'S ALL"
```
