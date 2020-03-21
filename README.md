# ubuntu16.04-opencv-4.0-manual

apt install pkg-config

pkg-config --modversion opencv

apt-get purge  libopencv* python-opencv

apt-get autoremove

apt-get update

apt-get upgrade

apt-get install build-essential cmake

apt-get install pkg-config

apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev

apt-get install libavcodec-dev libavformat-dev libswscale-dev libxvidcore-dev libx264-dev libxine2-dev

apt-get install libv4l-dev v4l-utils

apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev

apt-get install libqt4-dev

apt-get install mesa-utils libgl1-mesa-dri libqt4-opengl-dev

apt-get install libatlas-base-dev gfortran libeigen3-dev

apt-get install python2.7-dev python3-dev python-numpy python3-numpy

apt-get install wget

apt-get install unzip

mkdir opencv

cd opencv

wget -O opencv.zip https://github.com/opencv/opencv/archive/4.0.0.zip

wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/4.0.0.zip

unzip opencv.zip

unzip opencv_contrib.zip

cd opencv-4.0.0/

mkdir build

cd build

cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D WITH_TBB=OFF \
-D WITH_IPP=OFF \
-D WITH_1394=OFF \
-D BUILD_WITH_DEBUG_INFO=OFF \
-D BUILD_DOCS=OFF \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D BUILD_EXAMPLES=OFF \
-D BUILD_TESTS=OFF \
-D BUILD_PERF_TESTS=OFF \
-D WITH_QT=ON \
-D WITH_GTK=OFF \
-D WITH_OPENGL=ON \
-D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-4.0.0/modules \
-D WITH_V4L=ON  \
-D WITH_FFMPEG=ON \
-D WITH_XINE=ON \
-D BUILD_NEW_PYTHON_SUPPORT=ON \
-D PYTHON2_INCLUDE_DIR=/usr/include/python2.7 \
-D PYTHON2_NUMPY_INCLUDE_DIRS=/usr/lib/python2.7/dist-packages/numpy/core/include/ \
-D PYTHON2_PACKAGES_PATH=/usr/lib/python2.7/dist-packages \
-D PYTHON2_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython2.7.so \
-D PYTHON3_INCLUDE_DIR=/usr/include/python3.5m \
-D PYTHON3_NUMPY_INCLUDE_DIRS=/usr/lib/python3/dist-packages/numpy/core/include/  \
-D PYTHON3_PACKAGES_PATH=/usr/lib/python3/dist-packages \
-D PYTHON3_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython3.5m.so \
../
