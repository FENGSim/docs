**********************
Examples
**********************

Free Falling: ::
  
    cd FENGSim/starter/mbdyn/free_falling
    ./../../../toolkit/DAE/install/mbdyn_install/bin/mbdyn -f free_falling_body_E.mbd
    gnuplot
    plot 'free_falling_body_E.mov' using 3:4

.. image:: fig/mbdyn_1.png
   :scale: 50 %
   :alt: alternate text
   :align: center    

UR3 Robot Arm: ::
  
    cd FENGSim/starter/mbdyn/robot
    ./run

* Forward & inverse kinematics: the mapping between joint angles and end-effector poses (position and orientation)
* Forward & inverse dynamics: the mapping between joint angles and joint torques

.. image:: fig/ur3e.gif
   :alt: alternate text
   :align: center    

