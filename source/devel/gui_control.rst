GUI Control Modules
#####################
Modules to control the GUI view for particular task.
Binds different tkinter events with required class methods.

Features and Functionalities
=============================
This module is responsible for managing overall functionality of GUI. 
Interacts with LITESOPH manager and views modules.
Contains attributes and methods related to control logic, user interface events.

Modules under LITESOPH
=======================

*   GUIApp : Main Application control class

*   ProjectController: Base Class assigned for handling LITESOPH project

*   WorkFlowController: Base Class assigned for handling workflow under LITESOPH project

*   TaskController: Base Class defined for single Task related actions. 


Class TaskController
--------------------
litesoph/gui/taskcontroller.py

Base Controller Class to assemble common functions and attributes required for handling LITESOPH defined tasks.
Acts on assigned GUI view to control and regulate the flow of tkinter events.

.. Attributes
.. ~~~~~~~~~~~~~~
.. *   workflow_controller : controller attribute for 
.. *   app :  


Relevant Methods
~~~~~~~~~~~~~~~~
*   set_task( )
        Method to handle all functions under a GUI frame.
        Assigns particular view and binds respective tkinter events to functions.
        Includes method related to default set of view and parameters.

Usage
---------
Instructions for adding control logic to GUI frames.

Defining a TaskController
~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.  Sub class of TaskController is assigned to activate the working of GUI Frame

2.  Modify the class method set_task( ) depending on the requirement of the current task

3.  Bind the TaskController Sub-class to the task-view mapping under WorkFlowController      

Remarks
~~~~~~~~~~~
    Sub-class of TaskController is only required in the case of LITESOPH interfaced tasks.
    Alternatively, new frame can be handled by independent or controller object under TaskController.