# INT

To truncate an expression to a whole number.

## Syntax

`INT(x)`

## Comments

Negative numbers return the next lowest number. The [FIX](FIX) and [CINT](CINT) functions also return integer values.

## Example

```vb
PRINT INT(98. 89)
```

```text
 98
```

```vb
PRINT INT(-12. 11)
```

```text
 -13
```
