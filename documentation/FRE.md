# FRE

To return the number of available bytes in allocated string memory.

## Syntax

`FRE(x$)`
`FRE(x)`

## Comments

Arguments (*x$*) and (*x*) are dummy arguments.

Before `FRE(x$)` returns the amount of space available in allocated string memory, BASIC initiates a "garbage collection" activity. Data in string memory space is collected and reorganized, and unused portions of fragmented strings are discarded to make room for new input.

If `FRE` is not used, BASIC initiates an automatic garbage collection activity when all string memory space is used up. BASIC will not initiate garbage collection until all free memory has been used. Garbage collection may take 1 to 1.5 minutes.

`FRE("")` or any string forces a garbage collection before returning the number of free bytes. Therefore, using `FRE("")` periodically will result in shorter delays for each garbage collection.

It should be noted that the CTRL-BREAK function cannot be used during this housecleaning process.

## Example

```vb
PRINT FRE(0)
```

```text
 14542
```

Your computer may return a different value.
