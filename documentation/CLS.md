# CLS

To clear the screen.  

## Syntax

`CLS [n]`

## Comments

`n` is one of the following values:

| Value Of *n* | Effect |
| ------------ | ------ |
| `0` | Clears the screen of all text and graphics |
| `1` | Clears only the graphics viewport |
| `2` | Clears only the text window |

If the graphics viewport is active, `CLS` without argument clears only the viewport. If the graphics viewport is inactive, `CLS` clears the text window.

If the screen is in alpha mode, the active page is cleared to the currently selected background color (see the [SCREEN](SCREEN) and [COLOR](COLOR) statements).

If the screen is in graphics mode, the entire screen buffer is cleared to background color.

The screen may also be cleared by pressing `CTRL-HOME`, or by changing the screen mode with the [SCREEN](SCREEN) or [WIDTH](WIDTH) statements.

`CLS` returns the cursor to the upper-left corner of the screen, and sets the last point referenced to the center of the screen.

If the [VIEW](VIEW) statement has been used, `CLS` clears only the last viewport specified.

## Example

```vb
CLS
```

This clears the screen.

## See Also

* [SCREEN](SCREEN), [COLOR](COLOR), [WIDTH](WIDTH), [VIEW](VIEW)
