# MKI$, MKD$, MKS$

To convert numeric values to string values.

## Syntax

`MKI$(integer expression)`

`MKS$(single-precision expression)`

`MKD$(double-precision expression)`

## Comments

`MKI$` converts an integer to a 2-byte string.

`MKS$` converts a single-precision number to a 4-byte string.

`MKD$` converts a double-precision number to an 8-byte string.

Any numeric value placed in a random file buffer with a [LSET](LSET) or a [RSET](RSET) statement must be converted to a string (see [CVI](CVI), [CVS](CVS), [CVD](CVD) for the complementary functions).

These functions differ from [STR$](STR$) because they change the interpretations of the bytes, not the bytes themselves.

## Example

```vb
90 AMT=(K+T)
100 FIELD #1, 8 AS D$, 20 AS N$
110 LSET D$=MKS$(AMT)
120 LSET N$=A$
130 PUT #1
```
