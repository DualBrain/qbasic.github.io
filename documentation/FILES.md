# FILES

To print the names of the files residing on the specified drive.

## Syntax

`FILES [pathname]`

## Comments

If *pathname* is omitted, the command lists all files in the current directory of the selected drive. *pathname* may contain question marks (?) to match any character in the filename or extension. An asterisk (*) as the first character of the filename or extension will match any file or any extension.

This syntax also displays the name of the directory and the number of bytes in the file. When a tree-structured directory is used, two special symbols also appear.

Subdirectories are denoted by `<DIR>` following the directory name.

## Examples

```vb
FILES
FILES "*.BAS"
FILES "B:*.*"
FILES "TEST?.BAS"
```

`FILES` now allows pathnames. The directory for the specified path is displayed. If an explicit path is not given, the current directory is assumed.

```vb
FILES "ACCTS\"`
```

Lists all files in the directory named *accts*.

```vb
FILES "B:ACCTS\*.PAY"
```

Lists all files in the directory named *accts* that are on the diskette in drive B: and have the extension of *.PAY*.
