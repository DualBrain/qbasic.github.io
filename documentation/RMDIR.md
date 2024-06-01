# RMDIR

To delete a subdirectory.

## Syntax

`RMDIR pathname`

## Comment

*pathname* is a string expression, not exceeding 63 characters, identifying the subdirectory to be removed from its parent.

The subdirectory to be deleted must be empty of all files except "." and ".." or a `Path file/access error` is given.

## Example

Referring to the sample directory structure illustrated in [CHDIR](CHDIR), the following command deletes the subdirectory *report*:

```vb
RMDIR "SALES\JOHN\REPORT"
```
