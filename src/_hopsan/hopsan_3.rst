**********************
Examples
**********************

==================================
Use an LLM to Control Software
==================================


The LLM generates configuration files, script commands, and codes in Python/Julia, C++/C, and domain-specific languages to control the operational flow.

* In a finite element solver, the main workflow is fixed, but many options are selected at each step.
* Unlike the fixed solver core, pre/post-processing workflows are dynamic and highly customizable.
  
=========================== ================================= ======================================================== =========================================
Type                               Flow Control                    Readability                                           Examples
=========================== ================================= ======================================================== =========================================
Configuration Files            Fixed (all steps)              Easy                                                     Palace (.msh and `.json <https://github.com/FENGSim/FENGSim/blob/main/starter/palace/examples/spheres/spheres.json>`_)
Script Commands                Fixed (selectable steps)       Simple                                                   `Gmsh <https://github.com/FENGSim/FENGSim/blob/main/starter/palace/examples/spheres/mesh/spheres.geo>`_, `LAMMPS/Kalmelo <https://github.com/FENGSim/FENGSim/blob/main/starter/karamelo/cutting/cutting_tl.mpm>`_, Ansys APDL
Python/Julia                   Dynamic (new flow)             Moderate coding capability                               Gmsh (`.jl <https://github.com/FENGSim/FENGSim/blob/main/starter/palace/examples/spheres/mesh/mesh.jl>`_ and .py)
C++/C                          Dynamic (new flow)             Advanced coding capability                               Gmsh, OCCT, VTK
Domain-Specific Languages      Dynamic (new flow)             Closed to human language                                 `FEniCS (UFL) <https://github.com/FEniCS/ufl/blob/main/demo/Heat.py>`_, KittyCAD/Zoo (KCL)
=========================== ================================= ======================================================== =========================================

For LLM-driven software flow control, generating Python or Julia scripts is the recommended approach. Input the following content into DeepSeek: ::

  Write a Julia script using Gmsh to create three spheres:
  one large sphere centered at (0, 0, 0) with radius 1,
  and two small spheres centered at (0.2, 0, 0) and (-0.2, 0, 0) respectively, each with radius 0.1.
  Then, subtract the two small spheres from the large sphere and generate the mesh.

The generated Julia script is available at this `link <https://github.com/FENGSim/FENGSim/blob/main/starter/DeepLearning/llm/test.jl>`_.

==================================
Deep Reinforcement Learning
==================================
