# IMP

To return the byte read from machine port *n*.

## Syntax

`INP(n)`

## Comments

*n* represents a valid machine port number within the range of 0 to 65535.

The `INP` function is one way in which a peripheral device may communicate with a BASIC program.

`INP` is the complementary function to the [OUT](OUT) statement.

## Examples

```vb
100 A=INP(56)
```

Upon execution, variable A contains the value present on port 56. The number returned will be within the range of 0 to 255, decimal.

The assembly language equivalent to this statement is

```text
MOV DX,56
IN AL,DX
```
