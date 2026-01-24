**********************
Build and Install
**********************

* To clone FENGSim: ::
  
    git clone https://github.com/OpenDigitalTwin-Dev/FENGSim.git

* To clone MultiX: ::
  
    cd FENGSim/toolkit
    git clone https://github.com/OpenDigitalTwin-Dev/MultiX.git

* To clone NLA: ::
  
    cd FENGSim/toolkit
    git clone https://github.com/OpenDigitalTwin-Dev/NLA.git
  
* To clone CEM: ::
  
    cd FENGSim/toolkit
    git clone https://github.com/OpenDigitalTwin-Dev/CEM.git

* To compile and install ALE: ::
  
    cd FENGSim/toolkit/MultiX/extern/ALE/
    ./install.sh
    
* To compile and install Palace: ::
  
    cd FENGSim/toolkit/CEM/palace
    ./install
    ls ../install/palace_install

这里需要注意的是， ``FENGSim/toolkit/CEM/palace/palace/models/postoperator.cpp`` 编译有问题。需要将以下函数名中的Coeff和VCoeff去掉。 ::

  RegisterVCoeffField
  DeregisterVCoeffField
  RegisterCoeffField
  DeregisterCoeffField
  CoeffFieldMapType
  VCoeffFieldMapType
  GetCoeffFieldMap
  GetVCoeffFieldMap

并将以下函数调用注销掉。 ::

  paraview_bdr.SetBoundaryOutput(true);
  paraview_bdr.RegisterField(*)
  paraview.RegisterField("U_e", U_e.get());
  paraview.RegisterField("U_m", U_m.get());
  paraview.RegisterField("S", S.get());

如果用阿里云服务器root账户编译Palace，Petsc编译中的mpi并行会报错，如果是用docker中root账户，Palace并行计算也会报错，因此采用非root账户。

  
