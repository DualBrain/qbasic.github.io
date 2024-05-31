# STRING$

To return a string of length *n* whose characters all have ASCII code *j*, or the first character of *x$*

## Syntax

`STRING$(n,j)`

`STRING$(n,x$)`

## Comments

`STRING$` is also useful for printing top and bottom borders on the screen or the printer.

*n* and *j* are integer expressions in the range `0` to `255`.

## Example

```vb
10 X$ = STRING$(10, 45)
20 PRINT X$ "MONTHLY REPORT" X$
```

```text
----------MONTHLY REPORT----------
```

`45` is the decimal equivalent of the ASCII symbol for the minus (`-`) sign.
