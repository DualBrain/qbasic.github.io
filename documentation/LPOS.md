# LPOS

To return the current position of the line printer print head within the line printer buffer.

## Syntax

`LPOS(x)`

## Comments

`LPOS` does not necessarily give the physical position of the print head.

*x* is a dummy argument.

If the printer has less than the 132 characters-per-line capability, it may issue internal line feeds and not inform the computer internal line printer buffer. If this has happened, the value returned by `LPOS(x)` may be incorrect. `LPOS(x)` simply counts the number of printable characters since the last line feed was issued.

## Example

The following line causes a carriage return after the 60th character is printed on a line:

```vb
100 IF LPOS(X)>60 THEN LPRINT CHR$(13)
```
