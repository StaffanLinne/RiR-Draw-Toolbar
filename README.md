# RiR-Draw-Toolbar
Toolbar focused checking drawings
For instructions on necessary installations see: [White Work](https://work.white.se/rhino-inside-revit/)
Add the toolbar folder to your rhino.inside.revit tab according to this instruction
or run the script with

## List of Scripts with short description

# Dimensioning
**00_Del_Dim** - Deletes dimensions and detail lines drawn by scripts below  
**01_Dim_Rooms** - Creates dimensions for rooms, detail lines are added to draw the dimensions between  
**02_Dim_Wall_Grid** - Creates dimensions from walls to nearest perpendicular grid  
**03_Dim_Cat_Center** - Creates dimensions for all objects of the selected object's category from center plane to closest wall  
**04_Dim_Cat_Side** - Creates dimensions for all objects of the selected object's category from side to closest wall  

# Rotate Walls slightly off axis
**10_Rev_Off Axis_Wall** - Shows walls in plan that are slightly off axis (smaller than 1 degree) from grid directions  
**11_Ro_Wall_Off Axis** - Rotates selected walls if they are slightly off axis

# Marking
**20_Qfilter** - Creates a filter that catches selected objects  
**21_Filled Reg_Ele.gh** - Creates filled region covering selected elements
