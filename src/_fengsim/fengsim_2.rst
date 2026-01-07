*******************************
Build and Install
*******************************

To install FENGSim: ::

  git clone https://github.com/FENGSim/FENGSim.git
  cd FENGSim
  ./install

To download submodules: ::
  
  cd FENGSim
  ./submodule

---------
Docker
---------

To create a Docker container named ``test`` based on Ubuntu 24.04 with GUI support: ::
  
  cd FENGSim
  ./cli/test-docker-gui 

To enter the Docker container: ::

  sudo docker ps -a
  sudo docker start test
  sudo docker exec -it test /bin/bash

To build FENGSim in a container that requires some Qt libraries, first set the environment variables: ::
  
  export QT_DEBUG_PLUGINS=1
  cd FENGSim
  ./install

The libraries could be installed according to the error messages.

To create a Docker group and add new user: ::
  
  sudo groupadd -f docker
  sudo usermod -aG docker user_name
