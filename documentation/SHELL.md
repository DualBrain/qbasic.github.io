# SHELL

To load and execute another program or batch file. When the program finishes, control returns to the BASIC program at the statement following the `SHELL` statement. A program executed under control of BASIC is referred to as a child process.

## Syntax

`SHELL [string]`

## Comments

*string* is a valid string expression containing the name of a program to run and (optionally) command arguments.

The program name in string may have any extension that MS-DOS COMMAND.COM supports. If no extension is supplied, COMMAND will look for a .COM file, then an .EXE file, and finally, a .BAT file. If none is found, `SHELL` will issue a "File not found" error.

Any text separated from the program name by at least one blank space will be processed by COMMAND as program parameters.

BASIC remains in memory while the child process is running. When the child process finishes, BASIC continues at the statement following the `SHELL` statement.

`SHELL` with no string will go to MS-DOS. You may now do anything that COMMAND allows. When ready to return to BASIC, type the MS-DOS command `EXIT`.

## Examples

```text
SHELL
A>DIR
A>EXIT
```

Write some data to be sorted, use `SHELL SORT` to sort it, then read the sorted data to write a report.

```vb
10 OPEN "SORTIN.DAT" FOR OUTPUT AS #1
20 'write data to be sorted
.
.
.
1000 CLOSE 1
1010 SHELL "SORT <SORTIN.DAT >SORTOUT.DAT"
1020 OPEN "SORTOUT.DAT" FOR INPUT AS #1
1030 'Process the sorted data
```
