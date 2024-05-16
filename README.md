### 1. Clone repo
    git clone https://github.com/iminolee/dsp-navigation.git
### 2. Add sfm plugin
    cd /usr/local/include
    git clone https://github.com/robotics-upo/lightsfm.git
    cd lightsfm
    sudo make
    sudo make install
    cd ~/dsp-navigation/src && git clone https://github.com/robotics-upo/gazebo_sfm_plugin.git
    cd ..
    catkin_make
