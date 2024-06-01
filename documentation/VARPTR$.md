# VARPTR$

To return a character form of the offset of a variable in memory.

## Syntax

`VARPTR$(variable)`

## Comments

*variable* is the name of a variable that exists in the program.

> Assign all simple variables before calling `VARPTR$` for an array element, because the array addresses change when a new simple variable is assigned.

`VARPTR$` returns a three-byte string of the following form:

`| Byte 0 | Byte 1 | Byte 2 |`

Byte 0 contains one of the following variable types:

* 2 integer
* 3 string
* 4 single-precision
* 8 double precision

Byte 1 contains the 8086 address format, and is the least significant byte.

Byte 2 contains the 8086 address format, and is the most significant byte.

## Example

```vb
100 X = USR(VARPTR$(Y))
```
