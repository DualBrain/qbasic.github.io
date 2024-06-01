# RETURN

To return from a subroutine.

## Syntax

`RETURN [line number]`

## Comments

The `RETURN` statement causes BASIC to branch back to the statement following the most recent [GOSUB](GOSUB) statement. A subroutine may contain more than one `RETURN` statement to return from different points in the subroutine. Subroutines may appear anywhere in the program.

`RETURN line number` is primarily intended for use with event trapping. It sends the event-trapping routine back into the BASIC program at a fixed line number while still eliminating the [GOSUB](GOSUB) entry that the trap created.

When a trap is made for a particular event, the trap automatically causes a [STOP](STOP) on that event so that recursive traps can never take place. The `RETURN` from the trap routine automatically does an `ON` unless an explicit `OFF` has been performed inside the trap routine.

The non-local `RETURN` must be used with care. Any [GOSUB](GOSUB), [WHILE...WEND](WHILE...WEND), or [FOR...NEXT](FOR...NEXT) statement active at the time of the trap remains active.
