# LSET

To move data from memory to a random-file buffer and left- or right-justify it in preparation for a [PUT] statement.

## Syntax

`LSET string variable=string expression`

`RSET string variable=string expression`

## Comments

If `string expression` requires fewer bytes than were fielded to string variable, `LSET` left-justifies the string in the field, and `RSET` right-justifies the string (spaces are used to pad the extra positions).

If the string is too long for the field, characters are dropped from the right.

To convert numeric values to strings before the `LSET` or `RSET` statement is used, see the [MKI$](MKI$), [MKS$](MKS$), and [MKD$](MKD$) functions.

`LSET` or `RSET` may also be used with a nonfielded string variable to left-justify or right-justify a string in a given field.

## Example

```vb
110 A$ = SPACE$(20)
120 RSET A$ = N$
```

These two statements right-justify the string *N$* in a 20-character field. This can be valuable for formatting printed output.
