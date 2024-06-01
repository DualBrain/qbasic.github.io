# ON ERROR GOTO

To enable error trapping and specify the first line of the error-handling subroutine.

## Syntax

`ON ERROR GOTO line number`

## Comments

Once error trapping has been enabled, all errors detected by BASIC, including direct mode errors, (for example, syntax errors) cause BASIC to branch to the line in the program which begins the specified error-handling subroutine.

BASIC branches to the line specified by the `ON ERROR` statement until a [RESUME](RESUME) statement is found.

If *line number* does not exist, an `Undefined line` error results.

To disable error trapping, execute the following statement:

```vb
ON ERROR GOTO 0
```

Subsequent errors print an error message and halt execution.

An `ON ERROR GOTO 0` statement in an error-trapping subroutine causes BASIC to stop and print the error message for the error that caused the trap. It is recommended that all error-trapping subroutines execute an `ON ERROR GOTO 0` if an error is encountered for which there is no recovery action.

If an error occurs during execution of an error-handling subroutine, the BASIC error message is printed and execution terminated. Error trapping does not occur within the error-handling subroutine.

## Example

```vb
10 ON ERROR GOTO 1000
20 '...
999 END
1000 A=ERR: B=ERL
1010 PRINT A, B
1020 RESUME NEXT
```

Line 1010 prints the type and location of the error on the screen (see the [ERR](ERR) and [ERL](ERL) variables).

Line 1020 causes program execution to continue with the line following the error.
