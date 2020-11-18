# Intel Real Sense Setup For Raspberry Pi 4 Ubuntu 20.04

### install linux image on sd card
1. download ubuntu mate 20.04 from [https://ubuntu-mate.org/download/arm64/focal/](https://ubuntu-mate.org/download/arm64/focal/)

2. download etcher to write image to sd card [https://www.balena.io/etcher/](https://www.balena.io/etcher/)

3. insert sd card into your pc and select image -> then select drive and flash

### update operating system
1. open terminal and run `sudo apt update; sudo apt upgrade -y` you will need to enter your password for sudo commands

### installing sdk
1. in terminal change directory to desktop `cd ~/Desktop`

2. in terminal run `sudo apt install autoconf autogen libtool`

3. in terminal run `wget https://github.com/IntelRealSense/librealsense/raw/master/scripts/libuvc_installation.sh`

4. when finished make executable `chmod +x ./libuvc_installation.sh`

5. then run the script `./libuvc_installation.sh`

6. to verify installed run `realsense-viewer` in terminal. This should run the intel tool to view camera

### pyrealsense2 library
1. go to desktop directory `cd ~/Desktop`

2. download the repository `git clone https://github.com/IntelRealSense/librealsense.git`

3. cd into repo `cd librealsense`

4. make a build directory and cd into it `mkdir build && cd build`

5. run cmake `cmake ../ -DBUILD_PYTHON_BINDINGS:bool=true -DPYTHON_EXECUTABLE=$(which python3)`

6. run make `make -j4`

7. install `sudo make install`

8. update python path `export PYTHONPATH=$PYTHONPATH:/usr/local/lib`

### add additional common libraries
1. install pip `sudo apt install python3-pip`

2. install numpy `pip3 install numpy`

3. install opencv `pip3 install opencv-python`
