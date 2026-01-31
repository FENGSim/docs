**********************
Examples
**********************

Multix has three couplers: one for large deformation, contact, and friction in fluid-solid/solid-solid problems; one for multiphase-multicomponent fluid; and one for assembly.

To run MultiX: ::

  cd FENGSim/toolkit/MultiX/build
  ./multix

========================
Extreme Mechanics
========================

-------------------------
ALE
-------------------------

.. image:: fig/ale.gif
   :height: 400px
   :alt: alternate text
   :align: center

=============================
Complex Assembled Structure
=============================

.. image:: fig/modal_mpc.gif
   :height: 200px
   :alt: alternate text
   :align: center

--------------------------
Electrodynamics
--------------------------

To run the example: ::

  cd FENGSim/starter/multix/
  ./run
  paraview data/vtk/magnetostatics_nonlinear_domain.vtk

.. image:: fig/static_mag.png
   :height: 200px
   :alt: alternate text
   :align: center
	   
===================================================
Multi-phase, Multi-component, Multi-scale Fluid
===================================================

We will re-implement the following MFEM topology optimization example using MultiX.

.. image:: fig/topo.gif
   :height: 200px
   :alt: alternate text
   :align: center
	   
