# Exporting your designs

Now that we can make a design, the next thing we need to know is how to save the design in a file we can 3D print. The export behaviors live in the **Mesh** class which needs to be imported into the Python program from the library.

```
import Mesh
```

The Mesh class provides a bunch of useful methods, including **export**:

```
import FreeCAD as App
import Part
import Mesh

width = 1
height = 2
depth = 3

frame = Part.makeBox(width, height, depth)

doc = App.ActiveDocument or App.newDocument("Frame")

frame_obj = doc.addObject("Part::Feature", "Frame")
frame_obj.Shape = frame

Mesh.export([frame_obj], u"C:/Users/robmi/OneDrive/2025 Year/Projects/Film Holder/box.stl")

```

The program above creates a box and then exports the design into a file. The exporting is performed by the call of **export** in the last statement in the program.  The export method accepts two parameters: 

1. A list of objects to be written. 
1. The path to the file to be written

If you are only saving one object you must still provide a list to the export function. Otherwise the export will fail. 

The path in the example code above points to a file in my projects folder. If you leave the path out the export will fail because FreeCAD will try to write into the folder containing the FreeCAD program, and this is write protected.

[home](/README.md)
