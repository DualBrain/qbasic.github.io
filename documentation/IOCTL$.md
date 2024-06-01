# IOCTL$

To allow BASIC to read a "control data" string from an open character device driver.

## Syntax

`IOCTL$([#]file number)`

## Comments

*file number* is the file number open to the device.

The `IOCTL$` function is generally used to get acknowledgement that an [IOCTL](IOCTL) statement succeeded or failed. It is also used to get device information, such as device width after an [IOCTL](IOCTL) statement requests it.

## Example

```vb
10 'GW is a possible command
20 'for get device width
30 OPEN "\DEV\MYLPT" AS#1
40 IOCTYL#1, "GW"
50 'Save it in WID
60 WID=VAL(IOCTL$(#1))
```
