# SPACE$

To return a string of *x* spaces.

## Syntax

``SPACE$(x)``

## Comments

*x* is rounded to an integer and must be within the range of 0 to 255 (see [SPC](SPC) function).

## Example

```vb
10 FOR N=1 TO 5
20 X$=SPACE$(N)
30 PRINT X$; N
40 NEXT N
```

```text
 1
  2
   3
    4
     5
```

Line 20 adds one space for each loop execution.
