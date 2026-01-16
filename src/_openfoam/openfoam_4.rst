**********************
Pre/Post-Processing
**********************

继续 ``FENGSim/starter/openfoam/platHole`` 目录中的固体算例，该目录下有三个子目录，分别为0、constant、system，其中0目录中的文件定义了边界条件，constant目录中的文件定义了物理参数，例如弹性模量和泊松比，system目录中的文件定义了网格剖分、求解器、时间步、离散以及解法器。

运行blockMesh可以进行网格剖分，剖分后的网格数据保存在 ``platHole/constant/polyMesh`` 目录中的5个文件，分别为points、faces、owner、neighbour、boundary。和有限元网格有所区别，points是网格所有顶点，faces是网格所有单元面，单元面按照先内部单元面和后边界单元面排序，边界单元面按照几何模型面排序。owner定义了每个单元面归属的单元，如果是内部单元面，除了归属单元，还有相邻单元，相邻单元编号保存在neighbour中，这里需要注意的是neighbour对应了faces中的内部单元面，faces中内部单元面排在边界单元面前面。boundary是所有边界单元面，同一几何模型面上的边界单元面集合是按照faces中单元面编号起始位置以及个数定义。
