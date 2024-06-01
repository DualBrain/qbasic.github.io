# ENVIRON

To allow the user to modify parameters in BASIC's environment string table. This may be to change the path parameter for a child process, (see [ENVIRON$](ENVIRON$), [SHELL](SHELL), and the MS-DOS utilities `PATH` command), or to pass parameters to a child by inventing a new environment parameter.

## Syntax

`ENVIRON string`

*string* is a valid string expression containing the new environment string parameter.

*string* must be of the following form...

*parmid=text*

...where *parmid* is the name of the parameter such as `PATH`.

*parmid* must be separated from text by an equal sign or a blank. `ENVIRON` takes everything to the left of the first blank or equal sign as the *parmid*; everything following is taken as text.

*text* is the new parameter text. If text is a null string, or consists only of a single semicolon, then the parameter (including *parmid=*) is removed from the environment string table, and the table is compressed. *text* must not contain any embedded blanks.

If *parmid* does not exist, then *string* is added at the end of the environment string table.

If *parmid* does exist, it is deleted, the environment string table is compressed, and the new string is added at the end.

## Examples

Assuming the environment string table is empty, the following statement will create a default path to the root directory on Disk A:

```vb
ENVIRON "PATH=A:\"
```

If your work subdirectory were john, you would be able to get DEBUG from the root.

A new parameter may be added:

```vb
ENVIRON "COMSPEC=A:\COMMAND.COM"
```

The environment string table now contains

`PATH=A:\; COMSPEC=A:\COMMAND.COM`

The path may be changed to a new value:

```vb
ENVIRON "PATH=A:\SALES; A:\ACCOUNTING"
```

The path parameter may be appended by using the [ENVIRON$](ENVIRON$) function with the `ENVIRON` statement:

```vb
ENVIRON "PATH="+ENVIRON$("PATH")+"; B:\SAMPLES"
```

Finally, delete the parameter COMSPEC:

```vb
ENVIRON "COMSPEC=;"
```

The environment string table now contains

`PATH=A:\SALES; A:\ACCOUNTING; B:\SAMPLES`

## See Also

* [ENVIRON$](ENVIRON$), [SHELL](SHELL)
