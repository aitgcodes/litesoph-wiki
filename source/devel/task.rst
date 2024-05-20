.. _Adding new task:

===============
Adding new task
===============

To add a new task to the litesoph, choose an engine that is already
interfaced with the code base, else see :ref:`Adding new engine`.

All the tasks in litesoph are classes that inherits
from the base class :class:`litesoph.common.task.Task`. 
The task class is responsible for generating input scripts, job scripts, 
running the job, and storing the output generated for that task. 

The step by step procedure to add a new task to the litesoph code 
base is described below.


1. Add the new task identifier in the :class:`litesoph.common.task_data.TaskTypes`.

2. Create your task class by subclassing the :class:`litesoph.common.task.Task`

3. Implement the abstract methods of the :class:`litesoph.common.task.Task`

4. update the egine manger to account for the new added task. see :ref:`Adding new engine`


.. seealso::
    * The code for our GPAW tasks: `litesoph.engines.gpaw.gpaw_task.py`


Description of base-classes
===========================


The Task base-classes
-----------------------

.. autoclass:: litesoph.common.Task
   :members:
   :private-members:
   :member-order: bysource


.. autoclass:: litesoph.common.task_data.TaskTypes
   :members:
   :private-members:
   :member-order: bysource