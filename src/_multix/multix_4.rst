**********************
Pre/Post-Processing
**********************

``.conf`` files are configuration files, while ``.geo`` files are mesh data files.

=======================
Formats
=======================

The conversions are between ``.xml`` and ``.conf`` files, and between ``.dat`` and ``.geo`` files.

To convert ``.geo`` to ``.dat`` ::

  cd FENGSim/starter/multix
  python3 dat2geo.py
  input .geo: example14
  .geo is Maxwell/conf/geo/example14.geo
  input .dat: example14
  .dat is example14.dat

To convert ``.dat`` to ``.geo`` ::
   
  cd FENGSim/starter/multix
  python3 dat2geo.py
  input .dat: example14
  .dat is example14.dat
  input .geo: example14
  .geo is Maxwell/conf/geo/example14.geo


=======================
Coil
=======================

As shown in the figure below, the coil in the ``.xml`` file is defined by four parameters: three for its projection and one for its height.

.. image:: fig/coil.png
   :scale: 80 %
   :alt: alternate text
   :align: center

.. code-block:: xml

      <part_5>
	<Attributes>5</Attributes>
      	<CurrentIntensity>3000</CurrentIntensity>
	<Geom>0.01,0.015,0.020,0.020</Geom>
	<Position>0,0,0</Position>
	<Direction>0,0,1</Direction>
      </part_5>


	   
