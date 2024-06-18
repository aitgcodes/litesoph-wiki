.. _laser-masking:

Laser-Masking
=============

.. note::
   Compatible Engines: GPAW

.. image:: ./masking_workflow.png
   :width: 800
   :alt: Laser_masking

The Workflow for the Laser-masking is described below. As the feature is only available in GPAW, the **GS** parameters should be chosen 
accordingly. For example, PBE as Exchange Correlation and lcao as Basis Type.  

**1.** Start the workflow with ground state calculation. See :ref:`GS`

**2.** After the ground state calculation is done, proceed to RT-TDDFT calculation with laser pulse.

.. image:: ./laser_init_masking_updated.png
   :width: 800
   :alt: laser_init

**External fields:** For masking calculations, choose the parameters for **External fields** as Electric Field (**Type of fields**) and 
State Preparation (**Type of Experiment**). After that, proceed to **Design/Edit Laser**. For laser design, see :ref:`laser-design`.

Click on **Restart Option**, if applicable. Possible options include: increasing number of simulation steps.

.. note::

   All the input parameters will be collected to generate input if **Restart Option** is chosen. Make sure to change only the relevant parameters such as: Number of Steps.
   Any modification of External Fields (Laser Design Parameters) should be avoided.

**3.** To choose the masking parameters, see :ref:`masking`.

**Note:** To target a particular frequency, the absorption spectrum should be known. To compute spectrum, see :ref:`compute-spectrum`.

**4.** Run the RT-TDDFT simulation.

**5.** For post processing and visualization of time variation of dipole moment, see :ref:`dipole-moment`.
