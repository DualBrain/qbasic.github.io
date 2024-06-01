# INKEY$

To return one character read from the keyboard.

## Syntax

`v$=INKEY$`

## Comments

If no character is pending in the keyboard buffer, a null string (length zero) is returned.

If several characters are pending, only the first is returned. The string will be one or two characters in length.

Two character strings are used to return the extended codes described in Appendix C of the BASIC User's Guide. The first character of a two character code is zero.

No characters are displayed on the screen, and all characters except the following are passed to the program:

CTRL-BREAK
CTRL-NUM LOCK
CTRL-ALT-DEL
CTRL-PRTSCR
PRTSCR

## Example

```vb
10 CLS: PRINT "PRESS RETURN
20 TIMELIMIT% = 1000
30 GOSUB 1010
40 IF TIMEOUT% THEN PRINT "TOO LONG" ELSE PRINT "GOOD SHOW"
50 PRINT RESPONSE$
60 END
.
.
.
1000 REM TIMED INPUT SUBROUTINE
1010 RESPONSE$=""
1020 FOR N%=1 TO TIMELIMIT%
1030 A$=INKEY$:IF LEN(A$)=0 THEN 1060
1040 IF ASC(A$)=13 THEN TIMEOUT%=0: RETURN
1050 RESPONSE$=RESPONSE$+A$
1060 NEXT N%
1070 TIMEOUT%=1: RETURN
```

When this program is executed, and if the RETURN key is pressed before 1000 loops are completed, then "GOOD SHOW" is printed on the screen. Otherwise, "TOO LONG" is printed.

Since an `INKEY$` statement scans the keyboard only once, place `INKEY$` statements within loops to provide adequate response times for the operator.
