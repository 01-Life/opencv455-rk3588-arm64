# opencv455-rk3588-arm64
build opencv455 on rk3588 libs and shell ;


echo ""
echo "================================"

echo "cmake CMAKE_BUILD_TYPE=RELEASE "

#file use 
#opencv 455
#opencv_contrib-4.5.5

===================================

cd opencv-4.5.5
mkdir do
cd do

===================================

#ok 1 many libs 
cmake \
	-D CMAKE_BUILD_TYPE=RELEASE  \
	-D CMAKE_INSTALL_PREFIX=/usr/local  \
	-D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-4.5.5/modules    \
	\
	-D BUILD_EXAMPLES=ON  \
	-D BUILD_opencv_apps=ON   \
	-D BUILD_opencv_python3=ON  \
	\
	-D INSTALL_C_EXAMPLES=ON \
	-D INSTALL_TESTS=ON \
	\
	-DBUILD_TESTS=OFF  \
	-DBUILD_OPENCV_CALIB3D=OFF  \
	-DBUILD_OPENCV_ANNOTATION=OFF  \
	-DBUILD_opencv_perf_core=OFF  \
	-D BUILD_OPENCV_visualisation=OFF  \
	\
	.. 


===================================

#ok 2 one lib-world
cmake \
	-D CMAKE_BUILD_TYPE=RELEASE  \
	-D CMAKE_INSTALL_PREFIX=/usr/local  \
	-D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-4.5.5/modules    \
	\
	-D BUILD_opencv_world=ON   \
	\
	-D BUILD_EXAMPLES=ON  \
	-D BUILD_opencv_apps=ON   \
	-D BUILD_opencv_python3=ON  \
	\
	-D INSTALL_C_EXAMPLES=ON \
	-D INSTALL_TESTS=ON \
	\
	-DBUILD_TESTS=OFF  \
	-DBUILD_OPENCV_CALIB3D=OFF  \
	-DBUILD_OPENCV_ANNOTATION=OFF  \
	-DBUILD_opencv_perf_core=OFF  \
	-D BUILD_OPENCV_visualisation=OFF  \
	\
	.. 
	
sudo make DESTDIR=/usr/local install -j4

