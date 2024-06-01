# VARPTR

To return the address in memory of the variable or file control block (FCB).

## Syntax

`VARPTR(variable name)`

`VARPTR(#file number)`

## Comments

`VARPTR` is usually used to obtain the address of a variable or array so it can be passed to an assembly language subroutine. A function call of the following form:

`VARPTR(A(0))`

is usually specified when passing an array, so that the lowest-addressed element of the array is returned.

All simple variables should be assigned before calling `VARPTR` for an array, because the addresses of the arrays change whenever a new simple variable is assigned.

`VARPTR (#file number)` returns the starting address of the BASIC File Control Block assigned to file number.

`VARPTR (variable name)` returns the address of the first byte of data identified with the variable name.

A value must be assigned to variable name prior to execution of `VARPTR`, otherwise, an "Illegal function call" error results.

Any type variable name may be used (numeric, string, or array), and the address returned will be an integer within the range of 32767 to -32768. If a negative address is returned, it is added to 65536 to obtain the actual address.

Offsets to information in the FCB from the address returned by `VARPTR` are shown in the following table:

*Table 7*

Offsets to FCB Information

| Offset | Length | Name   | Description |
| ------ | ------ | ------ | ----------- |
| 0      | 1      | Mode   | The mode in which the file was opened: |
|        |        |        | 1 Input only |
|        |        |        | 2 Output only |
|        |        |        | 4 Random I/O |
|        |        |        | 16 Append only |
|        |        |        | 32 Internal use |
|        |        |        | 64 Future use |
|        |        |        | 128 Internal use |
| 1      | 38     | FCB    | Diskette file control block. |
| 39     | 2      | CURLOC | Number of sectors read or written for sequential access. The last record number +1 read or written for random files. |
| 41     | 1      | ORNOFS | Number of bytes in sector when read or written. |
| 42     | 1      | NMLOFS | Number of bytes left in [INPUT#](INPUT#) buffer. |
| 43     | 3      | ***    | Reserved for future expansion. |
| 46     | 1      | DEVICE | Device Number: |
|        |        |        | 0-9 Disks A: through J: |
|        |        |        | 255 KYBD: |
|        |        |        | 254 SCRN: |
|        |        |        | 253 LPT1: |
|        |        |        | 252 CAS1: |
|        |        |        | 251 COM1: |
|        |        |        | 250 COM2: |
|        |        |        | 249 LPT2: |
|        |        |        | 248 LPT3: |
| 47     | 1      | WIDTH  | Device width. |
| 48     | 1      | POS    | Position in buffer for [PRINT](PRINT). |
| 49     | 1      | FLAGS  | Internal use during [BLOAD](BLOAD)/[BSAVE](BSAVE). Not used for data files. |
| 50     | 1      | OUTPOS | Output position used during tab expansion. |
| 51     | 128    | BUFFER | Physical data buffer. Used to transfer data between DOS and BASIC. Use this offset to examine data in sequential I/O mode. |
| 179    | 2      | VRECL  | Variable length record size. Default is 128. Set by length option in [OPEN](OPEN) statement. |
| 181    | 2      | PHYREC | Current physical record number. |
| 183    | 2      | LOGREC | Current logical record number. |
| 185    | 1      | ***	Future use. |
| 186    | 2      | OUTPOS | Disk files only. Output position for [PRINT#](PRINT#), [INPUT#](INPUT#), and [WRITE#](WRITE#). |
| 188    | n      | FIELD  | Actual FIELD data buffer. Size is determined by S:switch. VRECL bytes are transferred between BUFFER and FIELD on I/O operations. Use this offset to examine file data in random I/O mode. |

## Examples

```vb
100 X=VARPTR(Y)
```

When executed, the variable X will contain an address that points to the storage space assigned to the variable Y.

```vb
10 OPEN "DATA.FIL" AS #1
20 FCBADR = VARPTR(#1)
30 DATADR = FCBADR+188
40 A$ = PEEK(DATADR)
```

In line 20, FCBADR contains the start of FCB.

In line 30, DATADR contains the address of the data buffer.

In line 40, A$ contains the first byte in the data buffer.
