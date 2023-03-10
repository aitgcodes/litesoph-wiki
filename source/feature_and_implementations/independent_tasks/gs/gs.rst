.. _GS:

Ground State
============
For Ground State Calculations, there are three windows for input parameters.

**Basic**

The basic input parameters for ground state DFT Calculations are as follows:

.. image:: ./basic.png
   :width: 800
   :alt: Spectrum

**1. Exchange correlation:** An exchange-correlation functional for all atoms.

**2 & 3: Basis Type and Basis Sets:** The basis type for the expansion of the wavefunction. The available options are lcao (linear combination of atomic orbitals), grid-based method, fd (finite difference method), pw (plane wave) and gaussian. For **lcao** and **gaussian**, the basis sets can be chosen accordingly. The gui chooses the suitable engine depending on the input functional and basis types.

**4. Spin polarization:** Default is set to unpolarized. If set to polarized, spin-polarized calculations is performed.

The input parameters for the simulation box are as follows:

**5. Grid Spacing (in angstrom):** Mesh grid for fd in real-space

**6. Box Shape:** Shape of the simulation box. Available options are parallelepiped, sphere, cylinder and minimum.

**7. Vacuum (in angstrom):** Cut-off distance for including vacuum.
Simulation box will be chosen (automatically) such that the minimum distance between any atom and the edge of the box is the cut off.

If the **Enter Box Dimension** is checked, length of the simulation box (in angstrom) along all the three directions can be entered.

**Convergence**

.. image:: ./convergence.png
   :width: 800
   :alt: Spectrum

Parameters related to the convergnece of electronic energies:

**1. Maximum Iteration:** Maximum number of iterations in a scf cycle.

**2. Energy Convergence (in au):** Convergence threshold in au for electronic energy.

**3. Density Convergence (in au):** Convergence threshold in au for charge density.

**4. Smearing:** Gaussian spreading for brillouin zone integration .

**5. Mixing:** Mixing factor for self consistency.

**Advanced**

.. image:: ./advanced.png
   :width: 800
   :alt: Spectrum

**1. Number of Extra States:** Number of unoccupied states

.. * :ref:`Proceed <rt-tddft>` : Open the Workflow for RT-TDDFT Calculations.