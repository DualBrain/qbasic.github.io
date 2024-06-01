# DEF FN

To define and name a function written by the user.

## Syntax

`DEF FNname[arguments] expression`

```text
DEF FNname[(parameterlist)]
   [statementblock]
 FNname = expression
   [statementblock]
 [EXIT DEF]
   [statementblock]
END DEF
```

## Comments

*name* must be a legal variable name. This name, preceded by `FN`, becomes the name of the function.

*arguments* consists of those variable names in the function definition that are to be replaced when the function is called. The items in the list are separated by commas.

*expression* is an expression that performs the operation of the function. It is limited to one statement.

In the `DEF FN` statement, arguments serve only to define the function; they do not affect program variables that have the same name. A variable name used in a function definition may or may not appear in the argument. If it does, the value of the parameter is supplied when the function is called. Otherwise, the current value of the variable is used.

The variables in the argument represent, on a one-to-one basis, the argument variables or values that are to be given in the function call.

User-defined functions may be numeric or string. If a type is specified in the function name, the value of the expression is forced to that type before it is returned to the calling statement. If a type is specified in the function name and the argument type does not match, a `Type Mismatch` error occurs.

A user-defined function may be defined more than once in a program by repeating the `DEF FN` statement.

A `DEF FN` statement must be executed before the function it defines may be called. If a function is called before it has been defined, an `Undefined User Function` error occurs.

Recursive functions are not supported in the `DEF FN` statement.

## Example

```vb
400 R=1: S=2
410 DEF FNAB(X, Y)=X^3/Y^2
420 T=FNAB(R, S)
```

Line 410 defines the user-defined function `FNAB`. The function is called in line 420. When executed, the variable `T` will contain the value `R3` divided by `S2`, or `.25`.
