**********************
Examples
**********************

MultiX features four couplers: one for large deformation, contact, and damage in fluid–solid and solid–solid problems; one for multiphase, multicomponent heat–fluid–solid interactions; one for assembly; and one for multiscale material properties.

To run MultiX: ::

  cd FENGSim/toolkit/MultiX/build
  ./multix

========================
Extreme Mechanics
========================

-------------------------
ALE
-------------------------

.. image:: fig/rivert.gif
   :width: 100%
   :alt: alternate text
   :align: center

.. image:: fig/pipe.gif
   :width: 100%
   :alt: alternate text
   :align: center
	   
.. image:: fig/ale.gif
   :width: 100%
   :alt: alternate text
   :align: center

-------------------------
MPM
-------------------------

.. image:: fig/mpm.gif
   :width: 100%
   :alt: alternate text
   :align: center

.. image:: fig/mpm2.gif
   :width: 100%
   :alt: alternate text
   :align: center

.. image:: fig/damage.gif
   :width: 100%
   :alt: alternate text
   :align: center

=============================
Complex Assembled Structure
=============================

------------------------------
Assembly and Modal Analysis
------------------------------

.. image:: fig/modal_mpc.gif
   :width: 50%
   :alt: alternate text
   :align: center

|
|

.. image:: fig/truss_tri.png
   :width: 50%
   :alt: alternate text
   :align: center

---------------------------------------------------------
Prestress Induced by Electrodynamic and Thermal Effects
---------------------------------------------------------

To run the example: ::

  cd FENGSim/starter/multix/
  ./run
  paraview data/vtk/magnetostatics_nonlinear_domain.vtk

.. image:: fig/static_mag.png
   :width: 50%
   :alt: alternate text
   :align: center

--------------------------
Mutibody
--------------------------

.. image:: fig/2dof.png
   :width: 50%
   :alt: alternate text
   :align: center
	   
.. image:: fig/cartpole.png
   :width: 50%
   :alt: alternate text
   :align: center

--------------------------
Reinforcement Learning
--------------------------

.. image:: fig/dnn.png
   :width: 50%
   :alt: alternate text
   :align: center

|
|

.. image:: fig/cart_pole.gif
   :width: 100%
   :alt: alternate text
   :align: center
	   
==============================================================
Multi-Phase, Multi-Component Thermo-Hydro-Mechanical Systems
==============================================================

--------------------------
Multi-Phase
--------------------------

.. image:: fig/allencahn.gif
   :width: 50%
   :alt: alternate text
   :align: center

--------------------------
Multi-Component
--------------------------

.. image:: fig/AkzoNobel.png
   :width: 50%
   :alt: alternate text
   :align: center

------------------------------------------
Imcompressible Navier-Stokes equations
------------------------------------------

.. image:: fig/navierstokes.png
   :width: 50%
   :alt: alternate text
   :align: center

------------------------------------------
Compressible Navier-Stokes equations
------------------------------------------
	   
======================================================================================================================================================
Multiscale Modeling of Multifunctional Material Properties
======================================================================================================================================================

--------------------------
Mechanical Performance
--------------------------


--------------------------
Electromagnetic Response
--------------------------


-----------------------------
Radiation Energy Deposition
-----------------------------
