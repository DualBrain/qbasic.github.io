# LPRINT

To print data at the line printer.

## Syntax

`LPRINT [list of expressions][;]`

`LPRINT USING string exp; list of expressions[;]`

## Comments

*list of expressions* consists of the string or numeric expression separated by semicolons.

*string expressions* is a string literal or variable consisting of special formatting characters. The formatting characters determine the field and the format of printed strings or numbers.

These statements are the same as [PRINT](PRINT) and [PRINT USING](PRINT-USING), except that output goes to the line printer. For more information about string and numeric fields and the variables used in them, see the [PRINT](PRINT) and [PRINT USING](PRINT-USING) statements.

The `LPRINT` and `LPRINT USING` statements assume that your printer is an 80-character-wide printer.

To reset the number of characters that you can print across the printed page (assuming that your printer is wider than 80 characters), see the [WIDTH](WIDTH) statement.
