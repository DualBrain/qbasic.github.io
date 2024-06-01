# LBOUND

Returns the lowest array subscript for the specified array dimension.

## Syntax

`v=LBOUND(array[,n])`

## Comments

*array* is the variable name of the array.

*n* is an integer value specifying the dimension in a multidimensional array. The default value is 1.

## Example

```vb
05 DIM a(1 TO 10, 11 TO 20, 21 TO 30)
10 PRINT LBOUND(a), LBOUND(a, 2), LBOUND(a, 3)
```

```text
1 11 21
```
