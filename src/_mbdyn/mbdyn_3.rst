**********************
算例测试
**********************

* 2自由度机械臂正逆运动学方程，关节角度和末端执行器位置姿态
* 2自由度机械臂正逆动力学方程，关节角度和关节力矩
* 6自由度机械臂正逆运动学方程，关节角度和末端执行器位置姿态
* 6自由度机械臂正逆动力学方程，关节角度和关节力矩

===========
算例一
===========

在 ``FENGSim/starter/mbdyn/free_falling`` 路径下有一个自由落体的简单例子，运行如下命令。 ::
  
    cd FENGSim/starter/mbdyn/free_falling
    ./../../../toolkit/DAE/install/mbdyn_install/bin/mbdyn -f free_falling_body_E.mbd
    gnuplot
    plot 'free_falling_body_E.mov' using 3:4

.. image:: fig/mbdyn_1.png
   :scale: 50 %
   :alt: alternate text
   :align: center    

===========
算例二
===========
在 ``FENGSim/starter/mbdyn/robot`` 路径下有UR3机械臂例子，运行如下命令。 ::
  
    cd FENGSim/starter/mbdyn/robot
    ./run

.. image:: fig/ur3e.gif
   :alt: alternate text
   :align: center    
