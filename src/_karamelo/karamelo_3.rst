
**********************
Examples
**********************

To run the ``two-disks.mpm`` example: ::

  cd FENGSim/starter/karamelo/ex_1
  ./../../../toolkit/MultiX/extern/Karamelo/build/karamelo -i two-disks.mpm

To download OVITO and open ``dump_p.*.LAMMPS``: ::

  cd FENGSim/toolkit/MultiX/extern/Karamelo
  ./download_ovito
  ./ovito-basic-3.10.6-x86_64/bin/ovito &

.. image:: fig/karamelo.gif
   :scale: 50 %
   :alt: alternate text
   :align: center

For parallel execution, each process will generate separate ``.LAMMPS`` files; these can later be merged using a Python script. ::

  cd FENGSim/starter/karamelo/ex_1
  mpirun -np 2 ./../../../toolkit/MultiX/extern/Karamelo/build/karamelo -i two-disks.mpm

To merge ``dump_g.proc-0.*.LAMMPS`` and ``dump_g.proc-1.*.LAMMPS`` to ``dump.*.dump``: ::

  cd FENGSim/starter/karamelo/ex_1
  python3 ../../../toolkit/MultiX/extern/Karamelo/ovito_merge_dumps.py

    
