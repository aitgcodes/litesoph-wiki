.. _pump_probe:

Pump-probe
==========

.. note::
   Compatible Engines: GPAW, NWChem, Octopus

.. image:: ./pump_probe_workflow.png
   :width: 800
   :alt: pp_workflow

The Workflow for the Pump-Probe is as follows:

**1.** Start the workflow with ground state calculation. See :ref:`GS`

**2.** After the ground state calculation is done, proceed to RT-TDDFT calculation for spectrum calculation. See :ref:`delta-kick`.

**3.** After RT-TDDFT calculation is done, proceed to compute spectrum. See :ref:`compute-spectrum`

.. image:: ./laser_init_pp_updated.png
   :width: 800
   :alt: laser_init_pp

**External fields:** For Pump-Probe calculations, choose the parameters for **External fields** as Electric Field (**Type of fields**) and 
Pump-Probe (**Type of Experiment**). For each Pump-Probe input **Delay time list in fs** separated by space. After that, proceed to 
**Design/Edit Laser**. For laser design, see :ref:`laser-design`.

Click on **Restart Option**, if applicable. Posible options include: increasing number of simulation steps.

.. note::

   All the input parameters will be collected to generate input if **Restart Option** is chosen. Make sure to change **ONLY** the relevant parameters such as: Number of Steps.
   Any modification of External Fields (Laser Design Parameters) should be avoided. For Pump-Probe workflow, all RT-TDDFT simulations should run for same duration.

**4.** Run all the RT-TDDFT simulations. The first simulation uses only pump. After that, perform each simulation for each pump-probe pair,
consecutively.

**5.** For post processing and and visualization of TAS, see :ref:`compute-tas`.