# RIGHT$

To return the rightmost *n* characters of string *x$*.

## Syntax

`RIGHT$(x$,n)`

## Comments

If *n* is equal to or greater than [LEN](LEN)`(x$)`, `RIGHT$` returns *x$*. If *n* equals zero, the null string (length zero) is returned (see the `MID$` and [LEFT$](LEFT$) functions).

## Example

```vb
10 A$ = "DISK BASIC"
10 PRINT RIGHT$(A$, 5)
```

```text
 BASIC
```

Prints the rightmost five characters in the A$ string.
