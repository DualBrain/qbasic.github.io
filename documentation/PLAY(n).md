# PLAY(n)

To return the number of notes currently in the background music queue.

## Syntax

`PLAY(n)`

## Comments

*n* is a dummy argument, and may be any value.

`PLAY(n)` returns 0 when in music foreground mode.

The maximum returned value of *x* is 32.

## Example

```vb
10 ' when 4 notes are left in
20 ' queue play another tune
30 PLAY "MBABCDABCDABCD"
40 IF PLAY (0) =4 then 200
.
.
.
200 PLAY "MBCDEFCDEF"
```
