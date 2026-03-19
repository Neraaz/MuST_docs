MuST Project Overview
====================

The starting point of the MuST package is the integration of two research codes: 
``LSMS`` (formerly LSMS3) and ``MST`` (formerly MST2), both originally based on the
legacy LSMS-1 code developed in the mid-1990s at Oak Ridge National Laboratory.

LSMS
----

The ``LSMS`` code, maintained by Markus Eisenbach, is primarily written in C++. It 
consists of muffin-tin LSMS with an interface for Monte-Carlo simulation drivers. 
``LSMS`` is one of the baseline benchmark codes for DOE COREL systems and has been 
selected as a CAAR project for exascale computing on the Frontier system. It demonstrates 
nearly ideal linear scaling with 96% parallel efficiency on the Titan machine at ORNL.

MST
---

The ``MST`` code, maintained by Yang Wang, is mainly written in Fortran 90. It focuses 
on physics capabilities and serves as a platform for implementing and testing full-potential 
multiple scattering theory and its numerical algorithms. It includes LSMS, KKR, and KKR-CPA codes 
and supports:

1. Muffin-tin and full-potential calculations  
2. Non-relativistic, scalar-relativistic, and fully-relativistic approaches  
3. Non-spin-polarized, spin-polarized, and spin-canted *ab initio* electronic structure calculations  

KUBO
----

The ``KUBO`` code, maintained by Vishnu Raghuraman, is mainly written in Fortran 90. It 
implements the Kubo-Greenwood formula within the KKR-CPA framework and calculates the 
electrical conductivity of random alloys.

Project Team
------------

The MuST project is a collaborative effort requiring expertise from condensed matter 
physics, high-performance computing, computational materials science, applied mathematics, 
and software engineering communities. Current participants include:

- Chioncel, Liviu (Institute of Physics, Augsburg University, Germany)  
- Eisenbach, Markus (Center for Computational Sciences, Oak Ridge National Laboratory, USA)  
- Raghuraman, Vishnu (Department of Physics, Carnegie Mellon University, USA)  
- Tam, Ka-ming (Department of Physics, Louisiana State University, USA)  
- Terletska, Hanna (Department of Physics, Middle Tennessee State University, USA)  
- Wang, Yang (Pittsburgh Supercomputing Center, Carnegie Mellon University, USA)  
- Widom, Michael (Department of Physics, Carnegie Mellon University, USA)  
- Zhang, Yi (Kavli Institute for Theoretical Sciences, Beijing 100190, China)  
