# LOF

To return the length (number of bytes) allocated to the file.

## Syntax

`LOF(file number)`

## Comments

*file number* is the number of the file that the file was opened under.

With communications files, `LOF` returns the amount of free space in the input buffers.

## Example

The following sequence gets the last record of the random-access file *file.big*, and assumes that the file was created with a default record length of 128 bytes:

```vb
10 OPEN "R", 1, "FILE.BIG"
20 GET #1, LOF(1) / 128
```
