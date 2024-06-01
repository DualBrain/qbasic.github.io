# ENVIRON$

To allow the user to retrieve the specified environment string from the environment table.

## Syntax

`v$=ENVIRON$(parmid)`

`v$=ENVIRON$(nthparm)`

## Comments

*parmid* is a valid string expression containing the parameter to search for.

*nthparm* is an integer expression in the range of `1` to `255`.

If a string argument is used, `ENVIRON$` returns a string containing the text following *parmid=* from the environment string table.

If *parmid* is not found, then a null string is returned.

If a numeric argument is used, `ENVIRON$` returns a string containing the *nth* parameter from the environment string table. If there is no *nth* parameter, then a null string is returned.

The `ENVIRON$` function distinguishes between upper- and lowercase.

## Examples

The following lines:

```vb
ENVIRON "PATH=A:\SALES; A:\ACOUNTING; B:\MKT:" 'Create entry
PRINT ENVIRON$("PATH")                          'Print entry
```

will print the following string:

`A:\SALES; A:\ACCOUNTING; B:\MKT`

The following line will print the first string in the environment:

```vb
PRINT ENVIRON$(1)
```

The following program saves the environment string table in an array so that it can be modified for a child process. After the child process completes, the environment is restored.

```vb
10 DIM ENVTBL$(10)
20 NPARMS= 1 
30 WHILE LEN(ENVIRON$(NPARMS))>0
40   ENVTBL$ (NPARMS) = ENVIRON$(NPARMS)
50   NPARMS = NPARMS + 1
60 WEND
70 NPARMS = NPARMS-1 
72 WHILE LEN(ENVIRON$(1))>0
73   A$=MID$(ENVIRON$(1), 1, INSTR (ENVIRON$(1), "="))
74   ENVIRON A$+";" 
75 WEND
90 ENVIRON "MYCHILDPARM1=SORT BY NAME"
100 ENVIRON "MYCHILDPARM2=LIST BY NAME"

1000 SHELL "MYCHILD"'RUNS "MYCHILD.EXE"
1002 WHILE LEN(ENVIRON$(1))>0
1003   A$=MID$(ENVIRON$(1), 1, INSTR(ENVIRON$ (1), "="))
1004   ENVIRON A$+";" 
1005 WEND
1010 FOR I=1 TO NPARMS
1020   ENVIRON ENVTBL$(I)
1030 NEXT I
```

The [DIM](DIM) statement in line 10 assumes no more than 10 parameters will be accessed.

In line 20, the initial number of parameters is established as 1.

In lines 30 through 70, a series of statements are used to adjust and correct  the parameter numbers.

Line 71 deletes the present environment.

Lines 72 through 80 create a new environment. Line 74 deletes the string.

Lines 80 through 100 store the new environment.

Lines 1000 through 1030 repeat the procedure by deleting the present environment and restore the parameters established in the first part of the program.

## See Also

* [PRINT](PRINT), [DIM](DIM), [WHILE...WEND](WHILE...WEND), [FOR...NEXT](FOR...NEXT), [LEN](LEN), [MID$](MID$), [INSTR](INSTR), [SHELL](SHELL), [ENVIRON](ENVIRON)
