**********************
Pre/Post-Processing
**********************

Configuration files (base path:``FENGSim/starter/openfoam/plateHole/``):

* boundary conditions: ``0/D``, ``0/T``
* material properteis: ``constant/physicalProperties``
* geometry model: ``system/blockMeshDict``
* finite volume methods: ``system/fvSchemes``
* numerical linear algebra: ``system/fvSolution``
* solver control: ``system/controlDict``

To generate mesh data based on the geometry model: ::
  
  cd FENGSim/starter/openfoam/plateHole/
  source ../../../toolkit/CFD/openfoam/OpenFOAM-dev/etc/bashrc
  blockMesh
  
Mesh files (base path:``FENGSim/starter/openfoam/plateHole/constant/polyMesh``): 
 
* points (vertices): ``points``
* faces (both internal and boundary): ``faces``
* cell indices for all faces: ``owner``
* adjacent cell indices for internal faces: ``neighbour``
* boundary condition groups for boundary faces: ``boundary``
