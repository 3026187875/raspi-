下载好文件，进入文件目录
编译前安装所需依赖               
sudo apt-get -y install build-essential cmake unzip pkg-config       
sudo apt-get -y install libjpeg-dev libpng-dev libtiff-dev          
sudo apt-get -y install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev               
sudo apt-get -y install libxvidcore-dev libx264-dev             
sudo apt-get -y install libgtk-3-dev            
sudo apt-get -y install libcanberra-gtk*            
sudo apt-get -y install libatlas-base-dev gfortran           
开始编译         
cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D OPENCV_EXTRA_MODULES_PATH=/home/pi/Downloads/opencv_contrib-4.4.0/modules \#本行需根据自己安装的路径修改     
-D BUILD_EXAMPLES=ON \
-D WITH_LIBV4L=ON \
-D PYTHON3_EXECUTABLE=/usr/bin/python3.7 \
-D PYTHON_INCLUDE_DIR=/usr/include/python3.7 \
-D PYTHON_LIBRARY=/usr/lib/arm-linux-gnueabihf/libpython3.7m.so \
-D PYTHON3_NUMPY_INCLUDE_DIRS=/usr/lib/python3/dist-packages/numpy/core/include \
..       
输入以上命令开始检查，没有错误后输入     
make # 开始编译          
make -j4 # 多核编译，适合4G以上版本pi            
编译完成后           
sudo make install         
此版本没有开启FFmpeg。如果需要请使用以下cmake命令，并预先编译安装好FFmpeg         
cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D OPENCV_EXTRA_MODULES_PATH=/home/pi/Downloads/opencv_contrib-4.4.0/modules \#本行需根据自己安装的路径修改     
-D BUILD_EXAMPLES=ON \
-D WITH_LIBV4L=ON \
-D WITH_FFMPEG=ON \ # 此命令即开启FFmpeg       
-D PYTHON3_EXECUTABLE=/usr/bin/python3.7 \
-D PYTHON_INCLUDE_DIR=/usr/include/python3.7 \
-D PYTHON_LIBRARY=/usr/lib/arm-linux-gnueabihf/libpython3.7m.so \
-D PYTHON3_NUMPY_INCLUDE_DIRS=/usr/lib/python3/dist-packages/numpy/core/include \
..        
经验证，以上命令无法通过编译，解决方案正在查找。
