.. _Adding new task:

===============
Adding new task
===============

To add a new task to the litesoph choose a engine which is already
interfaced the code base, to add new engine :ref:`Adding new engine`.


The step by step procedure to add a new task to the litesoph code 
base is described below.


1. Add the new task identifer in the :class:`litesoph.common.task_data.TaskTypes`.

2. Create your task class by subclassing the :class:`litesoph.common.task.Task`

3. Implement the abstract methods of the :class:`litesoph.common.task.Task`

4. update the egine manger's function :func:`litesoph.common.EngineManager.get_task`. :ref:`Adding new engine`



.. seealso::
    * The code for our NWChem interface: :git:`litesoph.engines.gpaw.gpaw_task.py`


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