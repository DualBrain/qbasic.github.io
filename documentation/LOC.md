# LOC

To return the current position in the file.

## Syntax

`LOC(file number)`

## Comments

*file number* is the file number used when the file was opened.

When transmitting or receiving a file through a communication port, `LOC` returns the number of characters in the input buffer waiting to be read. The default size for the input buffer is 256 characters, but can be changed with the /c: option on the BASIC command line. If there are more than 255 characters in the buffer, `LOC` returns 255. Since a string is limited to 255 characters, this practical limit alleviates the need to test for string size before reading data into it. If fewer than 255 characters remain in the buffer, then `LOC` returns the actual count.

With random disk files, `LOC` returns the record number just read from, or written to, with a [GET](GET) or [PUT](PUT) statement.

With sequential files, `LOC` returns the number of 128-byte blocks read from, or written to, the file since it was opened. When the sequential file is opened for input, BASIC initially reads the first sector of the file. In this case, the `LOC` function returns the character 1 before any input is allowed.

If the file was opened but no disk input/output was performed, `LOC` returns a zero.

## Example

```vb
IF LOC(1) > 50 THEN STOP
```

The program stops after `51` records are read or written.
