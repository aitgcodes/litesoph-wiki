.. _Adding new workflow:

========================
Adding new workflow type
========================


To add a new workflow type, all the tasks in the workflow should already be implemented
in the code base. see :ref:`Adding new task`.

All the workflows in the litesoph are defined in the dictionary :class:`litesoph.common.workflows_data.predefined_workflow`.


The step by step procedure to add a new workflow type to the litesoph code 
base is described below.

1.  Add the new workflow type identifier in the class :class:`~litesoph.common.workflows_data.WorkflowTypes`.

    Every workflow types has a unique identifier that is used identify them.
    This identifier is defined in the class
    :class:`~litesoph.common.workflows_data.WorkflowTypes`

    ::

        Class WorkflowTypes(str, enum):
            .
            .
            NEW_WORKFLOW = 'new_workflow'

    This string will be used to identifier the new workflow type

2. Define the new workflow in the dictionary :class:`litesoph.common.workflows_data.predefined_workflow`.

    All the workflow types are defined in the dictionary :class:`~litesoph.common.workflows_data.predefined_workflow`

    The workflow is defined as an ordered chain of tasks that needs to be completed
    to obtain a desired quantity, like Averaged spectrum of a molecule. 
    In litesoph, workflow is modeled as an ordered chain of blocks, where each block
    is group of the same task type but with different input parameters.

    For Example, Averaged spectrum of a molecule workflow can be modeled as:

    ::
        
            Block-1                  Block-2                  Block-3                  Block-4
        |---------------|      |-----------------|      |--------------------|    |----------------|
        |               |      |                 |      |                    |    |                |
        | 1. ground     |----> |  2. RT-TDDFT- x |----->| 5.compute-spectra-x|--->| 8. compute     | 
        |    state      |      |  3. RT-TDDFT- y |      | 6.compute-spectra-y|    | average spectra|
        |---------------|      |  4. RT-TDDFT- z |      | 7.compute-spectra-z|    |----------------|
                               |-----------------|      |--------------------|  
    
    All the information about the workflow will be encoded in the dictionary.
    The averaged spectrum workflow is encoded in the dictionary as follows:

    ::

        predefined_workflow = {
            .
            .
            .# key is workflow type identifier 
            "averaged_spectrum": {
                "name": "Averaged Spectrum",
                "blocks": [{'name' : 'Ground State',
                            'store_same_task_type': True,
                            'task_type': tt.GROUND_STATE
                            }, 
                            {'name':'RT TDDFT',
                            'store_same_task_type': True,
                            'task_type': tt.RT_TDDFT
                            }, 
                            {'name':'Compute Spectrum',
                            'store_same_task_type': True,
                            'task_type': tt.COMPUTE_SPECTRUM
                            },  
                            {'name': 'Compute Averaged Spectrum',
                            'store_same_task_type': True,
                            'task_type': tt.COMPUTE_AVERAGED_SPECTRUM
                            },  
                            {'name': 'End'}],

                "task_sequence" : [step(0 ,0 , tt.GROUND_STATE),
                            step(1 ,1 ,tt.RT_TDDFT, {
                                                'polarization':[1,0,0],
                                                        }),
                            step(2 ,1 ,tt.RT_TDDFT, {
                                                'polarization': [0,1,0],
                                                        }),
                            step(3 ,1 ,tt.RT_TDDFT, {
                                                'polarization': [0,0,1],
                                                        }),
                            step(4 ,2 ,tt.COMPUTE_SPECTRUM),
                            step(5 ,2 ,tt.COMPUTE_SPECTRUM),
                            step(6 ,2 ,tt.COMPUTE_SPECTRUM),
                            step(7, 3, tt.COMPUTE_AVERAGED_SPECTRUM)],
                }
        
        }

    This information will be used to build WorkflowInfo objects will be used in executing
    the workflow. see :class:`~litesoph.common.data_sturcture.data_classes.WorkflowInfo`

.. autoclass:: litesoph.common.workflows_data.WorkflowTypes
   :members:
   :private-members:
   :member-order: bysource

.. autoclass:: litesoph.common.workflows_data.predefined_workflow
   :members:
   :private-members:
   :member-order: bysource