# LINE INPUT

To input an entire line (up to 255 characters) from the keyboard into a string variable, ignoring delimiters.

## Syntax

`LINE INPUT [;][prompt string;]string variable`

## Comments

*prompt string* is a string literal, displayed on the screen, that allows user input during program execution.

A question mark is not printed unless it is part of prompt string.

*string variable* accepts all input from the end of the prompt to the carriage return. Trailing blanks are ignored.

`LINE INPUT` is almost the same as the [INPUT](INPUT) statement, except that it accepts special characters (such as commas) in operator input during program execution.

If a line-feed/carriage return sequence (this order only) is encountered, both characters are input and echoed. Data input continues.

If `LINE INPUT` is immediately followed by a semicolon, pressing the RETURN key will not move the cursor to the next line.

A `LINE INPUT` may be escaped by typing CTRL-BREAK. BASIC returns to command level and displays Ok.

Typing [CONT](CONT) resumes execution at the `LINE INPUT` line.

## Example

```vb
100 LINE INPUT A$
```

Program execution pauses at line 100, and all keyboard characters typed thereafter are input to string A$ until RETURN, CTRL-M, CTRL-C, or CTRL-BREAK is entered.
