# CHR$

To convert an ASCII code to its equivalent character.

## Syntax

`CHR$(n)`

## Comments

`n` is a value from 0 to 255. `CHR$` is commonly used to send a special character to the terminal or printer. For example, you could send `CHR$(7)` to sound a beep through the speaker as a preface to an error message, or you could send a form feed, `CHR$(12)`, to the printer. See the [ASC](ASC) function for ASCII-to-numeric conversion.

## Examples

```vb
PRINT CHR$(66);
```

```text
 B
```

This prints the ASCII character code `66`, which is the uppercase letter `B`.

```vb
PRINT CHR$(13);
```

This command prints a carriage return.

## See Also

* [PRINT](PRINT), [ASC](ASC)
