# RESET

To close all disk files and write the directory information to a diskette before it is removed from a disk drive.

## Syntax

`RESET`

## Comments

Always execute a `RESET` command before removing a diskette from a disk drive. Otherwise, when the diskette is used again, it will not have the current directory information written on the directory track.

`RESET` closes all open files on all drives and writes the directory track to every diskette with open files.