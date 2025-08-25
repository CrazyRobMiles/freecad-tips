# Understanding dimensions

![3d image of a block](/images/macros/macro%203d%20object.png)

This is really hard to get your head around (or at least it was for me). If you look at the picture above you will see that in the bottom right there are X, Y and Z arrows which show the directions of the axes. When you write your code you need to assign names to values representing amounts in these directions. I've gone for **width** meaning **x**, **height** meaning **y** and **depth** meaning **z**. I've used these conventions in the following code:

```
width = 10
height = 20
depth = 30

frame = Part.makeBox(width, height, depth)
```

This makes the box that you can see above. These names work well if I am 3D printing a picture frame. I might want the frame to be 100mm wide 80mm high and 10mm deep. If you look at the object in the picture above, remember that it is 10 wide, 20 high and 30 deep. If you stare at it long enough this will make sense. The rectangle at the top is 10x20 and the whole block is 30mm high.

There are lots of different standards for expressing the X, Y and Z axes. My names work for me but you can use whatever works for you.

[Macro file location](/pages/Marco%20file%20location.md)

[home](/README.md)
