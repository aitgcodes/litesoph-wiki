.. _rt-tddft:

RT-TDDFT
==========
The RT-TDDFT calculations can be done as follows:

.. _delta-kick:

Delta kick Inputs
###################

.. image:: ./Delta-kick.png
   :width: 800
   :alt: Spectrum

**1. Laser Strength in a.u (E0):** Strength of the delta kick electric field to be applied. This excites all the electronic degrees of freedom at the begining.

**2. Time steps (in attosecond):** Time steps for the dynamics of the Kohn-Sham euations.

**3. Number of Steps:** Total number of steps to be run for the dynamics. Total time is (Number of Steps*time steps)

**4. Frequency of data collection:** Number of times the data will be printed. Vale `1` indicates that data will be collected at each time steps. 

**5. Polarisation Direction:** Direction of the applied external electric field.

Properties
##########

.. image:: ./properties.png
   :width: 800
   :alt: Spectrum

**1. Observables to extract:** Choose the operation to be performed. For Spectrum Calculation
choose **Absorption Spectrum**. For KSD calculation choose **Absorption Spectrum** and 
**Kohn Sham Decomposition**. For MO population calculation
choose **Absorption Spectrum**, **Kohn Sham Decomposition** and **Population Correlation**.