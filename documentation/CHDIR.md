# CHDIR

To change from one working directory to another. 

## Syntax

`CHDIR pathname`

## Comments

`pathname` is a string expression of up to 63 characters.

## Example

To make *sales* the working directory on Drive A: and *inventory* the working directory on Drive B: (assume A: is the default drive), type the following commands:

```vb
CHDIR "SALES" 
CHDIR "B:INVENTORY" 
```
