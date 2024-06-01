# PCOPY

To copy one screen page to another in all screen modes.

## Syntax

`PCOPY sourcepage, destinationpage`

## Comments

The *sourcepage* is an integer expression in the range 0 to *n*, where *n* is determined by the current video-memory size and the size per page for the current screen mode.

The *destinationpage* has the same requirements as the *sourcepage*.

For more information, see [CLEAR](CLEAR) and [SCREEN](SCREEN).

## Example

This copies the contents of page 1 to page 2:

```vb
PCOPY 1,2
```
