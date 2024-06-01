# IOCTL

To allow BASIC to send a "control data" string to a character device driver anytime after the driver has been opened.

## Syntax

`IOCTL[#]file number,string`

## Comments

*file* number is the file number open to the device driver.

*string* is a valid string expression containing characters that control the device.

`IOCTL` commands are generally 2 to 3 characters followed by an optional alphanumeric argument. An `IOCTL` string may be up to 255 bytes long, with commands within the string separated by semicolons.

## Examples

If a user had installed a driver to replace LPT1, and that driver was able to set page length (the number of lines to print on a page before issuing a form feed), then the following lines would open the new LPT1 driver and set the page length to 66 lines:

```vb
OPEN "LPT1:" FOR OUTPUT AS #1
IOCTL #1, "PL66"
```

The following statements open LPT1 with an initial page length of 56 lines:

```vb
OPEN "\DEV\LPT1" FOR OUTPUT AS #1
IOCTL #1, "PL56"
```
