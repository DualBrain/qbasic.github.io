# CLOSE

To terminate input/output to a disk file or a device.

## Syntax

`CLOSE [[#]filenumber[,[#]filenumber]...]`

## Comments

*filenumber* is the number under which the file was opened. The association between a particular file or device and file number terminates upon execution of a `CLOSE` statement. The file or device may then be reopened using the same or a different file number. A `CLOSE` statement with no file number specified closes all open files and devices.

A `CLOSE` statement sent to a file or device opened for sequential output writes the final buffer of output to that file or device.

The [END](END), [NEW](NEW), [RESET](RESET), [SYSTEM](SYSTEM), or [RUN](RUN) and [LOAD](LOAD) (without `r` option) statements always close all files or devices automatically. [STOP](STOP) does not close files.

## Examples

```vb
250 CLOSE
```

This closes all open devices and files.

```vb
300 CLOSE 1, #2, #3
```

Closes all files and devices associated with file numbers `1`, `2`, and `3`.

## See Also

* [END](END), [NEW](NEW), [RESET](RESET), [SYSTEM](SYSTEM), [RUN](RUN), [LOAD](LOAD), [STOP](STOP)
