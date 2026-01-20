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
  
Mesh data (base path:``FENGSim/starter/openfoam/plateHole/constant/polyMesh``): 
  
* points: ``points``
* faces: ``faces``
* owner: ``owner``
* neighbour for inner faces: ``neighbour``
* boundary group for boundary faces: ``boundary``

和有限元网格有所区别，points是网格所有顶点，faces是网格所有单元面，单元面按照先内部单元面和后边界单元面排序，边界单元面按照几何模型面排序。owner定义了每个单元面归属的单元，如果是内部单元面，除了归属单元，还有相邻单元，相邻单元编号保存在neighbour中，这里需要注意的是neighbour对应了faces中的内部单元面，faces中内部单元面排在边界单元面前面。boundary是所有边界单元面，同一几何模型面上的边界单元面集合是按照faces中单元面编号起始位置以及个数定义。
