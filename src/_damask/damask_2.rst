**********************
Build and Install
**********************

* To clone FENGSim: ::
  
    git clone https://github.com/FENGSim/FENGSim.git
  
* To clone NLA: ::

    cd FENGSim
    git submodule init
    git submodule update toolkit/NLA

* To clone MultiX: ::

    cd FENGSim/toolkit
    git clone https://github.com/OpenDigitalTwin-Dev/MultiX.git
    
* To compile and install: ::
		
    cd FENGSim/toolkit/MultiX/extern/DAMASK
    ./install.sh
