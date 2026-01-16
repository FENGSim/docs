
**********************
Build and Install
**********************

按照如下操作在FENGSim中编译OpenFOAM。

* 首先克隆FENGSim。 ::
  
    git clone https://github.com/FENGSim/FENGSim.git
  
* 再将CFD克隆到 ``FENGSim/toolkit`` 路径下。 ::
  
    cd FENGSim/toolkit
    git clone https://github.com/FENGSim/CFD.git
  
* 在 ``FENGSim/toolkit/CFD/openfoam`` 中有一个install脚本，该脚本是根据网站中Compiling Sources写的，直接运行该脚本可以在Ubuntu24.04下编译OpenFOAM，无需其他操作。 ::
  
    cd FENGSim/toolkit/CFD/openfoam
    ./install

OpenFOAM有两个仓库，分别是OpenFOAM-dev和ThirdParty-dev，dev可以换成版本号，例如OpenFOAM-12和ThirdParty-12。需要将OpenFOAM-dev和ThirdParty-dev保存在同一路径下，
在OpenFOAM-dev目录下运行的编译命令还会编译ThirdParty-dev目录中的第三方库。OpenFOAM-dev目录下有三个子目录，分别为applications、test、tutorials，test和tutorials里有很多测试例子，例子里主要包括前处理文件，
applications里有APP开发的例子，例子里主要包括二次开发的程序。OpenFOAM中使用了wmake编译工具，wmake是用脚本程序开发的，采用wmake又写了脚本程序Allwmake去执行编译，例如在OpenFOAM-dev目录下有Allwmake脚本程序。
编译安装完后，为了运行可执行程序或者调用链接库，需要配置环境变量，运行如下命令。 ::
  
    cd FENGSim/toolkit/CFD/openfoam
    source OpenFOAM-dev/etc/bashrc
    echo $FOAM_INST_DIR

如果要编译APP，在 ``FENGSim/starter/openfoam/mkdir`` 中有一个例子，运行如下命令，会发现在当前目录下编译生成了可执行程序Test-mkdir，运行可执行程序，在当前目录下创建了一个test目录。 ::
  
    cd FENGSim/starter/openfoam/mkdir
    wmake
    ./Test-mkdir

