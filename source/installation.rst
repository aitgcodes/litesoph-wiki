Installation Guide
==================

Before installing LITESOPH, the following modules or packages are required:

    **Essentials**
  
        * `python <https://www.python.org/>`_ 3.7.6 or later
        * `tkinter <https://docs.python.org/3/library/tkinter.html>`_
        * click_
        * numpy_
        * scipy_
        * matplotlib_
        * paramiko_
        * scp_
        * rsync_

    **Optional Requirements**
  
        **Visualization tools**: `VMD <https://www.ks.uiuc.edu/Research/vmd/>`_ , `vesta <https://jp-minerals.org/vesta/en/>`_ , `imagemagick <https://imagemagick.org/>`_ , `blender <https://www.blender.org/>`_
        **Compression tools**: lz4, zstd, lzop, gzip, bzip2, p7zip, xz, pigz, plzip, pbzip2, lbzip2



**Installation**
    Some very basic information. If you never used Litesoph before, maybe it is best to start here, otherwise you can just skip and go to the next sections.

**Python**
----------

    We currently only support python versions from  3.7 to 3.10, hence we recommend to check the python version installed in your machine

.. code-block:: console
 
    $ python --version

If the output is not in the given range, please reinstall the python with the following command:

.. code-block:: console
  
    $ sudo apt-get install python<version_number>

After the check, just run the following command in the main directory of litesoph source

.. code-block:: console

    $ python -m pip install .

*Note: Post-Installation, ensure that you add Python <version_number> to PATH to make the Python executable accessible from the command line.*

**Engines**
-----------

Running computational codes can often pose challenges, especially due to their heavy computational requirements, often necessitating access to High-Performance Computing (HPC) resources. However, not everyone has easy access to such resources. This is where Litesophs comes in to bridge the gap.

.. note::

    **However, Litesoph requires seperate installation of the the underlying engines if one wants to run the calculations locally. If you want to run on a remote server where litesoph has been already deployed, please skip to the final section about getting litesoph source code**  

We've compiled the instllation guide for all the three engines for ease of access :

**GPAW**
++++++++

GPAW relies on the Python library atomic simulation environment (ASE), so you need to install ASE first. GPAW itself is written mostly in the Python programming language, but there are also some C-code used for:
   
    **Requirements**
        * Python 3.8 or later
        * ASE
        * numpy
        * scipy
        * `LibXC <http://www.tddft.org/programs/libxc/>`_
        * C compiler
        * `BLAS <https://www.netlib.org/blas/>`_ library


**Installation Using sudo**
    If you are installing GPAW on you personal PC, or have the root access to the workstation, using sudo is the best way for installing GPAW

.. code-block:: console

    $ sudo apt-get install gpaw


**Insallation Using PIP**

    The simplest way to install GPAW is using pip and the GPAW package from the Python package index (PyPI):

.. code-block:: console

    $ python3 -m pip install gpaw
 
.. 

    *Note : If you install GPAW using this , you must also install the PAW dataset seperately*

    Install the datasets into the folder <dir> using this command:

.. code-block:: console

    $ gpaw install-data <dir>

..

**NWchem**
++++++++++

Aims to provide its users with computational chemistry tools that are scalable both in their ability to treat large scientific computational chemistry problems efficiently and in their use of available parallel computing resources from high-performance parallel supercomputers to conventional workstation clusters.

**Insallation**

To install Nwchem in your local machine,

**Using Sudo**

Input the following command in your terminal

.. code-block:: console

    $ sudo apt-get instal nwchem

**Source Compilation**

If you don't have access to root, you can install Nwchem using the source code.
The source code can be downloaded from `<https://nwchemgit.github.io/Download.html>`_ along with the compilation instructions

**Octopus**
+++++++++++

Octopus is a scientific program aimed at the ab initio virtual experimentation on a hopefully ever-increasing range of system types. Electrons are described quantum-mechanically within density-functional theory (DFT), in its time-dependent form (TDDFT) when doing simulations in time.

