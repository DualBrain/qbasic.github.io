# EOF

To return `-1` (true) when the end of a sequential or a communications file has been reached, or to return `0` if end of file (EOF) has not been found.

## Syntax

`v=EOF(file number)`

## Comments

If a [GET](GET) is done past the end of the file, `EOF` returns `-1`. This may be used to find the size of a file using a binary search or other algorithm. With communications files, a `-1` indicates that the buffer is empty.

Use `EOF` to test for end of file while inputting to avoid `Input Past End` errors.

## Example

```vb

Start:
  OPEN "I", 1, "DATA"
  C=0

ReadValue:
  IF EOF(1) THEN Done
  INPUT #1, M(C)
  C = C + 1 : GOTO ReadValue

Done:
  END

```

The file named `DATA` is read into the `M` array until the end of the file is reached, then the program branches to `Done`.

## See Also

* [GET](GET), [OPEN](OPEN), [INPUT#](INPUT#), [GOTO](GOTO), [END](END)
