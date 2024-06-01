# VIEW

To define a physical viewport limit from *x1,y1* (upper-left x,y coordinates) to *x2,y2* (lower-right x,y coordinates).

## Syntax

`VIEW [[SCREEN][(x1,y1)-(x2,y2) [,[fill][,[border]]]]`

## Comments

[RUN](RUN) or `VIEW` with no arguments define the entire screen as the viewport.

*(x1,y1)* are the upper-left coordinates.

*(x2,y2)* are the lower-right coordinates.

The *fill* attribute lets you fill the view area with color.

The *border* attribute lets you draw a line surrounding the viewport if space for a border is available. If *border* is omitted, no border is drawn.

The *x* and *y* coordinates must be within the physical bounds of the screen and define the rectangle within the screen that graphics map into. The *x* and *y* coordinate pairs will be sorted, with the smallest values placed first.

Points are plotted relative to the viewpoint if the screen argument is omitted; that is, *x1* and *y1* are added to the *x* and *y* coordinates before the point is plotted.

It is possible to have a varied number of pairs of *x* and *y*. The only restriction is that *x1* cannot equal *x2*, and *y1* cannot equal *y2*.

Points are plotted absolutely if the [SCREEN](SCREEN) argument is present. Only points within the current viewpoint will be plotted.

When using `VIEW`, the [CLS](CLS) statement clears only the current viewport. To clear the entire screen, you must use `VIEW` to disable the viewports. Then use [CLS](CLS) to clear the screen. [CLS](CLS) does not move the cursor to home. Press CTRL-HOME to send the cursor home, and clear the screen.

## Examples

The following defines a viewport such that the statement [PSET](PSET)`(0,0),3` would set down a point at the physical screen location 10,10.

```vb
VIEW (10, 10)-(200, 100)
```

The following defines a viewport such that the point designated by the statement [PSET](PSET)`(0,0),3` would not appear because 0,0 is outside of the viewport. [PSET](PSET)`(10,10),3` would be within the viewport.

```vb
VIEW SCREEN (10, 10)-(200, 100)
```
