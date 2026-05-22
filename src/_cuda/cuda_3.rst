**********************
Examples
**********************

Compile and run a simple CUDA example: ::

  cd FENGSim/starter/cuda/hello_world
  nvcc -o test test.cu
  ./test
  mkdir build
  cd build
  cmake ..
  make -j4
  ./test
