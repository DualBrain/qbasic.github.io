# GOSUB

To branch to, and return from, a subroutine.

## Syntax

`GOSUB line number`

`RETURN [line number]`

## Comments

*line number* is the first line number of the subroutine.

A subroutine may be called any number of times in a program, and a subroutine may be called from within another subroutine. Such nesting of subroutines is limited only by available memory.

A `RETURN` statement in a subroutine causes BASIC to return to the statement following the most recent `GOSUB` statement. A subroutine can contain more than one `RETURN` statement, should logic dictate a `RETURN` at different points in the subroutine.

Subroutines can appear anywhere in the program, but must be readily distinguishable from the main program.

To prevent inadvertent entry, precede the subroutine by a [STOP](STOP), [END](END), or [GOTO](GOTO) statement to direct program control around the subroutine.

```vb
GOSUB Subroutine
PRINT "BACK FROM SUBROUTINE"
END

Subroutine:
10 GOSUB 40
20 PRINT "BACK FROM SUBROUTINE"
30 END
40 PRINT "SUBROUTINE";
50 PRINT " IN";
60 PRINT " PROGRESS"
70 RETURN
```

```text
 SUBROUTINE IN PROGRESS
 BACK FROM SUBROUTINE
```

The [END](END) statement in line 30 prevents re-execution of the subroutine.
