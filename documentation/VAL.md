# VAL

Returns the numerical value of string *x$*.

## Syntax

`VAL(x$)`

## Comments

The `VAL` function also strips leading blanks, tabs, and line feeds from the argument string. For example, the following line returns `-3`:

`VAL(" -3")`

The [STR$](STR$) function (for numeric to string conversion) is the complement to the `VAL(x$)` function.

If the first character of *x$* is not numeric, the `VAL(x$)` will return zero.

## Example

```vb
10 READ NAME$, CITY$, STATE$, ZIP$
20 IF VAL(ZIP$)<90000 OR VAL(ZIP$)>96699 THEN PRINT NAME$ TAB(25) "OUT OF STATE"
30 IF VAL(ZIP$)>=90801 AND VAL(ZIP$)<=90815 THEN PRINT NAME$ TAB(25) "LONG BEACH"
```
