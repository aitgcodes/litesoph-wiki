.. _MO:

=================================
Molecular Orbital (MO) Population
=================================

.. note::
   Compatible Engines: GPAW, NWChem, Octopus

.. image:: ./mo_landing_page.png
   :width: 800
   :alt: MO_Population

The Workflow for the calculations of MO population is as follows:

**1.**  Start the workflow with ground state calculation. See :ref:`GS`.

**2.** After the ground state calculation is done, proceed to RT-TDDFT calculation. See :ref:`rt-tddft`.

**3.** After RT-TDDFT calculation is done, proceed to compute spectrum. See :ref:`compute-spectrum`.

**4.** After spectrum is computed, proceed to compute MO population. See :ref:`compute-mo`.

.. _compute-mo:

Compute MO Population
---------------------

.. note::
   Compatible Engines: GPAW, NWChem, Octopus

Plots the Population Tracking for the chosen molecular system.

.. image:: ./Compute-MO.png
   :width: 800
   :alt: MO

The inputs required for population tracking are as follows:

**1. Number of occupied states(HOMO & below):** 

**2. Number of unoccupied states(LUMO & below):**

For plotting the change in population as a function of simulation time, two options are present as follows:

**3. All States:** For plotting the change in population for all available occupied and unoccupied states.

**4. Select the states:** Takes the input from **5 & 6** and plots the change in MO population accordingly.

**5. Number of occupied states(HOMO & below):** Input the number of occupied states to plot MO population change.

**6. Number of unoccupied states(LUMO & below):** Input the number of unoccupied states to plot MO population change.