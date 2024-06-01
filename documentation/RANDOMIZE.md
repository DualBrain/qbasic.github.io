# RANDOMIZE

To reseed the random number generator.

## Syntax

`RANDOMIZE expression`

`RANDOMIZE TIMER`

## Comments

If the random number generator is not reseeded, the [RND](RND) function returns the same sequence of random numbers each time the program is run.

To change the sequence of random numbers every time the program is run, place a `RANDOMIZE` statement at the beginning of the program, and change the argument with each run (see [RND](RND) function).

`RANDOMIZE expression` will not force floating-point values to integer. *expression* may be any numeric formula.

```vb
RANDOMIZE TIMER 
```

## Examples

The internal clock can be set at intervals.

```vb
RANDOMIZE TIMER
FOR I = 1 to 5
  PRINT RND;
NEXT I
```

The internal clock can be used for random number seed.

```vb
N = VAL(MID$(TIME$, 7, 2)) 'get seconds for seed
RANDOMIZE N                'install number
PRINT N                    'print seconds
PRINT RND                  'print random number generated
```
