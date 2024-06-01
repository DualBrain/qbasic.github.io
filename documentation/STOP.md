# STOP

To terminate program execution and return to command level.

## Syntax

`STOP`

## Comments

`STOP` statements may be used anywhere in a program to terminate execution. When a `STOP` is encountered, the following message is printed:

`Break in line nnnnn`

Unlike the [END](END) statement, the `STOP` statement does not close files.

BASIC always returns to command level after a `STOP` is executed. Execution is resumed by issuing a [CONT](CONT) command.

## Example

```vb
10 INPUT A, B, C
20 K=A^2*5.3: L=B^3/.26
30 STOP
40 M=C*K+100: PRINT M
```

```text
RUN
 ? 1, 2, 3
BREAK IN 30
PRINT L
 30.76923
CONT
 115.9
```
