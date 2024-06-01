# KEY

To allow rapid entry of as many as 15 characters into a program with one keystroke by redefining BASIC special function keys.

## Syntax

`KEY key number,string expression`

`KEY n,CHR$(hex code)+CHR$(scan code)`

`KEY ON`

`KEY OFF`

`KEY LIST`

## Comments

*key number* is the number of the key to be redefined. *key number* may range from 1-20.

*string expression* is the key assignment. Any valid string of 1 to 15 characters may be used. If a string is longer than 15 characters, only the first 15 will be assigned. Constants must be enclosed in double quotation marks.

*scan code* is the variable defining the key you want to trap. Appendix H in the BASIC User's Guide lists the scan codes for the keyboard keys.

*hex code* is the hexadecimal code assigned to the key shown below:

| Key | Hex code |
| --- | -------- |
| EXTENDED | &H80 |
| CAPS LOCK | &H40 |
| NUM LOCK | &H20 |
| ALT | &H08 |
| CTRL | &H04 |
| SHIFT | &H01, &H02, &H03 |

Hex codes may be added together, such as &H03, which is both shift keys.

Initially, the function keys are assigned the following special functions:

| Key | Label | Key | Label |
| --- | ----- | --- | ----- |
| F1 | LIST | F2 | RUN¿ |
| F3 | LOAD" | F4 | SAVE" |
| F5 | CONT¿ | F6 | ,"LPT1:" ¿ |
| F7 | TRON¿ | F8 | TROFF¿ |
| F9 | KEY | F10 | SCREEN 000¿ |

## Note

¿ (arrow) means that you do not have to press RETURN after each of these keys has been pressed.

Any one or all of the 10 keys may be redefined. When the key is pressed, the data assigned to it will be input to the program.

`KEY key number, "string expression"`

Assigns the string expression to the specified key.

`KEY LIST`

List all 10 key values on the screen. All 15 characters of each value are displayed.

`KEY ON`

Displays the first six characters of the key values on the 25th line of the screen. When the display width is set at 40, five of the 10 keys are displayed. When the width is set at 80, all 10 are displayed.

`KEY OFF`

Erases the key display from the 25th line, making that line available for program use. `KEY OFF` does not disable the function keys.

If the value for key number is not within the range of 1 to 10, or 15 to 20, an "Illegal function call" error occurs. The previous `KEY` assignment is retained.

Assigning a null string (length 0) disables the key as a function key.

When a function key is redefined, the [INKEY$](INKEY$) function returns one character of the assigned string per invocation. If the function key is disabled, [INKEY$](INKEY$) returns a string of two characters: the first is binary zero; the second is the key scan code.

## Examples

```vb
10 KEY 1, "MENU"+CHR$(13)
```

Displays a menu selected by the operator each time key 1 is pressed.

```vb
1 KEY OFF 
```

Turns off the key display.

```vb
10 DATA KEY1, KEY2, KEY3, KEY4, KEY5
20 FOR N=1 TO 5: READ SOFTKEYS$(n)
30 KEY N, SOFTKEYS$(I)
40 NEXT N
50 KEY ON
```

Displays new function keys on line 25 of the screen.

```vb
20 KEY 1, ""
```

Disables function key 1.