Proceeed to download any version of octopus from `<https://octopus-code.org/documentation/13/releases/>`_ 

We recommend using spack for installation.

**Installation**

    **Using spack**
  
    * Clone the github repository of SPACK

.. code-block:: console

    $ git clone https://github.com/spack/spack.git --depth 1
..

    * Change directory 
  
.. code-block:: console

    $ cd spack/bin
..

    * Run 
  
.. code-block:: console

    $ spack install octopus
..

    * Sit back and let octopus compile.

    * After the build, move final build to path variable. (Directory of build would be printed after the build)

.. code-block:: console

    $ mv path/to/octopus ~/octopus
..

    * Now add octopus to path like `this <https://stackoverflow.com/a/14638025>`_

    **Installation using source**

    Besides the compiler, you will also need:

    * make: most computers have it installed, otherwise just grab and install the GNU make.

    * cpp: The C preprocessor is heavily used in Octopus to preprocess Fortran code. It is used for both C (from the CPP variable) and Fortran (FCCPP). GNU cpp is the most convenient but others may work too. For more info, see Preprocessors.

    * Libxc: The library of exchange and correlation functionals. It used to be a part of Octopus, but since version 4.0.0 it is a standalone library and needs to be installed independently. For more information, see the libxc page. Octopus 4.0.0 and 4.0.1 require version 1.1.0 (not 1.2.0 or 1.0.0). Octopus 4.1.2 requires version 2.0.x or 2.1.x, and won’t compile with 2.2.x. (Due to bugfixes from libxc version 2.0 to 2.1, there will be small discrepancies in the testsuite for functionals/03-xc.gga_x_pbea.inp and periodic_systems/07-tb09.test). Octopus 5.0.0 supports libxc versions 2.0.x, 2.1.x and 2.2.x. Please note: The Libxc testsuite prior to 2.1 will report some errors in most cases. This is not something to worry about.

    * FFTW: We have relied on this great library to perform Fast Fourier Transforms (FFTs). You may grab it from the `FFTW site <https://www.fftw.org/>`_. You require FFTW version 3.

    * LAPACK/BLAS: Our policy is to rely on these two libraries as much as possible on these libraries for linear-algebra operations. If you are running Linux, there is a fair chance they are already installed in your system. The same goes to the more heavy-weight machines (alphas, IBMs, SGIs, etc.). Otherwise, just grab the source from netlib site.

    * GSL: Finally someone had the nice idea of making a public scientific library! GSL still needs to grow, but it is already quite useful and impressive. Octopus uses splines, complex numbers, special functions, etc. from GSL, so it is a must! If you don’t have it already installed in your system, you can obtain GSL from the GSL site. You will need version 1.9 or higher. Version 4.0 of Octopus (and earlier) can only use GSL 1.14 (and earlier). A few tests will fail if you use GSL 1.15 or later. Version 5.0.0 of Octopus (and earlier) can only use GSL 1.16 or earlier, due to a bug in our configure script.

    * Perl: During the build process Octopus runs several scripts in this language. It’s normally available in every modern Unix system.

    To build octopus from source, visit `octopus-code.org <https://octopus-code.org/documentation/13/manual/installation/building_from_scratch/>`_


Getting the source code of LITESOPH
===================================

You can get the source from a zip-file or from Git:

**zip-file:** You can get the source as a zip-file for the latest stable release (:download:`litesoph-main.zip <https://github.com/LITESOPH/litesoph/archive/refs/heads/main.zip>`)

**git clone:** Alternatively, you can get the source for the latest stable release from github

.. code-block:: console

    $ git clone -b main https://github.com/aitgcodes/litesoph.git

Install it using the following command

.. code-block:: console

    $ pip install <path-to-litesoph>

Configuration
=============

