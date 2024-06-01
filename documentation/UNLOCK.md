# UNLOCK

To release locks that have been applied to an opened file. This is used in a multi-device environment, often referred to as a network or network environment.

## Syntax

`UNLOCK [#]n [,[record number] [TO record number]]`

## Comments

*n* is the number that was assigned the file as it was originally numbered in the program.

*record number* is the number of the individual record that is to be unlocked. Or, if a range of records are to be unlocked, record number designates the beginning and ending record of the specified range.

The range of legal record numbers is 1 to 232-1. The limit on record size is 32767 bytes.

The record range specified must be from lower to (the same or) higher record numbers.

If a starting *record number* is not specified, the record number 1 is assumed.

If an ending *record number* is not specified, then only the specified record is unlocked.

The following are legal `UNLOCK` statements:

```vb
UNLOCK #n         ' unlocks the entire file n
UNLOCK #n, X      ' unlocks record X only
UNLOCK #n, TO Y   ' unlocks records 1 through Y
UNLOCK #n, X TO Y ' unlocks records X through Y
```

The locked file or record range should be unlocked before the file is closed.

Failure to execute the `UNLOCK` statement can jeopardize future access to that file in a network environment.

In the case of files opened in random mode, if a range of record numbers is specified, this range must match exactly the record number range given in the [LOCK](LOCK) statement.

The `Permission denied` message will appear if a syntactically correct `UNLOCK` request cannot be granted. The `UNLOCK` statement must match exactly the paired [LOCK](LOCK) statement.

It is expected that the time in which files or regions within files are locked will be short, and thus the suggested usage of the [LOCK](LOCK) statement is within shortterm paired [LOCK](LOCK)/`UNLOCK` statements.

## Examples

The following demonstrates how the [LOCK](LOCK)/`UNLOCK` statements should be used:

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
