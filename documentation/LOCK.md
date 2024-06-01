# LOCK

To restrict the access to all or part of a file that has been opened by another process. This is used in a multi-device environment, often referred to as a network or network environment.

## Syntax

`LOCK [#]n [,[record number] [TO record number]]`

## Color

*n* is the number that was assigned to the file as it was originally numbered in the program.

*record number* is the number of the individual record that is to be locked. Or, if a range of records are to be locked, record number designates the beginning and ending record of the specified range.

The range of legal record numbers is 1 to 232-1. The limit on record size is 32767 bytes.

The record range specified must be from lower to (the same or) higher record numbers.

If a starting *record number* is not specified, the *record number 1* is assumed.

If an ending *record number* is not specified, then only the specified record is locked.

The following are examples of legal `LOCK` statements:

```vb
LOCK #n         ' locks the entire file n
LOCK #n, X      ' locks record X only
LOCK #n TO Y    ' locks records 1 through Y
LOCK #n, X TO Y ' locks records X through Y
```

With a random-access file, the entire opened file, or a range of records within an opened file, may be locked, thus denying access to those records to any other process which has also opened the file.

With a sequential access file that has been opened for input or output, the entire file is locked, regardless of any record range specified. This is not considered an error. The specification of a range in the `LOCK` statement regarding the sequential file will simply be disregarded.

The `LOCK` statement should be executed on a file or record range within a file before attempting to read or write to that file.

The locked file or record range should be unlocked before the file is closed. Failure to execute the [UNLOCK](UNLOCK) statement can jeopardize future access to that file in a network environment.

It is expected that the time in which files or regions within files are locked will be short, and thus the suggested usage of the `LOCK` statement is within short-term paired `LOCK`/[UNLOCK](UNLOCK) statements.

## Examples

The following sequence demonstrates how the `LOCK`/[UNLOCK](UNLOCK) statements should be used:

```vb
LOCK #1, 1 TO 4
LOCK #1, 5 TO 8
UNLOCK #1, 1 TO 4
UNLOCK #1, 5 TO 8
```

The following example is illegal:

```vb
LOCK #1, 1 TO 4
LOCK #1, 5 TO 8
UNLOCK #1, 1 TO 8
```
