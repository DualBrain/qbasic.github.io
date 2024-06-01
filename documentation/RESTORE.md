# RESTORE

To allow [DATA](DATA) statements to be reread from a specified line.

## Syntax

`RESTORE[line number]`

## Comments

If *line number* is specified, the next [READ](READ) statement accesses the first item in the specified [DATA](DATA) statement.

If *line number* is omitted, the next [READ](READ) statement accesses the first item in the first [DATA](DATA) statement.

## Example

```vb
READ A, B, C
RESTORE
READ D, E, F
DATA 57, 68, 79
```

Assigns the value `57` to both `A` and `D` variables, `68` to `B` and `E`, and so on.
