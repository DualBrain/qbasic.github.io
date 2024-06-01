# FIELD

To allocate space for variables in a random file buffer.

## Syntax

`FIELD [#] filenum, width AS stringvar [,width AS stringvar]...`

## Comments

*filenum* is the number under which the file was opened.

*width* is the number of characters to be allocated to the string variable.

*string* variable is a string variable which will be used for random file access.

A `FIELD` statement must have been executed before you can:

- get data out of a random buffer after a [GET](GET) statement
- enter data before a [PUT](GET) statement

For example, the following line allocates the first 20 positions (bytes) in the random file buffer to the string variable *N$*, the next 10 positions to *ID$*, and the next 40 positions to *ADD$*:

```vb
FIELD 1, 20 AS N$, 10 AS ID$, 40 AS ADD$ 
```

`FIELD` only allocates space; it does not place any data in the random file buffer.

The total number of bytes allocated in a `FIELD` statement must not exceed the record length specified when the file was opened. Otherwise, a `Field overflow` error occurs (the default record length is 128).

Any number of `FIELD` statements may be executed for the same file, and all `FIELD` statements executed are in effect at the same time.

## Note

Do not use a fielded variable name in an [INPUT](INPUT) or [LET](LET) statement. Once a variable name is fielded, it points to the correct place in the random file buffer. If a subsequent [INPUT](INPUT) or [LET](LET) statement with that variable name is executed, the variable's pointer is moved to string space (see [LSET](LSET)/[RSET](RSET) and [GET](GET) statements).
