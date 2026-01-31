**********************
Pre/Post-Processing
**********************

* Configuration files: ``FENGSim/starter/palace/examples/spheres/spheres.json``
* Gmsh Julia script files: ``FENGSim/starter/palace/examples/spheres/mesh/mesh.jl``
* Mesh files: ``FENGSim/starter/palace/examples/spheres/mesh/spheres.msh``
* ``.vtk`` files: ``FENGSim/starter/palace/examples/spheres/postpro/paraview/electrostatic/electrostatic.pvd``
* ``.csv`` files: ``FENGSim/starter/palace/examples/spheres/postpro/*.csv``

Palace uses the Gmsh ``.msh`` file format.

==========================
Mesh Format
==========================

To install Julia: ::

  cd FENGSim/starter/palace/examples/spheres/mesh
  ./install_julia_gmsh

To generate the ``spheres.msh`` mesh file using Julia: ::

  cd FENGSim/starter/palace/examples/spheres/mesh
  julia mesh.jl

To generate the ``spheres.msh`` mesh file using Gmsh: ::

  cd FENGSim/starter/palace/examples/spheres/mesh
  gmsh spheres.geo -3 -o "spheres2.msh" -format msh2

The format option ``msh2`` is used for the Version 2 ASCII format.
If the mesh file is exported using Gmsh GUI, do not select the option "Save all elements".
If this option is enabled, physical group numbers will be omitted from the ``.msh`` file.

The Gmsh ``.msh`` file format is documented in Section 9.1 of the user manual `<https://web.mit.edu/gmsh_v3.0.1/gmsh.pdf>`_. ::

  $MeshFormat
  2.2 0 8
  $EndMeshFormat
  $PhysicalNames
  4
  2 2 "farfield"
  2 3 "sphere_a"
  2 4 "sphere_b"
  3 1 "domain"
  $EndPhysicalNames
  $Nodes
  48882
  1 4.592425496802574e-15 -1.124819836996393e-30 75
  2 4.592425496802574e-15 -1.124819836996393e-30 -75
  .......
  $EndNodes
  $Elements
  11317
  1 21 2 2 1 2 234 225 295 296 297 298 299 300 301
  2 21 2 2 1 127 227 129 302 303 304 305 306 307 308
  .......
  437 21 2 3 2 2020 3 2093 2112 2113 2114 2115 2116 2117 2118
  438 21 2 3 2 2053 2078 2079 2119 2120 2121 2122 2123 2124 2125
  .......
  645 21 2 4 3 2961 2958 2997 3021 3022 3023 3024 3025 3026 3027
  646 21 2 4 3 2944 2941 2995 3028 3029 3030 3031 3032 3033 3034
  .......
  845 29 2 1 3 3805 3806 3807 3808 5287 5288 5289 5290 5291 5292 5293 5294 5295 5296 5297 5298 5299 5300 5301 5302
  846 29 2 1 3 3809 3810 3811 2992 5303 5304 5305 5306 5307 5308 5309 5310 5311 5312 5313 5314 5315 5316 5317 5318
  .......
  $EndElements

* Line 6: The first number ``2`` is the dimension and the second number ``3`` is the physical group number.
* Line 19: The second number ``21`` is the element type. The third number is the tag number (for how many tags).
  The fourth and fifth numbers are the tags for physical groups and geometrical groups.

==========================
Configuration Format
==========================

Solvers:

* Eigenmode
* Driven
* Transient
* Electrostatic
* Magnetostatic

Materials:

* Permeability
* Permittivity
* LossTan
* Conductivity
* LondonDepth
* MaterialAxes
  
Boundary Conditions:

* PEC: zero tangential electric field used for electrostatics, frequency domain and time domain
* PMC: zero tangential magnetic field used for  magnetostatics, frequency domain and time domain
* Impedance: relates the tangential electric and magnetic fields on the boundary used for eigenmode, frequency domain and time domain
* Absorbing: eigenmode, frequency domain, time domain
* Conductivity: frequency domain
* LumpedPort: eigenmode, frequency domain, time domain
* WavePort: frequency domain
* WavePortPEC: from WavePort
* SurfaceCurrent: magnetostatics, frequency doamin, time domain
* Ground: zero voltage used for electrostatics
* ZeroCharge: zero charge used for electrostatics
* Terminal: electroststics
* Periodic

--------------------
from .xml to .json
--------------------

在 ``FENGSim/starter/palace/examples/spheres/`` 路径下有两个python脚本，分别是xml2json.py和xml2json2.py，
xml2json.py是原封不动将xml中字典格式转换为json，xml2json2.py是将xml中网格组名称去掉后转换为json。
运行xml2json2.py，会要求从命令行输入xml文件名称和网格文件名称，名称不用输入后缀名，网格文件默认保存在 ``FENGSim/starter/palace/examples/spheres/mesh`` 路径下，
运行结果如下图，并生成data3.json文件。

.. image:: fig/palace_2.png
   :scale: 50 %
   :alt: alternate text
   :align: center

在 ``FENGSim/starter/palace/examples/spheres/`` 路径下有两个例子。
一个是原始Palace给的电容矩阵例子，xml和msh文件名称分别为configure_spheres.xml和spheres.msh，也可以用spheres2.msh。生成的data3.json和sphere.json区别是，data3.json是一阶单元，sphere.json是三阶单元。sphere.msh和sphere2.msh区别是，sphere.msh是三阶单元网格文件，sphere2.msh是一阶单元网格文件。这个例子中用了Ground和Terminal的边界条件。另外一个是自定义的例子，xml和msh文件名称分别为configure_ex_3d.xml和ex_3d.msh，这个例子中测试了Ground、Terminal、ZeroCharge三种边界条件。这两个例子测试了xml2json2.py。

.. image:: fig/palace_3.png
   :scale: 50 %
   :alt: alternate text
   :align: center
