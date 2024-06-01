# LEFT$

To return a string that comprises the left-most *n* characters of *x$*.

## Syntax

`LEFT$(x$,n)`

## Comments

*n* must be within the range of 0 to 255. If *n* is greater than [LEN](LEN)`(x$)`, the entire string (*x$*) will be returned. If *n* equals zero, the null string (length zero) is returned (see the [MID$](MID$) and [RIGHT$](RIGHT$) substring functions).

## Example

```vb
10 A$ = "BASIC"
20 B$ = LEFT$(A$, 3)
30 PRINT B$
```

```text
 BAS
```

The left-most three letters (*BAS*) of the string "BASIC" are printed on the screen.
