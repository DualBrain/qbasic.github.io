# CDBL

To convert `x` to a double-precision number.

## Syntax

``CDBL(x)``

## Comments

`x` must be a numeric expression.

## Example

```vb
A=454.67
PRINT A; CDBL(A)
```

```text
 454.67 454.6700134277344
```

Prints a double-precision version of the single-precision value stored in the variable named `A`.

The last 11 numbers in the double-precision number have no meaning in this example, since A was previously defined to only two-decimal place accuracy.

## Note

See the [CINT](CINT) and [CSNG](CSNG) functions for converting numbers to integer and single precision, respectively.

## See Also

* [PRINT](PRINT), [CINT](CINT), [CSNG](CSNG)