In software development, configuration files play a crucial role in customizing the behavior of applications or modules. 
A configuration file is a plain text file that contains parameters and settings that define how a program should operate. These settings can range from file paths and connection strings to more complex configurations like feature toggles or system settings.

Understanding the Config.py File:

Within our module, we utilize a config.py file to manage various settings and paths crucial for its functionality. Let's delve into each section of this configuration file:

**1**. [path]:

This section deals with defining paths related to the litesoph's operation. Specifically, it contains keys such as lsproject and lsroot. These keys represent important directories or locations within the project structure. For instance, lsproject might denote the path to a specific project associated with the litesoph, while lsroot indicates the installation path of the litesoph itself.

**2**. [visualization_tools]:

In this section, we specify paths to visualization tools essential for the litesoph's functionality. Keys like vmd and vesta represent paths to tools such as VMD (Visual Molecular Dynamics) and VESTA, respectively. These tools are crucial for visualizing molecular structures and conducting analyses, making their paths vital for seamless integration with  litesoph.

**3**. [engine]:

The [engine] section focuses on defining paths related to computational engines utilized by Litesoph. Keys like gpaw, nwchem, and octopus represent paths to binaries or executables of computational engines like GPAW, NWChem, and Octopus, respectively. These engines play a pivotal role in performing computations and simulations within litesoph.

**4**. [programs]:

This section is dedicated to specifying paths related to external programs or dependencies required by the litesoph. The key python typically denotes the path to the Python interpreter. Ensuring correct paths for such programs is essential for the proper execution of litesoph's functionalities, especially when invoking external processes or scripts.

**5**. [mpi]:

Lastly, the [mpi] section deals with paths relevant to Message Passing Interface (MPI) implementations, which are commonly used for parallel computing tasks. Keys like mpirun, gpaw_mpi, octopus_mpi, and nwchem_mpi represent paths to MPI-related executables or configurations. These paths are crucial for enabling parallelism and distributed computing capabilities within the litesoph.


To create :ref:`lsconfig file <lsconfig>`:

    .. code-block:: console

        $ litesoph config -c
  
To edit lsconfig file:
    .. code-block:: console

        $ litesoph config -e

.. _lsconfig:

Example lsconfig file
===============================
Here is an example of lsconfig file.

.. code-block:: console

    [path]
    lsproject = <litesoph project path>
    lsroot = <installation path of litesoph>

    [visualization_tools]
    vmd = <path to vmd || e.g. /usr/local/bin/vmd ||can be obtained using :command:`which vmd` >
    vesta = <path to vesta || e.g. /usr/local/bin/vesta||can be obtained using :command:`which vesta` >

    [engine]
    gpaw = <path of gpaw||can be obtained using :command:`which gpaw`> 
    nwchem =<binary path of nwchem||can be obtained using :command:`which nwchem`>
    octopus =<binary path of octopus ||can be obtained using :command:`which octopus`>

    [programs]
    python = <path to python||can be obtained using :command:`which python`>

    [mpi]
    mpirun = <path to mpirun || e.g. /usr/local/bin/mpirun ||can be obtained using :command:`which mpirun`>
    gpaw_mpi = <path to mpirun through which gpaw is compiled|| e.g. /usr/local/bin/mpirun>
    octopus_mpi =<path to mpirun through which octopus is compiled|| e.g. /usr/local/bin/mpirun>
    nwchem_mpi =<path to mpirun through which nwchem is compiled|| e.g. /usr/local/bin/mpirun>

.. _usage:

Usage
=====

To start gui application, run:

.. code-block:: console

    $ litesoph gui


.. _NumPy: http://docs.scipy.org/doc/numpy/reference/
.. _SciPy: http://docs.scipy.org/doc/scipy/reference/
.. _click : https://pypi.org/project/click/
.. _Matplotlib : https://pypi.org/project/matplotlib/
.. _Paramiko : https://pypi.org/project/paramiko/
.. _scp : https://www.ssh.com/academy/ssh/scp
.. _Rsync : https://rsync.samba.org/