# PMAP

To map expressions to logical or physical coordinates.

## Syntax

`x=PMAP (exp,function)`

## Comments

This function is valid for graphics modes only.

*x* is the physical coordinate of the point that is to be mapped.

*exp* is a numeric variable or expression.

| Function | Maps |
| -------- | ---- |
| 0 | logical expressions to physical x |
| 1 | logical expressions to physical y |
| 2 | physical expressions to logical x |
| 3 | physical expressions to logical y |

`PMAP` is used with [WINDOW](WINDOW) and [VIEW](VIEW) to translate coordinates.
