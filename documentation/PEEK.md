# PEEK

To read from a specified memory location.

## Syntax

`PEEK(a)`

## Comments

Returns the byte (decimal integer within the range of 0 to 255) read from the specified memory location a. a must be within the range of 0 to 65535.

The [DEF SEG](DEF-SEG) statement last executed determines the absolute address that will be peeked into.

`PEEK` is the complementary function to the [POKE](POKE) statement.

## Example

```vb
10 A=PEEK(&H5A00)
```

The value of the byte, stored in user-assigned hex offset memory location 5A00 (23040 decimal), will be stored in the variable A.
