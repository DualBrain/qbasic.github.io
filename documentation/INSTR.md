# INSTR

To search for the first occurrence of string *y$* in *x$*, and return the position at which the string is found.

## Syntax

`INSTR([n,] x$, y$)`

## Comments

Optional offset *n* sets the position for starting the search. The default value for *n* is `1`. If *n* equals `0`, the error message `Illegal argument in line number` is returned. *n* must be within the range of `1` to `255`. If *n* is out of this range, an `Illegal Function Call` error is returned.

`INSTR` returns `0` if:

- `n > LEN(x$)`
- *x$* is null
- *y$* cannot be found

If *y$* is null, `INSTR` returns *n*.

*x$* and *y$* may be string variables, string expressions, or string literals.

```vb
10 X$ = "ABCDEBXYZ"
20 Y$ = "B"
30 PRINT INSTR(X$, Y$); INSTR(4, X$, Y$)
```

The interpreter searches the string `"ABCDFBXYZ"` and finds the first occurrence of the character `B` at position `2` in the string. It then starts another search at position `4` (`D`) and finds the second match at position `6` (`B`).
