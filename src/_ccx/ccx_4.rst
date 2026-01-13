**********************
Pre/Post-Processing
**********************

Calculix uses the Abaqus ``.inp`` format for input files. The results are stored in ``.frd`` files which can be converted to ``.vtk`` format.

To convert ``.frd`` files to ``.vtk`` files: ::

  cd FENGSim/starter/ccx/Mesh1
  python3 ./../../../toolkit/MultiX/extern/Calculix/ccx2paraview/ccx2paraview.py modal.frd vtu
  python3 ./../../../toolkit/MultiX/extern/Calculix/ccx2paraview/ccx2paraview.py modal.frd vtk

For more details about the ``ccx2paraview`` converter, please refer to its ``README.md`` file.

=======================
Formats
=======================

-------------------------------------------
from .xml and .msh to .inp
-------------------------------------------

The ``xml2inp.py`` script converts ``configure_modal.xml`` and a mesh file (``all.msh`` from CGX or ``all2.msh`` from GMSH) into a single ``modal2.inp`` file.
``xml2inp.py`` removes line and face elements from the ``.msh`` file.

To convert ``.xml`` and ``.msh`` to ``.inp``: ::
  
  cd FENGSim/starter/ccx/Mesh1
  python3 xml2inp.py 
  input .xml file: configure
  .xml file is  configure.xml
  input .msh file: all2
  .msh file is  all2.msh
  ./../../../toolkit/MultiX/extern/Calculix/bin/ccx_2.21 modal2
  python3 ./../../../toolkit/MultiX/extern/Calculix/ccx2paraview/ccx2paraview.py modal2.frd vtk

.. image:: fig/ccx_2.gif
   :scale: 50 %
   :alt: alternate text
   :align: center

-----------------------------------------------------------------
from .xml and .msh to .inp (with boundary conditions)
-----------------------------------------------------------------

GMSH automatically assigns unique IDs to all geometric sets. GMSH also defines physical groups for boundary conditions and materials, as shown in the figure below. 

.. image:: fig/ccx/1.png
   :scale: 50 %
   :alt: alternate text
   :align: center

Since boundary conditions are defined on node sets, the option "Save groups of nodes" is choosed to export ``.inp`` files, as shown in the figure below.
   
.. image:: fig/ccx/2.png
   :scale: 50 %
   :alt: alternate text
   :align: center

To convert ``.xml`` and ``.msh`` to ``.inp``: ::
  
  cd FENGSim/starter/ccx/beam
  python3 xml2inp.py 
  input .xml file: configure
  .xml file is  configure.xml
  input .msh file: all
  .msh file is  all.msh
  ./../../../toolkit/MultiX/extern/Calculix/bin/ccx_2.21 modal
  python3 ./../../../toolkit/MultiX/extern/Calculix/ccx2paraview/ccx2paraview.py modal.frd vtk
  
.. image:: fig/ccx/beam.gif
   :scale: 50 %
   :alt: alternate text
   :align: center

--------------------------------------
from .xml and .dat to .inp
--------------------------------------

在 ``FENGSim/starter/ccx/oiltank`` 目录下有configure_modal.xml、oiltank.dat、dat2inp.py。
configure_modal.xml是配置文件，oiltank.dat是网格文件。
dat2inp.py提取configure_modal.xml文件中的数据，提取oiltank.dat文件中的数据，将.dat格式转成.inp格式，合并生成新的modal.inp。

dat2inp.py的运行结果如下图，文件名称不用输入后缀名。

.. image:: fig/ccx/oiltank.jpg
   :scale: 50 %
   :alt: alternate text
   :align: center

.dat文件格式很简单，如下第1行的31276为顶点个数，99818为单元个数，
第8行的sphere_tank为单元组名称，56644为单元个数，第12行outer_surface_nodes为顶点组名称，9247为顶点个数，其他类似。 ::
  
  3 4 31276 99818
  1 -8315 2.55536e-12 0
  ......
  31276 8315 0 10850 
  1 59 2 1 98
  ......
  99818 31180 31223 31222 31179
  8 sphere_tank 56644
  2601
  .....
  97218
  7 outer_surface_nodes 9247
  788
  .....
  30489
  7 inner_surface_nodes 8317
  862
  .....
  30415
  7 fixed_nodes 200
  1
  .....
  31222
  8 guandao 2866
  47324
  .....
  52495
  8 support 40308
  1
  .....
  99818
  7 guandao_fixed_nodes 24
  14829
  .....
  16488

运行以下命令。 ::
  
  cd FENGSim/starter/ccx/oiltank
  mkdir Refs
  ./../../../toolkit/MultiX/extern/Calculix/bin/ccx_2.21 modal
  ./../../../toolkit/MultiX/extern/Calculix/bin/cgx -b shapes.fbl
  python3 ./../../../toolkit/MultiX/extern/Calculix/ccx2paraview/ccx2paraview.py modal.frd vtk

.. image:: fig/ccx/oiltank.gif
   :scale: 50 %
   :alt: alternate text
   :align: center

