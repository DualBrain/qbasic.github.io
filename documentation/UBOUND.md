# UBOUND

Returns the highest array subscript for the specified array dimension.

## Syntax

`v=UBOUND(array[,n])`

## Comments

*array* is the variable name of the array.

*n* is an integer value specifying the dimension in a multidimensional array. The default value is 1.

## Example

```vb
05 DIM a(1 TO 10, 1 TO 20, 1 TO 30)
10 PRINT UBOUND(a), UBOUND(a, 2), UBOUND(a, 3)
```

```text
10 20 30
```
