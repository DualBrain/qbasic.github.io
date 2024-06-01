# LET

To assign the value of an expression to a variable.

## Syntax

`[LET] variable=expression`

## Comments

The word `LET` is optional; that is, the equal sign is sufficient when assigning an expression to a variable name.

The `LET` statement is seldom used. It is included here to ensure compatibility with previous versions of BASIC that require it.

When using `LET`, remember that the type of the variable and the type of the expression must match. If they don't, a `Type mismatch` error occurs.

## Example

Both of the following examples are functionally equal.

```vb
110 LET D = 12
120 LET E = 12 ^ 2
130 LET F = 12 ^ 4
140 LET SUM = D + E + F
```

```vb
110 D = 12
120 E = 12 ^ 2
130 F = 12 ^ 4
140 SUM = D + E + F
```
