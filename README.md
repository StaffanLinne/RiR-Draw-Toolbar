# RiR-Draw-Toolbar
Toolbar focused checking drawings
For instructions on necessary installations see: [White Work](https://work.white.se/rhino-inside-revit/)  
General guides RiR: https://www.rhino3d.com/inside/revit/1.0/guides/  
Add the toolbar folder to your rhino.inside.revit tab according to this instruction (in the picture): https://discourse.mcneel.com/t/sharing-rhino-inside-scripts-among-team/131474/4 
or run the script with Grasshopper Player

## List of Scripts with short description

### Dimensioning
**00_Del_RiR** - Deletes dimensions and detail lines drawn by scripts below  
**01_Dim_Rooms** - Creates dimensions for rooms, detail lines are added to draw the dimensions between  
**02_Dim_Wall_Grid** - Creates dimensions from walls to nearest perpendicular grid  
**03_Dim_Cat_Center** - Creates dimensions for all objects of the selected object's category from center plane to closest wall  
**04_Dim_Cat_Side** - Creates dimensions for all objects of the selected object's category from side to closest wall  

### Rotate Walls slightly off axis
**10_Rev_Off Axis_Wall** - Shows walls in plan that are slightly off axis (smaller than 1 degree) from grid directions  
**11_Ro_Wall_Off Axis** - Rotates selected walls if they are slightly off axis

### Marking
**20_Qfilter** - Creates a filter that catches selected objects  
**21_Filled Reg_Ele.gh** - Creates filled region covering selected elements  
**22_Iso_Sel_Cat.gh** - Creates and applies a view template that is a copy of the existing view template but with all categories exept of the selected objects hidden. Click again and the parent template is restored. 

### Commenting
**30_Hide_Red** - Hides all red text, lines or dimensions on a view or all views on a sheet  
**31_Show_Red.gh** - Show all red text, lines or dimensions on a view or all views on a sheet




# Script Documentation

## 10_Rev_Off Axis_Wall

**Intent:**  
To visualize and select walls with off axis direction

**Input:**  
An active viewport with visible gridlines

**Output:**  
Filled regions showing which walls that are off axis, These walls are also selected in the viewport.

**Dependencies:**  
Rhino  
Revit  
Rhino Inside Revit  

**Instructions:**
The script is best runned from the Revit Toolbar
1. While in a plan view with visible gridlines, click the script icon.
2. If walls are selected by the script, you might use **11_Ro_Wall_Off Axis** to rotate the walls.   
The script will select walls that are >1 degree of the direction of a gridline.
A new type of filled region is created which is deletable with **00_Del_RiR**

**Limitations/Known issues** 
If your model lacks filled regions or if theese are hidden in ypor active view they might not be visible.

**Linked scripts**
**10_Rev_Off Axis_Wall** can be used to rotate selected walls. **00_Del_RiR** can be used to delete filled regions in view.

**Contact:** 
Staffan Linné, staffan.linne@white.se


## 11_Ro_Wall_Off Axis

**Intent:**  
Rotate selected walls so they align with grids visible in view

**Input:**  
Views selected in the viewport.

**Output:**  
A rotation of the selected walls if they are off axis

**Dependencies:**  
Rhino  
Revit  
Rhino Inside Revit  

**Instructions:**
The script is best runned from the Revit Toolbar

1. Select an object (or several) in the Revit viewport  
2. Run script  
3. The script will rotate walls according to the gridline that has the most similar direction to the wall line direction  

**Limitations/Known issues** 
Long walls with hosted objects might delete some of these objects. Reason unknown. Might be resolved in the future.

**Linked scripts**
10_Rev_Off Axis_Wall can be used to reveal and select walls off axis 

**Contact:** 
Staffan Linné, staffan.linne@white.se










## 20_QFilter

**Intent:**  
To create a filter based on the Category, Type (Type Name), Family and Type Mark of an model object. 

**Input:**  
One or several selected model objects in the viewport

**Output:**  
A filter applied to the view or view template. To "save" the filter - rename it.

**Dependencies:**  
Rhino  
Revit  
Rhino Inside Revit  

**Instructions:**
The script is best runned from the Revit Toolbar

1. Select an object (or several) in the Revit viewport  
2. Run script  
3. The script will create a filter and apply a random colour to the filter  
4. If you like to keep the filter, change the name, otherwise it will be updated next time you use Qfilter

**Limitations/Known issues** 
Has not been tested for linked models  
Does not work for certain object categories, for example views (section, elevations etc.) and annotation objects

**Contact:** 
Staffan Linné, staffan.linne@white.se
