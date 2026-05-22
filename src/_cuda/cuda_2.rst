**********************
Build and Install
**********************

Ubuntu version: 24.04

Install NVIDIA GPU driver: ::

  sudo apt-get --purge remove '*nvidia*'
  sudo apt autoremove
  sudo apt autoclean
  sudo ubuntu-drivers autoinstall

Install CUDA: ::
  
  wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2404/x86_64/cuda-keyring_1.1-1_all.deb
  sudo dpkg -i cuda-keyring_1.1-1_all.deb
  sudo apt update
  sudo apt install cuda-toolkit
    
