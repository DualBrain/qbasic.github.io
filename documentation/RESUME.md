# RESUME

To continue program execution after an error-recovery procedure has been performed.

## Syntax

`RESUME`

`RESUME 0`

`RESUME NEXT`

`RESUME line number `

## Comments

Any one of the four formats shown above may be used, depending upon where execution is to resume:

- `RESUME` or `RESUME 0` Execution resumes at the statement that caused an error.
- `RESUME NEXT` Execution resumes at the statement immediately following the one that caused an error.
- `RESUME line number` Execution resumes at the specified line number.

A `RESUME` statement that is not in an error trapping routine causes a `RESUME without error` message to be printed.

## Example

```vb
10 ON ERROR GOTO 900
.
.
.
900 IF (ERR = 230) AND (ERL = 90) THEN PRINT "TRY AGAIN": RESUME 80
```

If an error occurs after line 10 is executed, the action indicated in line 900 is taken and the program continues at line 80.
