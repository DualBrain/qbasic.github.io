# WHILE...WEND

To execute a series of statements in a loop as long as a given condition is true.

## Syntax

```text
WHILE expression
  .
  .
  [loop statements]
  .
  .
WEND 
```

## Comments

If *expression* is nonzero (true), *loop statements* are executed until the `WEND` statement is encountered. BASIC then returns to the `WHILE` statement and checks expression. If it is still true, the process is repeated.

If it is not true, execution resumes with the statement following the `WEND` statement.

`WHILE` and `WEND` loops may be nested to any level. Each `WEND` matches the most recent `WHILE`.

An unmatched `WHILE` statement causes a `WHILE without WEND` error. An unmatched `WEND` statement causes a `WEND without WHILE` error.

## Examples

```vb
90 'BUBBLE SORT ARRAY A$
100 FLIPS=1
110 WHILE FLIPS
115   FLIPS=0
120   FOR N=1 TO J-1
130     IF A$(N)>A$(N+1) THEN SWAP A$(N), A$(N+1): FLIPS=1
140   NEXT N
150 WEND
```

```vb
' BUBBLE SORT ARRAY A$
FLIPS = 1
WHILE FLIPS
  FLIPS = 0
  FOR N = 1 TO J-1
    IF A$(N) > A$(N + 1) THEN SWAP A$(N), A$(N + 1): FLIPS = 1
  NEXT N
WEND
```
