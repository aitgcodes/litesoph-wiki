.. _avg-spectrum:

Averaged Spectrum
=================

.. note::

    Compatible Engines: GPAW, NWChem, Octopus

The Workflow for the calculations of simulating average spectrum is as follows:

**1.**  Start the workflow with ground state calculation. See :ref:`GS`.

**2.** After the ground state calculation is done, proceed to RT-TDDFT calculation. See Delta Kick Inputs under :ref:`rt-tddft`.

**3.** After RT-TDDFT calculation is done, proceed to compute spectrum. See :ref:`compute-spectrum`.

.. **4.** After the MO population is computed, for post processing and visualization, see :ref:`pp-visualization`.
