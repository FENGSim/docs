**********************
Examples
**********************

The LLM generates configuration files, script commands, and codes in Python/Julia, C++/C, and domain-specific languages to control the operational flow.

* In a finite element solver, the main workflow is fixed, but many options are selected at each step.
* Unlike the fixed solver core, pre/post-processing workflows are dynamic and highly customizable.

=========================== ================================= ======================================================== =========================================
Type                               Flow Control                    Readability                                           Examples
=========================== ================================= ======================================================== =========================================
Configuration Files            Fixed                            Easy                                                    Palace (.msh and .json)
Script Commands                Fixed with selectable steps      Simple                                                  Gmsh, LAMMPS/Kalmelo, Ansys APDL
Python/Julia                   Dynamic                          Moderate coding capability                              Gmsh (.jl and .py)
C++/C                          Dynamic                          Advanced coding capability                              Gmsh, OCCT, VTK
Domain-Specific Languages      Dynamic                          Closed to human language                                FEniCS (UFL), KittyCAD/Zoo (KCL)
=========================== ================================= ======================================================== =========================================

                        
