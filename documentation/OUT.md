# OUT

To send a byte to a machine output port.

## Syntax

`OUT h,j`

## Comments

*h* and *j* are integer expressions. *h* may be within the range of 0 to 65535. *j* may be within the range of 0 to 255. *h* is a machine port number, and *j* is the data to be transmitted.

`OUT` is the complementary statement to the [INP](INP) function.

## Example

```vb
100 OUT 12345,225
```

Outputs the decimal value 225 to port number 12345. In assembly language, this is equivalent to the following:

```vb
MOV DX,12345
MOV AL,255
OUT DX,AL
```
