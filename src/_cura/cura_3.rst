**********************
Examples
**********************

* Convert STL to slices: ::
		
    cd FENGSim/start/AM
    ./install
    cd build
    cmake ..
    make -j4
    ./AMSolver

Open ``thinwall.stl`` (located in ``FENGSim/start/AM/build/AM/conf/geo/``) and ``slices.vtk`` (located in ``FENGSim/start/AM/build/data/am/``) using ParaView.

.. image:: fig/cura_1.png
   :scale: 40 %
   :alt: alternate text
   :align: center

* Modify ``FENGSim/start/AM/build/AM/conf/m++conf`` to set ``loadconf = AM/conf/pathplanning.conf``. Do path planning: ::
		
    cd FENGSim/start/AM
    ./install
    cd build
    cmake ..
    make -j4
    ./AMSolver

Open ``pathplanning.vtk`` (located in ``FENGSim/start/AM/build/data/am/``) using ParaView.

.. image:: fig/cura_2.png
   :scale: 40 %
   :alt: alternate text
   :align: center
