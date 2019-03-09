
#Ref
    http://raspberrypi4u.blogspot.com/2018/10/raspberry-pi-movidius-neural-compute-stick.html
    https://www.pyimagesearch.com/2017/09/04/raspbian-stretch-install-opencv-3-python-on-your-raspberry-pi/
*Requirements
    Hardware
    Raspberry Pi 3B Board with SD card and accessories.
    Intel Movidius Neural Compute Stick
    USB Camera 
    Software and Library
    Raspbien Stretch OS
    OpenCV 3.3.0
    Python 3.x
    Intel® Movidius™ NCSDK 2.0


    *Setup build , intro to install python2,3,Opecv 3.3.0
        sudo apt-get install build-essential cmake pkg-config
        sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
        sudo apt-get install libxvidcore-dev libx264-dev
        sudo apt-get install libgtk2.0-dev
        sudo apt-get install libatlas-base-dev gfortran
        sudo apt-get install python2.7-dev python3-dev



        
Download OpenCV 3.3.0: In the future you might want to change the 3.1.0 in the following code snippet to the newest version. You can check out the newest version here.

cd ~
wget -O opencv.zip https://github.com/Itseez/opencv/archive/3.3.0.zip
unzip opencv.zip
wget -O opencv_contrib.zip https://github.com/Itseez/opencv_contrib/archive/3.3.0.zip
unzip opencv_contrib.zip



Installing the Python 3 package manager:

wget https://bootstrap.pypa.io/get-pip.py
sudo python get-pip.py



Installing NumPy:

pip install numpy







cd ~/opencv-3.1.0/
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib-3.3.0/modules \
    -D BUILD_EXAMPLES=ON ..
make -j4
sudo make install
sudo ldconfig

// comman 
sudo rm -rf folderName


Testing OpenCV 3 installation: To test the installation it is easiest to open Python and check whether it is possible to import the bindings. As a result this step should show you the installed version which is in this case 3.1.0 or a newer version of OpenCV.

cd ~
python3
import cv2
cv2. __version__
 





