# STRIG(n)

To allow the use of a joystick by enabling or disabling the trapping of its buttons.

## Syntax

`STRIG(n) ON`

`STRIG(n) OFF`

`STRIG(n) STOP`

## Comments

*n* is 0, 2, 4, or 6, corresponding to the buttons on the joystick, where:

* 0 is button A1
* 2 is button B1
* 4 is button A2
* 6 is button B2

## Example

`STRIG(n) ON`

Enables trapping of the joystick buttons. After this statement is executed, BASIC checks to see if this button has been pressed before executing following statements.

`STRIG(n) OFF`

Disables BASIC from checking the state of the button.

`STRIG(n) STOP`

Disables trapping of a given button through the [ON STRIG(n)](ON-STRIG(n)) statement. But, any pressings are remembered so that trapping may take place once it is reenabled.
