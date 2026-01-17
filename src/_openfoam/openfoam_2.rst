
**********************
Build and Install
**********************

* To clone FENGSim: ::
  
    git clone https://github.com/FENGSim/FENGSim.git
  
* To clone CFD: ::
  
    cd FENGSim/toolkit
    git clone https://github.com/FENGSim/CFD.git
  
* To install OpenFOAM: ::
  
    cd FENGSim/toolkit/CFD/openfoam
    ./install
    
OpenFOAM comprises two core repositories: OpenFOAM-dev and ThirdParty-dev. Note that the suffix -dev can be replaced with a specific version number, such as OpenFOAM-12 and ThirdParty-12. It is required to place both repositories (e.g., OpenFOAM-dev and ThirdParty-dev) in the same parent directory, as they are compiled together during the build process.

Many examples (preprocessing files) can be found in ``FENGSim/toolkit/CFD/openfoam/OpenFOAM-dev/test`` and ``FENGSim/toolkit/CFD/openfoam/OpenFOAM-dev/tutorials``.
Application examples (secondary development source codes) can be found in ``FENGSim/toolkit/CFD/openfoam/OpenFOAM-dev/applications``.

The shell script ``wmake`` is the compilation tool for OpenFOAM. Scripts such as ``Allwmake`` utilize ``wmake`` to automate the build process.

To set environmental variables for executing binaries or linking libraries: ::
  
    cd FENGSim/toolkit/CFD/openfoam
    source OpenFOAM-dev/etc/bashrc
    echo $FOAM_INST_DIR

To run an application exmaple that creates a directory: ::
  
    cd FENGSim/starter/openfoam/mkdir
    wmake
    ./Test-mkdir

