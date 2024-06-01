# DATA

To store the numeric and string constants that are accessed by the program [READ](READ) statement(s).

## Syntax

`DATA constants`

## Comments

*constants* are numeric constants in any format (fixed point, floating-point, or integer), separated by commas. No expressions are allowed in the list.

String constants in `DATA` statements must be surrounded by double quotation marks only if they contain commas, colons, or significant leading or trailing spaces. Otherwise, quotation marks are not needed.

`DATA` statements are not executable and may be placed anywhere in the program. A `DATA` statement can contain as many constants that will fit on a line (separated by commas), and any number of `DATA` statements may be used in a program.

[READ](READ) statements access the `DATA` statements in order. The data contained therein may be thought of as one continuous list of items, regardless of how many items are on a line or where the lines are placed in the program. The variable type (numeric or string) given in the [READ](READ) statement must agree with the corresponding constant in the `DATA` statement, or a `Type Mismatch` error occurs.

`DATA` statements may be reread from the beginning by use of the [RESTORE](RESTORE) statement.

For further information and examples, see the [RESTORE](RESTORE) statement and the [READ](READ) statement.

```vb
80  FOR I=1 TO 10
90    READ A(I)
100 NEXT I
110 DATA 3.08,5.19,3.12,3.98,4.24
120 DATA 5.08,5.55,4.00,3.16,3.37
```

This program segment reads the values from the `DATA` statements into array `A`. After execution, the value of `A(1)` is `3.08`, and so on. The `DATA` statements (last two lines) may be placed anywhere in the program; they may even be placed ahead of the [READ](READ) statement.

```vb
5 PRINT
10 PRINT "CITY","STATE","ZIP"
20 READ C$,S$,Z
30 DATA "NORTH RICHLAND HILLS,","TEXAS",76182
40 PRINT C$,S$,Z
```

```text
 CITY STATE ZIP
 NORTH RICHLAND HILLS, TEXAS 76182
```

This program reads string and numeric data from the `DATA` statement.

## See Also

* [READ](READ), [RESTORE](RESTORE), [FOR...NEXT](FOR...NEXT), [PRINT](PRINT)
