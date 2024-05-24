About LITESOPH
==============

The LITESOPH project is aimed at developing a comprehensive toolkit to launch, monitor, manage and analyze 
large-scale simulations of photo-induced phenomena in a high-performance computing (HPC) environment. 
It is designed to serve the needs of computational researchers interested in solar energy conversion 
applications (photovoltaics, water-splitting catalysts, solar fuels, etc.), optoelectronic materials, 
photochemistry and photobiology. The toolkit consists of several Python-based layers driven by popular 
and open-source TDDFT codes like OCTOPUS, GPAW and NWChem.

The project is currently funded by `MeitY <https://www.meity.gov.in/>`_ through the National Supercomputing Mission's "Applications for Materials and Computational Chemistry" initiative.

Engines Interfaced with LITESOPH
=================================

There are currently three engines implemented in LITESOPH. The details of these engines with their Installation Instruction are given below:

`GPAW <https://wiki.fysik.dtu.dk/gpaw/index.html>`_    (versions >=22 and <24 are recommended) is a density-functional theory (DFT) `python <https://www.python.org/>`_ code based on the projector-augmented wave (`PAW <https://wiki.fysik.dtu.dk/gpaw/documentation/introduction_to_paw.html#introduction-to-paw>`_) method and the atomic simulation environment (`ASE <https://wiki.fysik.dtu.dk/ase/>`_). The wave functions can be described with:

* Plane-waves (`pw <https://wiki.fysik.dtu.dk/gpaw/documentation/basic.html#manual-mode>`_)

* Real-space uniform grids, multigrid methods and the finite-difference approximation (`fd <https://wiki.fysik.dtu.dk/gpaw/documentation/basic.html#manual-stencils>`_)

* Atom-centered basis-functions (`lcao <https://wiki.fysik.dtu.dk/gpaw/documentation/lcao/lcao.html#lcao>`_)

    Note: Before installing this engine, see `GPAW <https://wiki.fysik.dtu.dk/gpaw/index.html>`_  and its installation instruction  for details.

`Octopus <https://octopus-code.org/wiki/Main_Page>`_ (version 11.4) is a scientific program aimed at the ab initio virtual experimentation on a hopefully ever-increasing range of system types. Electrons are described quantum-mechanically within density-functional theory (DFT), in its time-dependent form (TDDFT) when doing simulations in time. Nuclei are described classically as point particles. Electron-nucleus interaction is described within the pseudopotential approximation.

For optimal execution performance, Octopus is parallelized using MPI and OpenMP and can scale to tens of thousands of processors. It also has support for graphical processing units (GPUs) through OpenCL and CUDA.

Octopus is free software, released under the GPL license, so you are free to download it, use it and modify it.
Before installing this engine, see `Octopus <https://octopus-code.org/wiki/Main_Page>`_  and its Installation Instruction for details.

`NWChem <https://nwchemgit.github.io/>`_ (version 7.0.0 or later) aims to provide its users with computational chemistry tools that are scalable both in their ability to treat large scientific computational chemistry problems efficiently and in their use of available parallel computing resources from high-performance parallel supercomputers to conventional workstation clusters. NWChem software can handle:

* Biomolecules, nanostructures, and solid-state
* From quantum to classical, and all combinations
* Ground and excited-states
* Gaussian basis functions or plane-waves
* Scaling from one to thousands of processors
* Properties and relativistic effects

Before installing this engine, see `NWChem <https://nwchemgit.github.io/>`_  and its installation instruction for details.