# ERR

To return the error code (`ERR`) and line number (`ERL`) associated with an error.

## Syntax

`v=ERR`

`v=ERL`

## Comments

The variable `ERR` contains the error code for the last occurrence of an error. All the error codes and their definitions are listed in Appendix A of the BASIC User's Guide.

The variable `ERL` contains the line number of the line in which the error was detected.

The `ERR` and `ERL` variables are usually used in [IF...THEN](IF...THEN), or [ON ERROR GOTO](ON-ERROR-GOTO], or [GOSUB](GOSUB) statements to direct program flow in error trapping.

If the statement that caused the error was a direct mode statement, `ERL` will contain 65535. To test if an error occurred in a direct mode statement, use a line of the following form:

`IF 65535=ERL THEN ...`

Otherwise, use the following:

```vb
IF ERR=error code THEN GOSUB 4000
IF ERL=line number THEN GOSUB 4010
```

## Note

If the line number is not on the right side of the relational operator, it cannot be renumbered by [RENUM].

Because `ERL` and `ERR` are reserved variables, neither may appear to the left of the equal sign in a `LET` (assignment) statement.
