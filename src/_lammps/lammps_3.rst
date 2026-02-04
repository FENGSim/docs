
**********************
Examples
**********************

The directory ``FENGSim/toolkit/Particles/lammps/examples`` contains several examples and more details information can be found in the ``README`` file.

To run the crack example: ::

   cd FENGSim/starter/lammps/crack
   export LD_LIBRARY_PATH=$PWD/../../../toolkit/Particles/install/lammps_install/lib
   ./../../../toolkit/Particles/install/lammps_install/bin/lmp < in.crack

To open ``dump.crack`` using OVITO: ::

   ./../../../toolkit/MultiX/extern/Karamelo/ovito-basic-3.10.6-x86_64/bin/ovito
   
.. image:: fig/crack.gif
    :align: center

.. image:: fig/melt.gif
    :align: center
	    


