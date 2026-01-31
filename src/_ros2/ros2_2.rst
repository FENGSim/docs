**********************
Build and Install
**********************

* To clone FENGSim: ::
  
    git clone https://github.com/FENGSim/FENGSim.git

* To clone DAE: ::
  
    cd FENGSim/toolkit
    git clone https://github.com/FENGSim/DAE.git

* To compile and install ROS2: ::
  
    cd FENGSim/toolkit/DAE/ros2/ros2/
    ./install
    
* To compile and install MoveIt2: ::
  
    cd FENGSim/toolkit/DAE/ros2/moveit2/
    ./install

* To compile and install MoveIt2_Tutorials: ::
  
    cd FENGSim/toolkit/DAE/ros2/moveit2_tutorials/
    ./install

Key tools and work flow for compiling ROS2, MoveIt2 and MoveIt2_Tutorials: 

* ROS packages: `<http://packages.ros.org/>`_
* Toolset (``ros-dev-tools``): ``Vsctool``, ``rosdep``, ``colcon``
* Source code management from any repositories (``Vcstool``): `<https://github.com/dirk-thomas/vcstool>`_
* Dependency database (``rosdistro``): `<https://github.com/ros/rosdistro/tree/master>`_
* Dependency installer (``rosdep``):
* Build tool (``colcon``): `<https://colcon.readthedocs.io/en/released/>`_

The ``rosdep`` package can be downloaded from `<http://packages.ros.org/ros2/ubuntu/pool/main/p/python3-rosdep/>`_.  
To resolve the download failure when running ``rosdep init``:

* modify the path in ``FENGSim/toolkit/DAE/ros2/ros2/20-default.list``
* modify the path in ``FENGSim/toolkit/DAE/ros2/ros2/__init__.py``


  

ROS2、MoveIt2、MoveIt2_Tutorials的源代码都在 ``src`` 目录下，编译安装后会生成  ``build`` ， ``install`` ， ``log`` 三个目录。
安装依赖库的命令为 ``rosdep install`` ，需要注意路径设置，例如： ::

  rosdep install --from-paths src --ignore-src -y --skip-keys "fastcdr rti-connext-dds-6.0.1 urdfdom_headers"

中指定了路径为 ``src`` 也就是源代码目录，会从源代码目录中寻找package.xml的依赖配置文件，再例如： ::

  rosdep install -r --from-paths . --ignore-src --rosdistro jazzy -y

中指定了当前路径，是因为在 ``src`` 路径下运行的该命令。编译的命令为 ``colcon build`` ，需要注意在 ``src`` 的上一层路径下执行该命令。例如： ::

  cd FENGSim/toolkit/DAE/ros2/ros2/ros2_jazzy
  colcon build --symlink-install

在 ``FENGSim/toolkit/DAE/ros2/ros2/ros2_jazzy/install`` ， ``FENGSim/toolkit/DAE/ros2/moveit2/ws_moveit2/install`` 和 ``FENGSim/toolkit/DAE/ros2/moveit2_tutorials/install`` 以及 ``/opt/ros/jazzy/`` 目录下有setup.bash文件配置环境变量，在使用ROS2、MoveIt2、MoveIt2_Tutorials之前运行以下命令。 ::

  cd FENGSim/toolkit/DAE/ros2
  source ros2/ros2_jazzy/install/setup.bash
  source moveit2/ws_moveit2/install/setup.bash
  source moveit2_tutorials/install/setup.bash

``/opt/ros/jazzy/`` 是在MoveIt2安装过程中产生的，在MoveIt2编译需要调用通过ros包管理器安装的一些库，因此需要运行以下命令配置环境变量，否则编译过程中会有一些ros链接库找不到。 ::

  source /opt/ros/jazzy/setup.bash
  
ROS2、MoveIt2、MoveIt2_Tutorials的编译安装可以在Docker中进行，运行 ``FENGSim/cli/`` 目录下的脚本程序test-docker-gui.sh，可以创建一个可以
打开图形用户界面的Docker容器，需要注意的是容器、终端或者电脑重启后，再进入容器可能会打不开图形用户界面，需要重复操作下test-docker-gui.sh中的以下几条命令。 ::
  
  sudo xhost +si:localuser:root
  sudo chmod 777 /tmp/.docker.xauth
  XAUTH=/tmp/.docker.xauth

