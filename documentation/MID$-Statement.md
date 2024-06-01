# MID$ (Statement)

To replace a portion of one string with another string.

## Syntax

`MID$(stringexp1,n[,m])=stringexp2`

## Comments

Both *n* and *m* are integer expressions.

*stringexp1* and *stringexp2* are string expressions.

The characters in *stringexp1*, beginning at position *n*, are replaced by the characters in *stringexp2*.

The optional *m* refers to the number of characters from *stringexp2* that are used in the replacement. If *m* is omitted, all of *stringexp2* is used.

Whether *m* is omitted or included, the replacement of characters never goes beyond the original length of *stringexp1*.

## Example

```vb
10 A$="KANSAS CITY, MO"
20 MID$(A$, 14)="KS"
30 PRINT A$
```

```text
 KANSAS CITY, KS
```

Line 20 overwrites "MO" in the *A$* string with "KS".
