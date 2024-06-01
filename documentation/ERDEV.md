# ERDEV

To return the actual value (`ERDEV`) of a device error, and the name of the device (`ERDEV$`) causing the error.

## Syntax

`ERDEV`

`ERDEV$`

## Comments

`ERDEV` will contain the error code from interrupt 24H in the lower 8 bits. Bits 8 to 15 from the attribute word in the Device Header Block are mapped directly into the upper 8 bits.

`ERDEV$` will contain the 8-byte character device name if the error was on a character device. It will contain the 2 byte block device name (A:, B:, etc.) if the device was not a character device.

## Example

Installed device driver lpt2: caused a "Printer out of paper" error via INT 24H.

`ERDEV` contains the error number 9 in the lower 8 bits, while the upper 8 bits contain the upper byte of the Device Header word attributes.

`ERDEV$ contains "LPT2: ".`
