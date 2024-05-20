.. _avg-spectrum:

Averaged Spectrum
=================

.. note::

    Compatible Engines: GPAW, NWChem, Octopus

The Workflow for the calculations of simulating average spectrum is as follows:

Averaged spectrum of a molecule workflow can be modeled as:

::
  
      Block-1                  Block-2                  Block-3                  Block-4
  |---------------|      |-----------------|      |--------------------|    |----------------|
  |               |      |                 |      |                    |    |                |
  | 1. ground     |----> |  2. RT-TDDFT- x |----->| 5.compute-spectra-x|--->| 8. compute     | 
  |    state      |      |  3. RT-TDDFT- y |      | 6.compute-spectra-y|    | average spectra|
  |---------------|      |  4. RT-TDDFT- z |      | 7.compute-spectra-z|    |----------------|
                         |-----------------|      |--------------------|  

One needs to compute the RT-TDDFT for three different polarization,generate the crossection vectors for the same and then Litesoph will generate the averaged spectrum

**1.**  Start the workflow with ground state calculation. See :ref:`GS`.

**2.** After the ground state calculation is done, proceed to RT-TDDFT calculation. See Delta Kick Inputs under :ref:`rt-tddft`.

    | **1** Compute the RT-TDDFT in the X polarization direction, click Proceed.
    | **2** Compute the RT-TDDFT in the Y polarization direction, click Proceed.
    | **3** Compute the RT-TDDFT in the Z polarization direction, click Proceed.

**3.** After RT-TDDFT calculation is done, proceed to compute spectrum. See :ref:`compute-spectrum`.

    | **1** Select the range for spectrum generation,then either submit local or network depending where litesoph has been deployed for the X polarization and click proceed
    | **2** Select the same range and submit for Y polarization and click proceed.
    | **3** Select the same range and submit for Z polarization and click proceed.

**4.** After the crossection vector has been generated for all three polarization, hit submit and then proceed to plot the average spectrum.

.. **4.** After the MO population is computed, for post processing and visualization, see :ref:`pp-visualization`.
