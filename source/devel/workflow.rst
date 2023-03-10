.. _Adding new workflow:

===================
Adding new workflow
===================

To add a new workflow all the task in the workflow should be added
to code base. see how to add a task :ref:`Adding new task`.


The step by step procedure to add a new workflow to the litesoph code 
base is described below.

1. Add the new workflow identifer in the :class:`litesoph.common.workflow_data.WorkflowTypes`

2. Define the new workflow in the :class:`litesoph.common.workflow_data.predefined_workflow`


.. autoclass:: litesoph.common.workflow_data.WorkflowTypes
   :members:
   :private-members:
   :member-order: bysource

.. autoclass:: litesoph.common.workflow_data.predefined_workflow
   :members:
   :private-members:
   :member-order: bysource