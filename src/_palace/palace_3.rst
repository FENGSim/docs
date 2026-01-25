**********************
Examples
**********************

* Examples Path: ``FENGSim/toolkit/CEM/palace/examples/``
* Documentation: For more details, see `<https://awslabs.github.io/palace/dev/examples/examples/>`_.

     
======================
Electrostatics
======================

Configurations: 
  
  * ZeroCharge, homogeneous Neumann b.c.
  * Ground, homogeneous Dirichlet b.c.
  * Terminal, constant Dirichlet b.c.


To run the example for the capacitance matrix of two spheres: ::
  
  cd FENGSim/starter/palace/examples/spheres
  ./../../../../toolkit/CEM/palace/palace/build/palace-x86_64.bin spheres.json
  paraview postpro/paraview/electrostatic/electrostatic.pvd

.. image:: fig/palace_1.png
   :scale: 50 %
   :alt: alternate text
   :align: center

======================
Magnetostatics
======================

Configurations: 
  
  * PEC, homogeneous Dirichlet b.c.
  * PMC, homogeneous Neumann b.c.
  * SurfaceCurrent, source term
  * nonlinear
  
From .xml to .json: ::

  cd FENGSim/starter/palace/examples/static_mag
  python3 xml2json.py
  input .xml: configure
  .xml is configure.xml
  input .msh: mag
  .msh is mesh/mag.msh

To run the magnetostatic example: ::
  
  cd FENGSim/starter/palace/examples/static_mag
  ./../../../../toolkit/CEM/palace/palace/build/palace-x86_64.bin mag2.json
  paraview postpro/paraview/magnetostatic/magnetostatic.pvd
  
+------------------------------------+------------------------------------+
| .. image:: fig/mag_2.png           | .. image:: fig/mag_1.png           |
|    :width: 350px                   |    :width: 350px                   |
+------------------------------------+------------------------------------+


