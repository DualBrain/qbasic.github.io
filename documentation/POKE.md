# POKE

To write (poke) a byte of data into a memory location.

## Syntax

`POKE a,b`

## Comments

*a* and *b* are integer expressions.

The integer expression a is the offset address of the memory location to be poked. The [DEF SEG](DEF-SEG) statement last executed determines the address. BASIC does not check any offsets that are specified.

The integer expression b is the data to be poked.

*b* must be within the range of 0 to 255. *a* must be within the range of 0 to 65535.

The complementary function to `POKE` is [PEEK](PEEK). The argument to [PEEK](PEEK) is an address from which a byte is to be read.

`POKE` and [PEEK](PEEK) are useful for efficient data storage, loading assembly language subroutines, and for passing arguments and results to and from assembly language subroutines.

## Examples

```vb
20 POKE &H5A00, &HFF
```

Places the decimal value 255 (&HFF) into the hex offset location (23040 decimal). See [PEEK](PEEK) function example.
