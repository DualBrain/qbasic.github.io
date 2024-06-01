# BEEP

To sound the speaker at 800 Hz (800 cycles per second) for one-quarter of a second.

## Syntax

`BEEP`

## Comments

BEEP, CTRL-G, and `PRINT CHR$(7)` have the same effect.

## Examples

```vb
2340 IF X>20 THEN BEEP
```

If X is out of range, the computer beeps.

## See Also

* [PRINT](PRINT), [CHR$](CHR$)
