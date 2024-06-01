# LEN

To return the number of characters in *x$*.

## Syntax

`LEN(x$)`

## Comments

Non-printing characters and blanks are counted.

## Example

*x$* is any string expression.

```vb
10 X$="PORTLAND, OREGON"
20 PRINT LEN(X$)
```

```text
 16
```

Note that the comma and space are included in the character count of 16.
