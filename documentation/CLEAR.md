# CLEAR

To set all numeric variables to zero, all string variables to null, and to close all open files. Options set the end of memory and reserve the amount of string and stack space available for use by BASIC.

## Syntax

`CLEAR[,[expression1][,expression2]]`

## Comments

*expression1* is a memory location that, if specified, sets the maximum number of bytes available for use by BASIC.

*expression2* sets aside stack space for BASIC. The default is the previous stack space size. When BASIC is first executed, the stack space is set to 512 bytes, or one-eighth of the available memory, whichever is smaller. BASIC allocates string space dynamically. An `Out of String Space` error occurs only if there is no free memory left for BASIC to use.

The `CLEAR` command:

- Closes all files
- Clears all [COMMON](COMMON) and user variables
- Resets the stack and string space
- Releases all disk buffers
- Turns off any sound
- Resets sound to music foreground
- Resets [PEN](PEN) to off
- Resets [STRIG](STRIG) to off
- Disables [ON ERROR GOTO](ON-ERROR-GOTO) trapping

## Examples

```vb
CLEAR
```

Zeroes variables and nulls all strings.

```vb
CLEAR 32768
```

Zeroes variables, nulls strings, protects memory above `32768`, does not change the stack space.

```vb
CLEAR ,,2000
```

Zeroes variables, nulls strings, allocates `2000` bytes for stack space, and uses all available memory in the segment.

```vb
CLEAR ,32768,2000
```

Zeroes variables, nulls strings, protects memory above `32768`, and allocates `2000` bytes for stack space.

## See Also

* [COMMON](COMMON), [PEN](PEN), [STRIG](STRIG), [ON ERROR GOTO](ON-ERROR-GOTO)
