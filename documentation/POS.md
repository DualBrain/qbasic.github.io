# POS

To return the current cursor position.

## Syntax

`POS(c)`

## Comments

The leftmost position is 1.

*c* is a dummy argument.

## Example

```vb
10 CLS
20 WIDTH 80
30 A$=INKEY$:IF A$=""THEN GOTO 30 ELSE PRINT A$;
40 IF POS(X)>10 THEN PRINT CHR$(13);
50 GOTO 30
```

Causes a carriage return after the 10th character is printed on each line of the screen.
