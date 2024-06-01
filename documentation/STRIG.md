# STRIG

To return the status of the joystick triggers.

## Syntax

As a statement:

`STRIG ON`

`STRIG OFF`

As a function:

`x=STRIG(n)`

## Comments

`STRIG ON` must be executed before any [STRIG(n)](STRIG(n)) function calls may be made. Once `STRIG ON` is executed, BASIC will check to see if a button has been pressed before every statement is executed. `STRIG OFF` disables the checking.

*x* is a numeric variable for storing the result.

*n* is a numeric expression within the range of 0 to 7 that returns the following values:

| Value of n | Returns |
| ---------- | ------- |
| 0 | -1 if trigger A1 was pressed since the last STRIG(0) statement; returns 0, if not. |
| 1 | -1 if trigger A1 is currently pressed; returns 0, if not. |
| 2 | -1 if trigger B1 was pressed since the last STRIG(2) statement; returns 0, if not. |
| 3 | -1 if trigger B1 is currently pressed; returns 0, if not. |
| 4 | -1 if trigger A2 was pressed since the last STRIG(4) statement; returns 0 if not. |
| 5 | -1 if trigger A2 is currently pressed; returns 0, if not. |
