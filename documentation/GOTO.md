# GOTO

To branch unconditionally out of the normal program sequence to a specified line number.

## Syntax

`GOTO line number`

## Comments

*line number* is any valid line number within the program.

If *line number* is an executable statement, that statement and those following are executed. If it is a non-executable statement, execution proceeds at the first executable statement encountered after line number.

## Example

```vb
10 READ R
20   PRINT "R ="; R;
30   A = 3.14*R^2
40   PRINT "AREA ="; A
50 GOTO 10
60 DATA 5, 7, 12
```

```text
 R = 5 AREA = 78.5
 R = 7 AREA = 153.86
 R = 12 AREA = 452.16
 Out of data in 10
```

The `out of data` advisory is generated when the program attempts to read a fourth [DATA](DATA) statement (which does not exist) in line 60.
