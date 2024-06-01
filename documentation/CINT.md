# CINT

To round numbers with fractional portions to the next whole number or integer.

## Syntax

`CINT(x)`

## Comments

If `x` is not within the  range of `-32768` to `32767`, an `Overflow` error occurs. See the [FIX](FIX) and [INT](INT) functions, both of which return integers.

## Examples

```vb
PRINT CINT(45.67)
```

```text
 46
```

45.67 is rounded up to 46.

## Note

 See the [CDBL](CDBL) and [CSNG](CSNG) functions for converting numbers to the double-precision and single-precision data types, respectively.

## See Also

* [PRINT](PRINT), [FIX](FIX), [INT](INT), [CDBL](CDBL), [CSNG](CSNG)
