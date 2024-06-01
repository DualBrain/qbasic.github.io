# COMMON

To pass variables to a chained program.

## Syntax

`COMMON variables`

## Comments

*variables* are one or more variables, separated by commas, that you want to pass to the chained program.

The `COMMON` statement is used in conjunction with the [CHAIN](chain) statement.

`COMMON` statements may appear anywhere in a program, although it is recommended that they appear at the beginning.

Any number of `COMMON` statements may appear in a program, but the same variable cannot appear in more than one `COMMON` statement. To pass all variables using the [CHAIN](chain) statement, use the all option, and omit the `COMMON` statement.

Place parentheses after the variable name to indicate array variables.

## Example

```vb
COMMON A, B, C, D(), G$
CHAIN "A:PROG3"
```

This example chains to program `PROG3.BAS` on disk drive A:, and passes the array `D` along with the variables `A`, `B`, `C`, and string `G$`.

## See Also

* [CHAIN](CHAIN)
