# PRINT

To output a display to the screen.

## Syntax

`PRINT [list of expressions][;]`

`?[list of expressions][;]`

## Comments

If list of expressions is omitted, a blank line is displayed.

If list of expressions is included, the values of the expressions are displayed. Expressions in the list may be numeric and/or string expressions, separated by commas, spaces, or semicolons. String constants in the list must be enclosed in double quotation marks.

For more information about strings, see the [STRING$](STRING$) function.

A question mark (`?`) may be used in place of the word `PRINT` when using the BASIC program editor.

## Print Positions

BASIC divides the line into print zones of 14 spaces. The position of each item printed is determined by the punctuation used to separate the items in the list:

| Separator | Print Position |
| --------- | -------------- |
| ,         | Beginning of next zone |
| ;         | Immediately after last value |
| space(s)  | Immediately after last value |

If a comma, semicolon, or SPC or TAB function ends an expression list, the next `PRINT` statement begins printing on the same line, accordingly spaced. If the expression list ends without a comma, semicolon, or [SPC](SPC) or [TAB](TAB) function, a carriage return is placed at the end of the lines (BASIC places the cursor at the beginning of the next line).

A carriage return/line feed is automatically inserted after printing width characters, where width is 40 or 80, as defined in the [WIDTH](WIDTH) statement. This results in two lines being skipped when you print exactly 40 (or 80) characters, unless the `PRINT` statement ends in a semicolon.

When numbers are printed on the screen, the numbers are always followed by a space. Positive number are preceded by a space. Negative numbers are preceded by a minus (-) sign. Single-precision numbers are represented with seven or fewer digits in a fixed-point or integer format.

See the [LPRINT](LPRINT) and [LPRINT USING](LPRINT-USING) statements for information on sending data to be printed on a printer.

## Examples

```vb
10 X$= STRING$(10,45)
20 PRINT X$"MONTHLY REPORT" X$
```

```text
----------MONTHLY REPORT----------
``` 

`45` is the decimal equivalent of the ASCII symbol for the minus (`-`) sign.
