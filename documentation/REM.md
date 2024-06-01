# REM

To allow explanatory remarks to be inserted in a program.

## Syntax

`REM[comment]`

`'[comment]`

## Comments

`REM` statements are not executed, but are output exactly as entered when the program is listed.

Once a `REM` or its abbreviation, an apostrophe (`'`), is encountered, the program ignores everything else until the next line number or program end is encountered.

`REM` statements may be branched into from a [GOTO](GOTO) or [GOSUB](GOSUB) statement, and execution continues with the first executable statement after the `REM` statement. However, the program runs faster if the branch is made to the first statement.

Remarks may be added to the end of a line by preceding the remark with an apostrophe (`'`) instead of `REM`.

> Do not use `REM` in a [DATA](DATA) statement because it will be considered to be legal data.

## Examples

```vb
REM CALCULATE AVERAGE VELOCITY
FOR I = 1 TO 20
SUM = SUM + V(I)
NEXT I
```

```vb
FOR I = 1 TO 20 ' CALCULATED AVERAGE VELOCITY
  SUM = SUM + V(I)
NEXT I
```
