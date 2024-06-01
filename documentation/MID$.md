# MID$

To return a string of m characters from *x$* beginning with the *nth* character.

## Syntax

`MID$(x$,n[,m])`

## Comments

*n* must be within the range of `1` to `255`.

*m* must be within the range of `0` to `255`.

If *m* is omitted, or if there are fewer than *m* characters to the right of *n*, all rightmost characters beginning with *n* are returned.

If *n* > [LEN](LEN)`(x$)`, `MID$` function returns a null string.

If *m* equals `0`, the `MID$` function returns a null string.

If either *n* or *m* is out of range, an `Illegal function call error` is returned.

For more information and examples, see the [LEFT$](LEFT$) and [RIGHT$](RIGHT$) functions.

## Example

```vb
10 A$ = "GOOD"
20 B$ = "MORNING EVENING AFTERNOON"
30 PRINT A$; MID$(B$, 8, 8)
```

```text
 GOOD EVENING
```

The last line concatenates (joins) the *A$* string to another string with a length of eight characters, beginning at position `8` within the *B$* string.
