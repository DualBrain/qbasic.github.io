# KILL

To delete a file from a disk.

## Syntax

`KILL filename`

## Comments

*filename* can be a program file, sequential file, or random-access data file.

`KILL` is used for all types of disk files, including program, random data, and sequential data files.

## Note

You must specify the filename's extension when using the `KILL` command. Remember that files saved in BASIC are given the default extension *.BAS*.

If a `KILL` command is given for a file that is currently open, a `File already open` error occurs.

## Examples

The following command deletes the BASIC file *DATA1*, and makes the space available for reallocation to another file:

```vb
200 KILL "DATA1.BAS"
```

The following command deletes the BASIC file *RAINING* from the subdirectory dogs:

```vb
KILL "CATS\DOGS\RAINING.BAS"
```
