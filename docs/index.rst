Welcome to the MuST Documentation!
===================================

.. image:: _static/MuST_logo.png
   :align: center
   :width: 200px
   :height: 200px

**MuST** is a research project supported by the National Science Foundation (NSF) to build 
a public *ab initio* electronic structure calculation software package with petascale 
and beyond computing capability, for first-principles studies of quantum phenomena in 
disordered materials.  

The MuST package is now (as of January 1, 2020) free to download on GitHub 
(`https://github.com/mstsuite <https://github.com/mstsuite>`_) under a BSD 3-clause license.

MuST is developed based on full-potential multiple scattering theory (also known as the 
Korringa-Kohn-Rostoker method) using the Green’s function approach. It builds upon decades 
of development of research codes led by Malcolm Stocks and his postdocs and students in 
the Theory Group of the Metals and Ceramics Division (later Materials Science and 
Technology Division) at Oak Ridge National Laboratory.  

The original research codes include:

- Korringa-Kohn-Rostoker Coherent Potential Approximation (KKR-CPA): A highly efficient 
  *ab initio* method for the study of random alloys.
- Locally Self-consistent Multiple Scattering (LSMS) method: A linear-scaling *ab initio* 
  code capable of treating extremely large disordered systems using the largest parallel 
  supercomputers available.

It was originally suggested by Mark Jarrell, and demonstrated by model calculations, that 
strong disorder and localization effects can be studied within the LSMS formalism using 
cluster embedding in an effective medium with the Typical Medium Dynamical Cluster 
Approximation (TMDCA), enabling a scalable approach for first-principles studies of quantum 
materials.

The ultimate goal of the MuST project is to provide a computational framework for investigating 
quantum phase transitions and electron localization in the presence of disorder in real 
materials, and to enable computational studies of local chemical correlation effects on 
magnetic structure, phase stability, and mechanical properties of solid-state materials 
with complex structures.

Contents
--------

.. toctree::
   :maxdepth: 2
   :caption: Contents

   installation
   usage
   theory
   input
   tutorials
   contrib
   acknowledge
   cite
