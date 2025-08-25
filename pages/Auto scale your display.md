# Auto scale your display

FreeCAD can automatically scale your drawing so that it fits you display. First you need to import the GUI object:

```
import FreeCADGui as Gui
```

Now just add this statement at the end of your program:

```
Gui.ActiveDocument.ActiveView.fitAll()
```

This is great, but you don't always want to fit the document to the entire screen. If you are working on a part of the object you might have rotated and zoomed into the view to see just that one area. However, when you do the fitall the view will revert back to the original one. Fortunately there is a way around this:

```
if App.ActiveDocument==None:
    print("First Run - creating document")
    doc = App.newDocument("ContactPrintFrame")
    firstRun=True
else:
    print("Using existing document")
    doc = App.ActiveDocument
    firstRun=False

```

Put the code above at the start of your program. It checks to see if there is an active document. If there is no active document it creates a new one and sets the **firstRun** variable to **True**. If there is an active document it sets the variable **doc** to this document. If not **doc** refers to the newly created one. Either way, the program now has a **doc** variable which refers to the active document and a **firstrun** flag that indicates that this is the first time the program has been run. Now you can use this to control whether or not the view is scaled. 

```
if firstRun:
	Gui.ActiveDocument.ActiveView.fitAll()
```

Now the view is only scaled the very first time that the program runs.  

[home](/README.md)
