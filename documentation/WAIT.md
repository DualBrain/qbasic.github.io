# WAIT

To suspend program execution while monitoring the status of a machine input port.

## Syntax

`WAIT port number, n[,j]`

## Comments

*port number* represents a valid machine port number within the range of 0 to 65535.

*n* and *j* are integer expressions in the range of 0 to 255.

The `WAIT` statement causes execution to be suspended until a specified machine input port develops a specified bit pattern.

The data read at the port is [XOR](XOR)ed with the integer expression *j*, and then [AND](AND)ed with *n*.

If the result is zero, BASIC loops back and reads the data at the port again.

If the result is nonzero, execution continues with the next statement.

When executed, the `WAIT` statement tests the byte *n* for set bits. If any of the bits is set, then the program continues with the next statement in the program. `WAIT` does not wait for an entire pattern of bits to appear, but only for one of them to occur.

It is possible to enter an infinite loop with the `WAIT` statement. You can exit the loop by pressing CTRL-BREAK, or by resetting the system.

If *j* is omitted, zero is assumed.

## Example

```vb
100 WAIT 32,2
```

Suspends machine operation until port 32 receives 2 as input.
