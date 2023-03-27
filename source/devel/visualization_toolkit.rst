========================================================
LITESOPH Visualization Toolkit
========================================================

LITESOPH Visualization Toolkit provides functionalities to plot and visualize simulation data. Current features include line plot, scatter plot, histogram and visualization of cube file(s) as movie rendered using blender.    

Modules, Functions and Working
===============================

* Module **litesoph/visualization/ls_viz_app.py** handles the frontend and backend of the standalone visualization toolkit.

    #. class **GuiAppTemplate:** handles the creation of GUI framework.
    #. class **CommonGraphParam:** inherits class GuiAppTemplate and responsible for handling common functionalities and features among different types of plot
    #. class **LinePlot:** handles plotting of Line, Scatter and Histogram Plot
    #. class **ContourPlot:** handles plotting of contour plot
    #. class **CubeFilePlot:** handles loading and visualization of cube files as movie
    #. class **LSVizApp:** inherits all the above plot classes and run the app.  

* How to add a new plot?
    
    #. Create a custom class for the new plot and inherit class **CommonGraphParam**.
    #. Define the methods and GUI controls required by the custom plot.
    #. Inherit the custom class to class **LSVizApp** and append custom class methods to class **LSVizApp**


