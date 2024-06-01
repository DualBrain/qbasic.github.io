# PUT

To transfer graphics images to the screen.

## Syntax

`PUT(x,y),array,[,action verb]`

## Comments

*action verb* may be `PSET`, `PRESET`, `AND`, `OR`, `XOR`.

The *(x,y)* are the coordinates of the top-left corner of the image to be transferred.

The `PUT` and [GET](GET) statements transfer graphics images to and from the screen. `PUT` and [GET](GET) make possible animation and high-speed object motion in either graphics mode.

The `PUT` statement transfers the image stored in the array onto the screen. The specified point is the coordinate of the upper-left corner of the image. An "Illegal function call" error results if the image to be transferred is too large to fit onto the screen.

The action verb is used to interact the transferred image with the image already on the screen. `PSET` transfers the data onto the screen verbatim.

`PRESET` is the same as `PSET` except that an inverse image (black on white) is produced.

`AND` transfers the image only if an image already exists under the transferred image.

`OR` superimposes the image onto the existing image.

`XOR` is a special mode often used for animation. `XOR` causes the points on the screen to be inverted where a point exists in the array image. This behavior is exactly like the cursor on the screen. `XOR` is especially useful for animation. When an image is put against a complex background twice, the background is restored unchanged. An object can be moved around the screen without obliterating the background. The default action mode is `XOR`.

For more information about effects within the different modes, see the [COLOR](COLOR), [PALETTE](PALETTE), and [SCREEN](SCREEN) statements.

Animation of an object is usually performed as follows:

* Put the object(s) on the screen.
* Recalculate the new position of the object(s).
* Put the object(s) on the screen a second time at the old location(s) to remove the old image(s).
* Return to Step 1, this time putting the object(s) at the new location.

Movement done this way leaves the background unchanged. Flicker can be cut down by minimizing the time between Steps 4 and 1, and by making sure that there is enough time delay between Steps 1 and 3. If more than one object is being animated, process every object at once, one step at a time.

If it is not important to preserve the background, animation can be performed using the `PSET` action verb.

Leave a border around the image (when it is first gotten) as large or larger than the maximum distance the object will move. Thus, when an object is moved, this border effectively erases any points. This method may be somewhat faster than the method using `XOR` described above since only one `PUT` is required to move an object. However, the image to be `PUT` must be larger than the existing image.

## Example

```vb
10 CLS: SCREEN 1
20 PSET (130, 120)
30 DRAW "U25; E7; R20; D32; L6; U12; L14"
40 DRAW "D12; L6": PSET(137, 102)
50 DRAW "U4; E4; R8; D8; L12"
60 PSET (137, 88)
70 DRAW "E4; R20; D32; G4": PAINT (131,119)
80 DIM A (500)
90 GET (125, 130)-(170, 80), A
100 FOR I= 1 TO 1000: NEXT I
110 PUT (20, 20), A, PSET
120 FOR I= 1 TO 1000: NEXT i
130 GET (125, 130)-(170, 80), A
140 FOR I= 1 TO 1000: NEXT I
150 PUT (220, 130), A, PRESET
```
