# INPUT$

To return a string of *x* characters read from the keyboard, or from *file number*.

## Syntax

`INPUT$(x[,[#]file number)]`

## Comments

If the keyboard is used for input, no characters will appear on the screen. All control characters (except CTRL-BREAK) are passed through. CTRL-BREAK interrupts the execution of the `INPUT$` function.

The `INPUT$` function is preferred over [INPUT](INPUT) and [LINE INPUT](LINE-INPUT) statements for reading communications files, because all ASCII characters may be significant in communications. [INPUT](INPUT) is the least desirable because input stops when a comma or carriage return is seen. [LINE INPUT](LINE-INPUT) terminates when a carriage return is seen.

`INPUT$` allows all characters read to be assigned to a string. `INPUT$` will return *x* characters from the file number or keyboard.

For more information about communications, refer to Appendix F in the BASIC User's Guide.

## Examples

The following example lists the contents of a sequential file in hexadecimal.

```vb
10 OPEN"I", 1, "DATA"
20 IF EOF(1) THEN 50
30 PRINT HEX$(ASC(INPUT$(1, #1)));
40 GOTO 20
50 PRINT
60 END
```

In the following program, the program pauses, awaiting a keyboard entry of either P or S. Line 130 continues to loop back to line 100 if the input is other than P or S.

```vb
100 PRINT "TYPE P TO PROCEED OR S TO STOP"
110 X$=INPUT$(1)
120 IF X$="P" THEN 500
130 IF X$="S" THEN 700 ELSE 100
```
