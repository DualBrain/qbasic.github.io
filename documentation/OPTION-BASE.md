# OPTION BASE

To declare the minimum value for array subscripts.

## Syntax

`OPTION BASE n`

## Comments

*n* is `1` or `0`. The default base is `0`.

If the statement `OPTION BASE 1` is executed, the lowest value an array subscript can have is `1`.

An array subscript may never have a negative value.

`OPTION BASE` gives an error only if you change the base value. This allows chained programs to have `OPTION BASE` statements as long as the value is not changed from the initial setting.

> You must code the `OPTION BASE` statement before you can define or use any arrays. If an attempt is made to change the option base value after any arrays are in use, an error results.
