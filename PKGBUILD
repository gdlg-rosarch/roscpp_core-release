# Script generated with Bloom
pkgdesc="ROS - roscpp_serialization contains the code for serialization as described in <a href="http://www.ros.org/wiki/roscpp/Overview/MessagesSerializationAndAdaptingTypes">MessagesSerializationAndAdaptingTypes</a>. This package is a component of <a href="http://www.ros.org/wiki/roscpp">roscpp</a>."
url='http://ros.org/wiki/roscpp_serialization'

pkgname='ros-lunar-roscpp-serialization'
pkgver='0.6.9_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-cpp-common'
'ros-lunar-roscpp-traits'
'ros-lunar-rostime'
)

depends=('ros-lunar-cpp-common'
'ros-lunar-roscpp-traits'
'ros-lunar-rostime'
)

conflicts=()
replaces=()

_dir=roscpp_serialization
source=()
md5sums=()

prepare() {
    cp -R $startdir/roscpp_serialization $srcdir/roscpp_serialization
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

