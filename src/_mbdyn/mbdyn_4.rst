**********************
Pre/Post-Processing
**********************

=========================
UR3 Robot Arm
=========================

Configuration files:

* ``FENGSim/starter/mbdyn/robot/robot_arm.mbd``

This example is for a 6-dof robot arm, though without the end effector, the final dof is disregarded.

To define angle constraints using time-dependent scalar funtions in ``robot_arm.mbd``: ::

  #-----------------------------------------------------------------------------
  # Scalar Functions 
  scalar function: "Fun_Motor_JoTotp_Stage",
  multilinear,
      0.0, 0.0,
      1.0, 0.0,
      2.0, -1./2.*pi;

  scalar function: "Fun_Motor_JoTotj_Stage_UpperArm",
  multilinear,
      0.0, 0.0,
      1.0, 0.0,
      2.0, -2./6.*pi;
       
  scalar function: "Fun_Motor_JoTotj_UpperArm_LowerArm",
  multilinear,
      0.0, 0.0,
      1.0, 0.0,
      2.0, -4./6.*pi;
      
  scalar function: "Fun_Motor_JoTotj_LowerArm_Wrist",
  multilinear,
      0.0, 0.0,
      1.0, 0.0,
      2.0, 1./6.*pi;
      
  scalar function: "Fun_Motor_JoTotj_Wrist_Hand",
  multilinear,
      0.0, 0.0,
      1.0, 0.0,
      2.0, pi;

* Line 7: the first number ``2.0`` is a time step and the second number ``-1./2.*pi`` is an angle value.

Geometry files (base path:``FENGSim/starter/mbdyn/robot/``):

* .stp file: ``UR3.STEP``
* .stl files: ``down.stl``, ``hand.stl``, ``stage1.stl``, ``stage2.stl``, ``upper.stl``, ``wrist.stl``
* .traj files: ``ur3.traj``, line segments with the pose and velocity values
* UR3E technical file: ``ur3e_e-series_datasheets_web.pdf``
  
The parameter (``131.05mm``) shown in the figure below from ``ur3e_e-series_datasheets_web.pdf`` does not match the corresponding one (``110.4mm``) in ``UR3.STEP``.

.. image:: fig/mbdyn_2.png
   :width: 200
   :alt: alternate text
   :align: center
	   
Results:

* ``.mov`` files: ``FENGSim/starter/mbdyn/robot/robot_arm.mov``
  
More details for ``.mov`` format in Section 2.1 of `<https://github.com/mmorandi/MBDyn-web/raw/main/userfiles/documents/tutorials.pdf>`_ :

* the node label
* the three coordinates of the position of the node
* the three Euler-like angles that define the orientation of the node (following the 1, 2, 3 convention)
* the three components of the velocity of the node
* the three components of the angular velocity of the node
