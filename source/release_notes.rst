=============
Release Notes
=============

V1.1 (Beta)
-----------

We are pleased to announce the release of LITESOPH version 1.1 (beta), which brings a range of enhancements and updates to improve your experience and productivity. Below are the key changes in this release:

Workflow Mode Enhancements:
^^^^^^^^^^^^^^^^^^^^^^^^^^^

* General Improvements: Integration of Pump-Probe across all engines, and resolution of cloning issues for all workflows, except for Pump-Probe.
* Engine Specific Updates:
    * GPAW: Fully operational (Previously, pump probe was not working properly)
    * OCTOPUS: All features now functional; previously, only "Compute Spectrum" was operational.

Task Mode Updates:
^^^^^^^^^^^^^^^^^^

* Enhanced post-processing capabilities including Compute Spectrum, Masking, KSD, and Molecular Orbital Population.
* Successful integration of all the engines in task mode.
* Automaticly updates to task dependencies to use the most recent related task.

User Interface and Usability Improvements:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* GUI Enhancements: Immediate updates in the OCTOPUS script upon GUI changes.
* Laser Design: Refined units on the multiple lasers page for precise design.
* Script Adjustments: Accurate reflection of box dimension changes in scripts.
* Stability Improvements: 'Proceed' button remains disabled until task completion.
* 'Proceed' button takes you back to the main page in task mode.

Documentation and Support:
^^^^^^^^^^^^^^^^^^^^^^^^^^

* Extensive updates to documentation for clearer guidance and support.

Future Updates:
^^^^^^^^^^^^^^^

* Under Development:
    * Development of cloning functionality for the Pump-Probe workflow.
    * Windows compatibility efforts to enhance accessibility.
    * Multiplicity option and Spin unrestricted calculation are currently disabled.
    * Implementing more features for NwChem.
    * Integration of TAS in task mode.
* Ongoing works:
    * Non-Adiabatic dynamics
    * QMMM tools for large scale systems
    * Plasmonicity Index calulator
    * Aggregate Hamiltonian mapper