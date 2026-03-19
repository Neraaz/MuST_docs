============================================
Input Parameters
============================================

This document provides the exhaustive list of input parameters for the LSMS code. It includes default values, allowed ranges, and technical logic extracted from the source input file.

.. contents:: Table of Contents
   :depth: 2

General Execution & File I/O
============================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Current File Path**
     - ``./``
     - Directory for I/O operations.
   * - **Current File Name**
     - ``i_lsms_D``
     - Primary input filename.
   * - **Info Table File Name**
     - ``info_table_D``
     - Filename for the system info table.
   * - **No. Iterations (> 0)**
     - ``60``
     - Total number of Self-Consistent Field (SCF) iterations.
   * - **Method of SCF Calculation**
     - ``2``
     - -2: Single Site; -1: ScreenKKR-LSMS; 0: Screen-KKR; 1: LSMS; 2: KKR; 3: KKR-CPA
   * - **Stop-at Routine Name**
     - ``main``
     - The routine where calculation terminates (useful for debugging).
   * - **Text Identification**
     - ``D``
     - Job/Run identifier.
   * - **Alloy System Description**
     - ``D, Default...``
     - Text description of the simulation cell.
   * - **Atomic Position File Name**
     - ``position.dat``
     - File containing the Cartesian coordinates of atoms.
   * - **No. Atoms in System (> 0)**
     - ``1``
     - Total number of atoms in the unit cell.

Output & Verbosity Control
==========================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Output to Screen (y/n)**
     - ``n``
     - Toggle standard output.
   * - **Output Level (>= -1)**
     - ``0``
     - Level of detail in log files.
   * - **Output Proc. ID (>= -1)**
     - ``0``
     - -1: All CPUs write; >=0: Specific processor IDs for unit 6.
   * - **Output Atom ID (>= -1)**
     - ``0``
     - -1: All atoms; 0: Local atoms; >=1: Specific global atom indexes.
   * - **No. Iter for Each Pot. Write**
     - ``5``
     - Frequency of potential file updates.
   * - **No. Iter for Each Movie**
     - ``0``
     - 0: No movie; >=1: Write movie every N iterations.

Electronic Structure & LDA Logic
================================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Potential Type (>= 0)**
     - ``3``
     - 0:MT; 1:ASA; 2:MT-ASA; 3:Full; 4:MT-Test; 5:Empty Lattice; 6:Mathieu
   * - **Exch-Corr. LDA Type (>= 0)**
     - ``0``
     - 0:Barth-Hedin; 1:VWN; 2:PZ; 3:PW-GGA; 4:PBE. Supports LibXC strings.
   * - **LDA Improvement Scheme**
     - ``0``
     - 0:None; 1:LDA+U; 2:LDA+SIC; 3:LDA+DFMT
   * - **Val. Electron Rel (>= 0)**
     - ``0``
     - 0:Non-rel; 1:Scalar-rel; 2:Full-rel
   * - **Core Electron Rel (>= 0)**
     - ``0``
     - 0:Non-rel; 1:Full-rel
   * - **Frozen-Core Calculation**
     - ``0``
     - Iteration index to start freezing the core.
   * - **Frozen-Core File Name**
     - ``' '``
     - Path to frozen core data.
   * - **Charge Symmetry (>=0)**
     - ``1``
     - 0: No symmetry; 1: Imposed from spherical scattering.
   * - **Additional Electrons**
     - ``0.0``
     - Manual charge adjustment for testing.

Energy Contour Integration
==========================



.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Contour Type (>= 0)**
     - ``0``
     - 0:Semi-circle; 1:Rectangle Box; 2:Horizontal Line; 3:Vertical Line
   * - **Number of Contours (> 0)**
     - ``1``
     - Number of energy contours to use.
   * - **Energy Grid Type (>= 0)**
     - ``1``
     - 0:Equal; 1:Gaussian; 2:Log; 3:Nicholson
   * - **No. Energy Grids**
     - ``30``
     - Points along the complex contour.
   * - **No. Extra Energy Points**
     - ``5``
     - Points added for refinement.
   * - **Real Axis Bottom/Top**
     - ``-0.40 / 0.00``
     - erbot and ertop values.
   * - **Imag Axis Bottom/Top**
     - ``0.001 / 1.000``
     - eibot and eitop values.
   * - **Read E-mesh from emeshs.inp**
     - ``0``
     - 1: Override all settings with external mesh file.
   * - **Imaginary energy shift**
     - ``0.001``
     - Small shift for pole avoidance.

Single Site & K-Space Solvers
=============================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Single Site Solver (>= 0)**
     - ``2``
     - 0:Spherical Schrodinger; 1:Spherical Dirac; 2:Full Schro; 3:Full Dirac
   * - **Single Site Solution Method**
     - ``2``
     - Truncation logic (-1 to 2) for volume/surface integration.
   * - **K-space Solver Method**
     - ``0``
     - 0:SuperLU; 1:SuperLU direct check; 2:Direct (Serial)
   * - **T-matrix inversion (>= 0)**
     - ``2``
     - Method for calculating the T-matrix.
   * - **M-matrix inversion (>= 0)**
     - ``10``
     - 0:LU method; 2:QMR method.
   * - **Lloyd correction**
     - ``0``
     - 0:Off; 1:On. Corrects density of states.
   * - **Pole Search Step**
     - ``0.010``
     - Resolution for identifying resonance poles.

