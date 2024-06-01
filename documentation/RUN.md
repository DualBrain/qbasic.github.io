# RUN

To execute the program currently in memory, or to load a file from the diskette into memory and run it.

## Syntax

`RUN [line number][,r]`

`RUN filename[,r]`

## Comments

`RUN` or `RUN line number` runs the program currently in memory.

If *line number* is specified, execution begins on that line. Otherwise, execution begins at the lower line number.

If there is no program in memory when `RUN` is executed, BASIC returns to command level.

`RUN filename` closes all open files and deletes the current memory contents before loading the specified file from disk into memory and executing it.

The `r` option keeps all data files open.

If you are using the speaker on the computer, please note that executing the `RUN` command will turn off any sound that is currently running and will reset to Music Foreground. Also, the [PEN](PEN) and [STRIG](STRIG) Statements are reset to `OFF`.

## Examples

```vb
RUN "NEWFIL", R
```

Runs *NEWFIL.BAS* without closing data files.
