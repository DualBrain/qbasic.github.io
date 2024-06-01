# ERASE

To eliminate arrays from a program.

## Syntax

`ERASE list of array variables`

## Comments

Arrays may be re-dimensioned after they are erased, or the memory space previously allocated to the array may be used for other purposes. If an attempt is made to re-dimension an array without first erasing it, an error occurs.

## Example

```vb
200 DIM B (250)
.
.
.
450 ERASE A, B
460 DIM B(3, 4)
```

Arrays `A` and `B` are eliminated from the program. The `B` array is re-dimensioned to a 3-column by 4-row array (12 elements), all of which are set to a zero value.

## See Also

* [DIM](DIM)