Mixing & Convergence Tolerances
===============================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Mixing algorithm**
     - ``2``
     - 0:Simple; 1:DGA; 2:Broyden
   * - **Mixing quantity type**
     - ``1``
     - 0:Charge; 1:Potential
   * - **Energy (Ryd) Tol (> 0)**
     - ``0.000001``
     - Convergence threshold for total energy.
   * - **Potential Tol (> 0)**
     - ``0.0000001``
     - Convergence threshold for potential.
   * - **Fermi Energy Tol (> 0)**
     - ``0.0000001``
     - Tolerance for $E_f$ search.
   * - **Default Rho Mix Param.**
     - ``0.1000``
     - Mixing parameter for density.
   * - **Default Pot Mix Param.**
     - ``0.1000``
     - Mixing parameter for potential.
   * - **Negative charge tol**
     - ``0.00001``
     - Threshold for setting $\rho(r) = 0$.

Spin Dynamics & Magnetism
=========================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Spin Index Param (>= 1)**
     - ``1``
     - 1:No Spin; 2:Spin-polarized; 3:Spin-canted
   * - **Moment Direction File**
     - ``Evec_input.dat``
     - File containing magnetic moment vectors.
   * - **Calculate J_ij (y/n)**
     - ``n``
     - Toggle calculation of exchange interactions.
   * - **Default Moment Direction**
     - ``0 0 1``
     - Default vector for magnetic moments.
   * - **No. Spin-dyn. Steps**
     - ``1``
     - Number of time steps for spin dynamics.

Lmax Cutoffs & Radial Grids
===========================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Default Lmax-T matrix**
     - ``4``
     - Controls KKR matrix size ($L_{max}$).
   * - **Default Lmax-Wave Func**
     - ``4``
     - Wave function expansion cutoff.
   * - **Default Lmax-Potential**
     - ``8``
     - Potential expansion (typically $2 \times L_{max,T}$).
   * - **Default Lmax-Charge Den**
     - ``8``
     - Charge density expansion cutoff.
   * - **Default No. Rad Points**
     - ``1001``
     - ``ndivin``: Points inside muffin-tin.
   * - **Radial Exponential Step**
     - ``0.01``
     - Recommended range: 0.005 - 0.02.

Local Interaction Zone (LIZ) & CPA
==================================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Default LIZ # Neighbors**
     - ``350``
     - Max neighbors for a local site.
   * - **Default LIZ # NN Shells**
     - ``16``
     - Number of nearest neighbor shells.
   * - **Default LIZ Cutoff**
     - ``25.0``
     - Radius for the local interaction zone.
   * - **Max Effective Medium Iter**
     - ``40``
     - CPA iterations (Set 0 for ATA).
   * - **Medium Mixing Scheme**
     - ``2``
     - 0:Simple; 1:Anderson; 2:Broyden; 3:Messina-Anderson
   * - **Effective Medium T-mat Tol**
     - ``1E-07``
     - Tolerance for CPA T-matrix convergence.

Advanced Calculation Modules
============================

Superconductivity (Tc)
----------------------
* **Calculate Superconducting Tc**: Default ``0`` (1 for Yes).
* **mu* (e-e interaction constant)**: Default ``0``. 0:Bennemann-Garland; 1:Modified BG.
* **Debye Temperature (K)**: Default ``0`` (Internal database).
* **Phonon Averages**: Parameters for $\langle\omega\rangle$, $\langle\omega^2\rangle$, and Mass $\times \langle\omega^2\rangle$.

DFT + DMFT / Local Orbitals
---------------------------
* **Perform DFT+DMFT Calculation**: Default ``0``.
* **Default Local Orbital Labels**: ``d`` (Options: s, p, d, f).
* **Orbital Energies**: Separate keys for s, p, d, f local energies in Rydbergs.

Visualization & Movie
=====================

.. list-table::
   :widths: 35 15 50
   :header-rows: 1

   * - Parameter Key
     - Default
     - Description / Options
   * - **Visual Grid Type**
     - ``3``
     - 1:Line (1D); 2:Plane (2D); 3:Region (3D).
   * - **Visual Grid Points**
     - ``10 10 10``
     - Divisions along visual vectors.
   * - **Output Density Format**
     - ``2``
     - 0:xyz; 1:vtk (ParaView); 2:xsf (VESTA).
   * - **Uniform Grid Parameters**
     - ``64 64 64``
     - Grid for Poisson solver (must be power of 2).


Atomic Position File (position.dat)
===================================

The ``position.dat`` file defines the structural framework and chemical composition of the system.

Structure Definition
--------------------
* **Lattice Constant**: The first line defines the global scaling factor (e.g., 5.53).
* **Bravais Vectors**: Three lines defining the primitive lattice vectors.
* **Site Position**: Cartesian coordinates (x, y, z) for each atom in the cell.

Crystal Structure: CuZn (BCC)
--------------------------------------

.. code-block:: text

    5.53
    # Bravais lattice
        1.00000000000    0.00000000000    0.0000000000
        0.00000000000    1.00000000000    0.0000000000
        0.00000000000    0.00000000000    1.0000000000
    # Atomic position
    Cu  0.00000000000    0.00000000000    0.00000000000
    Zn  0.50000000000    0.50000000000    0.50000000000

Crystal Structure: Cu-Zn Random Alloy (FCC, CPA)
---------------------------------------------------

.. code-block:: text

    5.53
    # Bravais lattice
         0.50000000000    0.50000000000   -0.50000000000
         0.50000000000   -0.50000000000    0.50000000000
        -0.50000000000    0.50000000000    0.50000000000
    # Atomic position
    CPA  0.00000000000    0.00000000000    0.00000000000  Cu  0.50000  Zn  0.50000
    
Notes
-----
- For random alloy calculations, use 'CPA' as the virtual atom name.
- Coordinates are Cartesian (x, y, z) of the virtual atom.
- The atomic species and their site concentrations follow the coordinates.
