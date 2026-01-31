
**********************
编译安装
**********************

在Karamelo的程序文档 `<https://adevaucorbeil.github.io/karamelo/html/index.html>`_　中的Getting started中有Karamelo编译安装的详细介绍，在 ``FENGSim/toolkit/MultiX/extern/Karamelo`` 路径下的install安装脚本就是
根据Getting started写的。Karamelo还有额外的第三方依赖库matplotlib-cpp和gzstream，保存在 ``FENGSim/toolkit/MultiX/extern/Karamelo/third-party`` 路径下。

按照如下操作在FENGSim中编译Karamelo。

* 首先克隆FENGSim。 ::
  
    git clone https://github.com/FENGSim/FENGSim.git
  
* 再将MultiX克隆到 ``FENGSim/toolkit`` 路径下。 ::
  
    cd FENGSim/toolkit
    git clone https://github.com/FENGSim/MultiX.git
  
* 在 ``FENGSim/toolkit/MultiX/extern/Karamelo`` 中有一个install脚本，直接运行该脚本可以在Ubuntu24.04下编译Karamelo，无需其他操作。 ::
  
    cd FENGSim/toolkit/MultiX/extern/Karamelo
    ./install

还有一个uninstall脚本可以删除。


