# END

To terminate program execution, close all files, and return to command level.

## Syntax

`END`

## Comments

`END` statements may be placed anywhere in the program to terminate execution.

Unlike the [STOP](STOP) statement, `END` does not cause a `Break in line xxxx` message to be printed.

An `END` statement at the end of a program is optional. BASIC always returns to command level after an `END` is executed.

`END` closes all files.

## Example

```vb
520 IF K>1000 THEN END ELSE GOTO DoItAgain
```

Ends the program and returns to command level whenever the value of `K` exceeds `1000`.

## See Also

* [STOP](STOP), [IF...THEN](IF...THEN), [GOTO](GOTO)
