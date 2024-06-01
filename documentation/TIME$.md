# TIME$

To set or retrieve the current time.

## Syntax

As a statement:

`TIME$ = string exp`

As a variable:

`string exp=TIME$`

## Comments

*string exp* is a valid string literal or variable that lets you set hours (*hh*), hours and minutes (*hh:mm*), or hours, minutes, and seconds (*hh:mm:ss*).

*hh* sets the hour (0-23). Minutes and seconds default to 00.

*hh:mm* sets the hour and minutes (0-59). Seconds default to 00.

*hh:mm:ss* sets the hour, minutes, and seconds (0-59).

If *string exp* is not a valid string, a "Type mismatch" error results.

As you enter any of the above values, you may omit the leading zero, if any. You must, however, enter at least one digit. If you wanted to set the time as a half hour after midnight, you could enter `TIME$= "0:30"`, but not `TIME$= ":30"`.

If any of the values are out of range, an "Illegal function call" error is issued. The previous time is retained.

The current time is stored if `TIME$` is the target of a string assignment.

The current time is fetched and assigned to the string variable if TIME$ is the expression in a [LET](LET) or [PRINT](PRINT) statement.

If `string exp = TIME$`, `TIME$` returns an 8-character string in the form *hh:mm:ss*.

## Examples

The following example sets the time at 8:00 A.M.:

```vb
TIME$ = "08:00"
PRINT TIME$
```

```text
 08:00:05
```

The following program displays the current date and time on the 25th line of the screen and will sound on the minute and half minute.

```vb
10 KEY OFF: SCREEN 0: WIDTH 80: CLS
20 LOCATE 25, 5
30 PRINT DATE$, TIME$;
40 SEC=VAL(MID$(TIME$, 7, 2))
50 IF SEC=SSEC THEN 20 ELSE SSEC=SEC
60 IF SEC=0 THEN 1010
70 IF SEC=30 THEN 1020
80 IF SEC<57 THEN 20
1000 SOUND 1000, 2: GOTO 20
1010 SOUND 2000, 8: GOTO 20
1020 SOUND 400, 4: GOTO 20
```
