# VIEW PRINT

To set the boundaries of the screen text window.

## Syntax

`VIEW PRINT [topline TO bottomline]`

## Comments

`VIEW PRINT` without topline and bottomline parameters initializes the whole screen area as the text window. The whole screen area consists of lines 1 to 24; by default, line 25 is not used.

Statements and functions that operate within the defined text window include [CLS](CLS), [LOCATE](LOCATE), [PRINT](PRINT), and [SCREEN](SCREEN).

The screen editor will limit functions such as scroll and cursor movement to the text window.

For more information, see [VIEW](VIEW).
