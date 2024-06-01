# DIM

To specify the maximum values for array variable subscripts and allocate storage accordingly.

## Syntax

`DIM variable(subscripts)[,variable(subscripts)]...`

## Comments

If an array variable name is used without a `DIM` statement, the maximum value of its subscript(s) is assumed to be `10`. If a subscript greater than the maximum specified is used, a `Subscript out of range` error occurs.

The maximum number of dimensions for an array is `255`.

The minimum value for a subscript is always `0`, unless otherwise specified with the [OPTION BASE](OPTION-BASE) statement.

An array, once dimensioned, cannot be re-dimensioned within the program without first executing a [CLEAR](CLEAR) or [ERASE](ERASE) statement.

The `DIM` statement sets all the elements of the specified arrays to an initial value of zero.

## Example

```vb
10 DIM A(20)
20 FOR I=0 TO 20
30   READ A(I)
40 NEXT I
```

This example reads 21 `DATA` statements elsewhere in the program and assigns their values to `A(0)` through `A(20)`, sequentially and inclusively. If the `A` array is single precision (default accuracy) then the first line will allocate 84 bytes of memory to this array (4 bytes times 21 elements).

## See Also

* [OPTION BASE](OPTION-BASE), [CLEAR](CLEAR), [ERASE](ERASE), [FOR...NEXT](FOR...NEXT)
