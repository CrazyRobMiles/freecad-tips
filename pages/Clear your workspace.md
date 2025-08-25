# Clear Your Workspace

A FreeCAD design is made up of objects, each of which represents a particular element in the thing you are building. You can create your objects in Python:

```
frame = Part.makeBox(width, height, depth)
```

The statement above makes a **frame** as a 3D object with a particular size. This is a 3D object, but at the moment it isn’t part of a design document. So, let’s make a document:

```
doc = App.ActiveDocument or App.newDocument("Frame")
```
This statement makes a new document called **doc**. Better yet, it only makes a new document if we don’t already have one.  Now we can add our frame to the document:

```
frame_obj = doc.addObject("Part::Feature", "Frame")
frame_obj.Shape = frame
```

The first statement above adds a **feature** to the document. the second sets the shape on this feature to the **frame** that we created. Great stuff. But if you re-run the program you get another feature created and added to the document. Which you don’t want. 

The statement above would make a box of a particular size and then make the **frame** variable refer to it. You can create more complex shapes by cutting and fusing objects with each other. Once you have such an object, you'll want to add it to the design you are crating. 


##  Delete all existing objects in the document

That’s why the statements at the top are so useful. They work through the document and clear away everything so that you can add new versions.

```
for obj in doc.Objects:
    doc.removeObject(obj.Name)
```

This allows you replace existing code generated objects with new ones so your workspace doesn’t fill up with stuff. This is useful if you are making objects with software:

[Arrange your windows](/pages/Arrange%20your%20windows.md)

[home](/README.md)
