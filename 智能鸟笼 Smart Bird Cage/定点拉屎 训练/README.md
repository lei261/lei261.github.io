
安装方法：
Win10:
安装anaconda, 英伟达驱动，cuda驱动，cudnn驱动以及其dependency。
cudnn直接复制到cuda文件夹就行。


Ubuntu:
安装英伟达驱动： 简单

安装CUDA：


NVCC not installed:
    From the terminal:
    https://askubuntu.com/questions/885610/nvcc-version-command-says-nvcc-is-not-installed
     nano /home/username/.bashrc

     # or

     nano /home/$USER/.bashrc
    Inside there add the following: (replace cuda-8.0 with your version)

     export PATH="/usr/local/cuda-8.0/bin:$PATH"
     export LD_LIBRARY_PATH="/usr/local/cuda-8.0/lib64:$LD_LIBRARY_PATH"
    Then do the following to save and close the editor:

     On you keyboard press the following: 

     ctrl + o             --> save 
     enter or return key  --> accept changes
     ctrl + x             --> close editor
    Now either do source .bashrc or close and open another terminal

Now run nvcc --version


安装CUDNN：
https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html#installlinux-tar


安装DLC-live 的时候，
conda create -n dlc-live python=3.7
pip install tensorflow==2.10.0
pip install deeplabcut-live
pip install opencv-python
pip install opencv-contrib-python
