# Making a Macro

You open the Macro dialog box in FreeCAD by selecting **Macro** on the top menu. This opens the Execute Macro dialog. You can see that I've already created a few macros of my own. Now click the **Create**  button to make your first macro. This will open up a little dialogue which will ask you for a filename. 

![Dialogue with the filename demo](/images/macros/macro%20demo.png)

Type in the name of your macro and click **OK**. When you go back to the Macro dialogue you will see that your new macro has been created. Note that the macro file has the language extension **.FCMacro**.

![Macro dialog with demo selected](/images/macros/macro%20demo%20selected.png)

 Select your new macro and click **Edit**

 ![FreeCAD application with the Macro editor open](/images/macros/macro%20editing.png)

 We now have a text area where we can enter our Python. Let's make a block.

 ```
import FreeCAD as App
import Part

width = 10
height = 20
depth = 30

frame = Part.makeBox(width, height, depth)

doc = App.ActiveDocument or App.newDocument("Frame")

frame_obj = doc.addObject("Part::Feature", "Frame")
frame_obj.Shape = frame
 ```

The program above makes a block 10mm wide, 20mm deep and 30mm high. Paste this into the edit window and then press the green right-pointing arrow on the top toolbar to run the macro. 

![toolbar with green run button outlined in red](/images/macros/macro%20run%20button.png)

With a bit of luck the program will work and a new tab will appear.

![FreeCAD application with new tab](/images/macros/macro%20newtab.png)

You should also notice that a new item, Frame, has appeared in the model. Click on the tab at the bottom of the upper window to view the part you have created. 

![Frame tab in FreeCAD](/images/macros/macro%20frametab.png)

This will switch the view to the frame containing the part display:

![FreeCAD application with part display](/images/macros/macro%20newpart.png)

You might not see what is displayed above because I moved the view around using my mouse. You move the display by:

* click and drag to rotate the view. The view rotates around the point you clicked on. 
* use the scroll wheel on the mouse to zoom in and out. The display zooms around the position of the mouse cursor. 
* hold down the middle button (or scroll wheel) and move the mouse to drag the view left and right

[Understanding Dimensions](/pages/Understanding%20dimensions.md)

[home](/README.md)





