
**********************
Examples
**********************

测试OpenFoam中的求解器，在 ``FENGSim/toolkit/CFD/openfoam/OpenFOAM-dev/applications/`` 路径下有两个目录，分别为modules和solvers。其中modules里是各个求解器模块，
见User Guide中第3.5节，求解器模块会编译成链接库，例如 ``modules/fluid`` 模块编译后，得到 ``FENGSim/toolkit/CFD/openfoam/OpenFOAM-dev/platforms/linux64GccDPInt32Opt/lib/libfluid.so`` 。
solvers里是求解器，通过solvers调用modules里的模块，见User Guide中第3.6节，求解器会编译成可执行程序，例如 ``solvers/foamRun`` 编译后，得到 ``FENGSim/toolkit/CFD/openfoam/OpenFOAM-dev/platforms/linux64GccDPInt32Opt/bin/foamRun`` 。

在 ``FENGSim/starter/openfoam/platHole`` 目录中是一个固体算例，运行如下命令。 ::
  
    cd FENGSim/starter/openfoam/platHole
    ./Allrun
    foamToVTK

这里一定要注意，需要运行环境变量的配置文件。生成的vtk文件在 ``FENGSim/starter/openfoam/platHole/VTK`` 目录中，可以用paraview打开，如下图。
    
.. image:: fig/openfoam_1.png
   :scale: 50 %
   :alt: alternate text
   :align: center

AdditiveFoam中熔池计算。
	   
.. image:: fig/heat.gif
   :scale: 50 %
   :alt: alternate text
   :align: center
	   
.. image:: fig/marangoni.gif
   :scale: 50 %
   :alt: alternate text
   :align: center


