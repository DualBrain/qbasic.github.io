# INPUT

To prepare the program for input from the terminal during program execution.

## Syntax

`INPUT[;][prompt string;] list of variables`

`INPUT[;][prompt string,] list of variables`

## Comments

*prompt* string is a request for data to be supplied during program execution.

*list of variables* contains the variable(s) that stores the data in the prompt string.

Each data item in the prompt string must be surrounded by double quotation marks, followed by a semicolon or comma and the name of the variable to which it will be assigned. If more than one *variable* is given, data items must be separated by commas.

The data entered is assigned to the variable list. The number of data items supplied must be the same as the number of variables in the list.

The variable names in the list may be numeric or string variable names (including subscripted variables). The type of each data item input must agree with the type specified by the variable name.

Too many or too few data items, or the wrong type of values (for example, numeric instead of string), causes the message "?Redo from start" to be printed. No assignment of input values is made until an acceptable response is given.

A comma may be used instead of a semicolon after prompt string to suppress the question mark. For example, the following line prints the prompt with no question mark:

`INPUT "ENTER BIRTHDATE",B$`

If the prompt string is preceded by a semicolon, the RETURN key pressed by the operator is suppressed. During program execution, data on that line is displayed, and data from the next [PRINT](PRINT) statement is added to the line.

When an `INPUT` statement is encountered during program execution, the program halts, the prompt string is displayed, and the operator types in the requested data. Strings that input to an `INPUT` statement need not be surrounded by quotation marks unless they contain commas or leading or trailing blanks.

When the operator presses the RETURN key, program execution continues.

`INPUT` and [LINE INPUT](LINE-INPUT) statements have built-in [PRINT](PRINT) statements. When an `INPUT` statement with a quoted string is encountered during program execution, the quoted string is printed automatically (see the [PRINT](PRINT) statement).

The principal difference between the `INPUT` and [LINE INPUT](LINE-INPUT) statements is that [LINE INPUT](LINE-INPUT) accepts special characters (such as commas) within a string, without requiring double quotation marks, while the `INPUT` statement requires double quotation marks.

##Examples

To find the square of a number:

```vb
10 INPUT X
20 PRINT X "SQUARED IS" X^2
30 END
```

```text
 ? 5
 5 SQUARED IS 25
```

To find the area of a circle when the radius is known:

```vb
10 PI=3.14
20 INPUT "WHAT IS THE RADIUS"; R
30 A=PI*R^2
40 PRINT "THE AREA OF THE CIRCLE IS"; A
50 PRINT
60 GOTO 20
```

```text
 WHAT IS THE RADIUS? 7.4
 THE AREA OF THE CIRCLE IS 171.9464
``` 

Note that line 20 in the above example makes use of the built-in [PRINT](PRINT) statement contained within `INPUT`.
