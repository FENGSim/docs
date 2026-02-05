**********************
Build and Install
**********************

* To clone FENGSim: ::
  
    git clone https://github.com/FENGSim/FENGSim.git
  
* To clone CFD and NLA: ::
  
    git submodule init
    git submodule update toolkit/CFD
    git submodule update toolkit/NLA
    
* To compile and install: ::
		
    cd FENGSim/toolkit/CFD/ibamr
    ./install   
