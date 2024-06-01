# OPEN

To establish input/output (I/O) to a file or device.

## Syntax

`OPEN mode,[#]file number,filename[,reclen]`

`OPEN filename [FOR mode][ACCESS access][lock] AS [#]file number [LEN=reclen]`

## Comments

*filename* is the name of the file.

*mode* (first syntax) is a string expression with one of the following characters:

- `O` Sequential output mode
- `I` Sequential input mode
- `R` Random input/output mode
- `A` Position to end of file

*mode* (second syntax) determines the initial positioning within the file, and the action to be taken if the file does not exist. If the `FOR` mode clause is omitted, the initial position is at the beginning of the file. If the file is not found, one is created. This is the random I/O mode. That is, records may be read or written at any position within the file. The valid modes and actions taken are as follows:

- `INPUT` Position to the beginning of the file. A "File not found" error is given if the file does not exist.
- `OUTPUT` Position to the beginning of the file. If the file does not exist, one is created.
- `APPEND` Position to the end of the file. If the file does not exist, one is created.
- `RANDOM` Specifies random input or output mode.

*mode* must be a string constant. Do not enclose mode in double quotation marks. access can be one of the following:

- `READ`
- `WRITE`
- `READ WRITE`

*file number* is a number between `1` and the maximum number of files allowed. The number associates an I/O buffer with a disk file or device. This association exists until a [CLOSE](CLOOSE) or [CLOSE](CLOSE) `file number` statement is executed.

*reclen* is an integer expression within the range of `1-32767` that sets the record length to be used for random files. If omitted, the record length defaults to 128-byte records.

When *reclen* is used for sequential files, the default is `128` bytes.

A disk file must be opened before any disk I/O operation can be performed on that file. `OPEN` allocates a buffer for I/O to the file and determines the mode of access that is used with the buffer.

More than one file can be opened for input or random access at one time with different file numbers. For example, the following statements are allowed:

```vb
OPEN "B:TEMP" FOR INPUT AS #1
OPEN "B:TEMP" FOR INPUT AS #2
```

However, a file may be opened only once for output or appending. For example, the following statements are illegal:

```vb
OPEN "TEMP" FOR OUTPUT AS #1
OPEN "TEMP" FOR OUTPUT AS #2
```

## NOTE

Be sure to close all files before removing diskettes from the disk drives (see [CLOSE](CLOSE) and [RESET](RESET)).

A device may be one of the following:

- `A:`, `B:`, `C:`... Disk Drive
- `KYBD:` Keyboard (input only)
- `SCRN:` Screen (output only)
- `LPT1:` Line Printer 1
- `LPT2:` Line Printer 2
- `LPT3:` Line Printer 3
- `COM1:` RS-232 Communications 1
- `COM2:` RS-232 Communications 2

For each device, the following `OPEN` modes are allowed:

- `KYBD:` Input Only
- `SCRN:` Output Only
- `LPT1:` Output Only
- `LPT2:` Output Only
- `LPT3:` Output Only
- `COM1:` Input, Output, or Random Only
- `COM2:` Input, Output, or Random Only
- Disk files allow all modes.

When a disk file is opened for `APPEND`, the position is initially at the end of the file, and the record number is set to the last record of the file (`LOF(x)/128`). [PRINT](PRINT#), [WRITE#](WRITE#), or [PUT#](PUT#) then extends the file. The program may position elsewhere in the file with a [GET#](GET#) statement. If this is done, the mode is changed to random and the position moves to the record indicated.

Once the position is moved from the end of the file, additional records may be appended to the file by executing a [GET](GET#) `#x,` [LOF](LOF)`(x) / reclen` statement. This positions the file pointer at the end of the file in preparation for appending.

Any values entered outside of the ranges given result in `Illegal function call` errors. The files are not opened.

If the file is opened as `INPUT`, attempts to write to the file result in `Bad file mode` errors.

If the file is opened as `OUTPUT`, attempts to read the file result in `Bad file mode` errors.

Opening a file for `OUTPUT` or `APPEND` fails, if the file is already open in any mode.

Since it is possible to reference the same file in a subdirectory via different paths, it is nearly impossible for BASIC to know that it is the same file simply by looking at the path. For this reason, BASIC does not let you open the file for `OUTPUT` or `APPEND` if it is on the same disk, even if the path is different. For example if *mary* is your working directory, the following statements all refer to the same file:

```vb
OPEN "REPORT"
OPEN "\SALES\MARY\REPORT"
OPEN "..\MARY\REPORT"
OPEN "..\..\MARY\REPORT"
```

At any one time, it is possible to have a particular diskette filename open under more than one file number. Each file number has a different buffer, so several records from the same file may be kept in memory for quick access. This allows different modes to be used for different purposes; or, for program clarity, different file numbers to be used for different modes of access.

If the `LEN=reclen` option is used, reclen may not exceed the value set by the `/s:reclen` switch option in the command line.

In a network environment, the use of the `OPEN` statement is based upon two different sets of circumstances:

* Devices may be shared on a network for specific purposes only, so that `OPEN` statements may be restricted to specific modes among those which might be requested, such as: `INPUT`, `OUTPUT`, `APPEND`, and default (random). 
* Files may be restricted by the implementation of an `OPEN` statement which allows a process to specify an access to the successfully opened file. The access determines a guaranteed exclusivity range on that file by the process while the `OPEN` statement is in effect.

*lock* can be one of the following:

- `SHARED` "deny none" mode. No restrictions are placed on the read/write accessibility of the the file to another process, except that the default mode is not allowed by any of the modes including `SHARED`.
- `LOCK READ` "deny read" mode. Once a file is opened with the `LOCK READ` access, no other process is granted read-access to that file. An attempt to open a file with this access will be unsuccessful, if the file is currently open in default mode or with a read access.
- `LOCK WRITE` "deny write" mode. A file successfully opened with `LOCK WRITE` access may not be opened for a write access by another process. An attempt to open a file with this access will be unsuccessful if the file has been opened in default mode, or with a write access by another process.
- `LOCK READ WRITE` "deny all" or "exclusive" mode. If a file is successfully opened with this access, the process has exclusive access to the file. A file that is currently open in this mode cannot be opened again in any mode by any process.
- default "compatibility" mode, in which the compatibility with other BASICs is understood. No access is specified. The file may be opened any number of times by a process, provided that the file is not currently opened by another process. Other processes are denied access to the file while it is open under default access. Therefore, it is functionally exclusive. 

When an attempt is made to open a file that has been previously accessed by another process, the error `Permission Denied` will result. An example of a situation generating this error is when a process attempts to `OPEN SHARED` on a file that is already `OPEN LOCK READ WRITE` by another process.

If an `OPEN` statement fails because the mode is incompatible with network-installed sharing access to a device, the error generated is `Path/File Access Error`. An example of this is when a process is attempting to `OPEN` a file for output on a directory that has been shared for read only.

For more information about using files in a networking environment, see the [LOCK](LOCK) and [UNLOCK](UNLOCK) statements.

## Example

```vb
10 OPEN "I",2,"INVEN"
```

Opens file `2`, *inven*, for sequential input.
