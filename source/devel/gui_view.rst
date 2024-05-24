

GUI View Modules
==================
Modules for creating a new GUI View Page or updating existing ones.
Mainly deals with tkinter class and objects. Refer to tkinter for more details.

Modules under LITESOPH
-----------------------
litesoph/gui/design/template.py

Includes templated view designs.

.. _view_cls:

Class View
~~~~~~~~~~
    Tkinter Frame template for generic LITESOPH page.    

Functionalities
^^^^^^^^^^^^^^^^^
    Defines a parent frame to hold multiple sub-frames. Includes class methods to create widgets for job submit.

Class InputFrame
~~~~~~~~~~~~~~~~~
    Tkinter Frame template for collecting LITESOPH inputs.

.. _inp_param:

Parameters
^^^^^^^^^^

    * *master*: (ttk.Frame) Parent tkinter frame
    * *fields*: (dict) Nested dictionary for inputs defined by example dictionary 
    * *visible_state*: (dict): dictionary with key(defined in fields)-value(initial visible_state boolean)
    * *padx*: (int)
    * *pady*: (int)
    * *column_minsize*: (int)

    Definition : *fields*

        To define a nested dictionary structure with following format

        *key* : string variable assigned for the input parameter

        *value* : dictionary with description of the input parameters and respective widgets.


    .. code :: python

            {
                "tab": 'Tab name assigned for the input key(default: Main)',
                "group": 'Group name under the tab if applicable',
                "text": 'Text to display',
                "help": 'Additional details to the input key',
                "widget": 'Type of tkinter widget',
                "default_value": 'Default value',
                "values": 'List of values (for Combobox widget type)',
                "type": 'Variable type (assigned from default_value/values if not explicitly defined)',
                "visible": 'Boolean for show/hide the input on default view',
                "switch_keys": 'Toggle condition for dependencies with preceeding keys defined'
            }

Functionalities
^^^^^^^^^^^^^^^^
        Creates single or multiple tabs defined under the Parameters: fields

    Relevant Methods

        * init_widgets( )

            Method to handle defaults. Sets the default values from fields option, by default.
            Updates defaults from var_values if ignore_state is False
            
            Parameters:
                *   fields: dictionary with key and default values
                *   ignore_state: boolean to check whether to update the assigned defaults or not
                *   var_values: dictionary to update required set of input defaults
        *   trace_variables( )

                Method to trace the events on any update of widgets using switch_keys defined with fields.
                Needs modification for cases beyond simple switch conditions
            
        *   get_values( )

                Method to collect selected field values. Returns a dictionary of the same.    
        
    Added Tkinter Widgets

    *   ttk.Combobox
    *   ttk.Checkbutton
    *   ttk.Entry
    *   ttk.SpinBox 

Usage
~~~~~~
Instructions for creating/modifying GUI frames under LITESOPH inputs
        
Creating a new GUI frame
^^^^^^^^^^^^^^^^^^^^^^^^^
1.  Refer to :ref:`view_cls` to inherit the LITESOPH defined frames, if applicable. Alternatively, create new tkinter frame as the parent frame.
2.  Define the :ref:`inp_param` : *fields*. 
3.  Initiate the InputFrame class with :ref:`inp_param` : *fields* 
4.  Modify the method trace_variables( ) to add more control to the widgets
5.  Use the method get_values() to get the set of selected input parameters
6.  The default values gets assigned from Parameters : *fields*. To customise the defaults, use the method init_widgets( ). 

Updating the existing frames
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1.  Update items to :ref:`inp_param` : *fields* 
2.  Cross-check the method trace_variables( ) to consider additional control of widgets

Visual Parameters Modules
---------------------------
litesoph/gui/visual_parameter.py

Functionalities
~~~~~~~~~~~~~~~
    Methods for customised font designs, widget attributes
