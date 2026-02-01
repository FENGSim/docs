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
* Toolset (``ros-dev-tools``): `<http://packages.ros.org/ros2/ubuntu/pool/main/r/ros-dev-tools/>`_ ``ros-dev-tools`` includes ``Vsctool``, ``rosdep`` and ``colcon``. 
* Source code management from any repositories (``Vcstool``): `<https://github.com/dirk-thomas/vcstool>`_
* Dependency database (``rosdistro``): `<https://github.com/ros/rosdistro/tree/master>`_
* Dependency installer (``rosdep``): `<http://packages.ros.org/ros2/ubuntu/pool/main/p/python3-rosdep/>`_.
* Build tool (``colcon``): `<https://colcon.readthedocs.io/en/released/>`_

To resolve the download failure when running ``rosdep init``:

* Modify the path in ``FENGSim/toolkit/DAE/ros2/ros2/20-default.list``
* Modify the path in ``FENGSim/toolkit/DAE/ros2/ros2/__init__.py``

The source codes of ROS2, MoveIt2 and MoveIt2_Tutorials are located in the ``src`` directory.
After compilation, the directories ``build``, ``install`` and ``log`` will be created.

To install dependencies using the ``.xml`` files located in the ``src`` directory and the current directory: ::

  cd FENGSim/toolkit/DAE/ros2/ros2/ros2_jazzy/
  rosdep install --from-paths src --ignore-src -y --skip-keys "fastcdr rti-connext-dds-6.0.1 urdfdom_headers"

  cd FENGSim/toolkit/DAE/ros2/moveit2/ws_moveit2/src/
  rosdep install -r --from-paths . --ignore-src --rosdistro jazzy -y

To compile the codes located in the ``src`` directory: ::
  
  cd FENGSim/toolkit/DAE/ros2/ros2/ros2_jazzy
  ls src
  colcon build --symlink-install

The compilation of MoveIt2 depends on the ROS2 libraries. To set the ROS2 environment variables before compiling MoveIt2: ::

  source /opt/ros/jazzy/setup.bash

To set environment variables before using ROS2, MoveIt2 and MoveIt2_Tutorials: ::

  cd FENGSim/toolkit/DAE/ros2
  source ros2/ros2_jazzy/install/setup.bash
  source moveit2/ws_moveit2/install/setup.bash
  source moveit2_tutorials/install/setup.bash
