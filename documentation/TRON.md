# TRON

To trace the execution of program statements.

## Syntax

`TRON`
`TROFF`

## Comments

As an aid in debugging, the `TRON` (trace on) command enables a trace flag that prints each line number of the program as it is executed. The numbers appear enclosed in square brackets.

`TRON` may be executed in either the direct or indirect mode.

The trace flag is disabled with the `TROFF` (trace off) command.

## Example

```vb
05 TRON
10 K=10
20 FOR J = 1 TO 2
30   L = K + 10
40   PRINT J; K; L
50   K = K + 10
60 NEXT
75 TROFF
70 END
```

```text
[10][20][30][40] 1 10 20
[50][60][30][40] 2 20 30
[50][60][70]
```
