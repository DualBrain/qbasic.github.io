# NAME

To change the name of a disk file.

## Syntax

`NAME old filename AS new filename`

## Comments

*old filename* must exist and *new filename* must not exist; otherwise, an error results.

After a `NAME` command, the file exists on the same diskette, in the same disk location, with the new name.

## Example

```vb
NAME "ACCTS" AS "LEDGER"
```

The file formerly named *ACCTS* will now be named *LEDGER*. The file content and physical location on the diskette is unchanged.
