# DEF DBL / INT / SNG / STR

To declare variable types as integer, single-precision, double-precision, or string.

## Syntax

`DEFtype letters`

## Comments

*type* is `INT` (integer), `SNG` (single-precision number), `DBL` (double-precision number), or `STR` (string of 0-255 characters).

*letters* are letters (separated by commas) or range of letters of the alphabet.

A `DEFtype` statement declares that variable names beginning with the letter(s) specify that type of variable. However, a type declaration character (`%`,`&`,`!`,`#`,`$`) always takes precedence over a `DEFtype` statement in the typing of a variable.

If no type declaration statements are encountered, BASIC assumes all variables are single-precision. Single-precision is the default value.

```vb
10 DEFDBL L-P
```

All variables beginning with the letters `L`, `M`, `N`, `O`, and `P` will be double-precision variables.

```vb
10 DEFSTR A
20 A="120#"
```

All variables beginning with the letter `A` will be string variables. The `$` declaration is unnecessary in this example.

```vb
10 DEFINT I-N, W-Z
20 W$="120#"
```

All variables beginning with the letters `I`, `J`, `K`, `L`, `M`, `N`, `W`, `X`, `Y`, `Z` will be integer variables. `W$` in line 20 establishes a string variable beginning with the letter `W`. However, the variable `W` will remain an integer elsewhere in the program.
