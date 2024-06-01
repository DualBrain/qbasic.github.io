# OPEN COM(n)

To allocate a buffer to support RS-232 asynchronous communications with other computers and peripheral devices in the same manner as OPEN for disk files.

## Syntax

`OPEN "COM[n]:[speed][,parity][,data] [,stop][,RS][,CS[n]][,DS[n]][,CD[n]][,LF] [,PE]" AS [#]filenum [LEN=number]`

## Comments

`COM[n]` is a valid communications device: com1: or com2:.

*speed* is a literal integer specifying the transmit/receive baud rate. Valid speeds are as follows: 75, 110, 150, 300, 600, 1200, 1800, 2400, 4800, and 9600. The default is 300 bps.

*parity* is a one-character literal specifying the parity for transmitting and receiving. Valid characters specifying parity are as follows:

| P | Name | Details |
| - | ---- | ------- |
| S | SPACE | Parity bit always transmitted and received as space (0 bit). |
| M | MARK | Parity bit always transmitted and received as mark (1 bit). |
| O | ODD | Odd transmit parity; odd receive parity checking. Default is even. |
| E | EVEN | Even transmit parity; even receive parity checking. Even is default. |
| N | NONE | No transmit parity. No receive parity checking. |

*data* is a literal integer indicating number of transmit/receive data bits. Valid values for the number of data bits are 4, 5, 6, 7, or 8, the default is 7 bits.

> Four data bits with no parity is illegal; eight data bits with any parity is illegal.

*stop* is a literal integer expression returning a valid file number. Valid values for number of stop bits are 1 and 2. If omitted, 75 and 110 bps transmit two stop bits. All others transmit one stop bit.

*filenum* is a number between 1 and the maximum number of files allowed. A communications device may be opened to only one file number at a time. The *filenum* is associated with the file for as long as the file is open, and is used to refer other COM I/O statements to the file. Any coding errors within the filename string result in "Bad file name" errors. An indication as to which parameters are in error is not given.

*number* is the maximum number of bytes which can be read from the communications buffer when using GET or PUT default of 128 bytes.

A "Device timeout" error occurs if "data set ready" (DSR) is not detected.

The `RS`, `CS`, `DS`, `DC`, `LF`, and `PE` options affect the line signals as follows:

| Option | Function |
| ------ | -------- |
| RS     | suppresses RTS (request to send) |
| CS[n]  | controls CTS (clear to send) |
| DS[n]  | controls DSR (data set ready) |
| CD[n]  | controls CD (carrier detect) |
| LF     | sends a line feed at each return |
| PE     | enables parity checking |

*n* is the number of milliseconds to wait (0-65535) for that signal before a device timeout error occurs. Defaults are: CS1000, DS1000, and CD0. If `RS` was specified then CS0 is the default. If *n* is omitted, then timeout is set to 0.

See Appendix F in the BASIC User's Guide for more information about communications.

## Examples

In the following, File 1 is opened for communications with all defaults: speed at 300 bps, even parity, seven data bits, and one stop bit.

```vb
10 OPEN "COM1:" AS 1
```

In the following, File 2 is opened for communications at 2400 bps. Parity and number of data bits are defaulted.

```vb
20 OPEN "COM1:2400" AS #2
```

In the following, File 1 is opened for asynchronous I/O at 1200 bits/second. No parity is to be produced or checked.

```vb
10 OPEN "COM1:1200,N,8" AS #1
```
