# Script generated with Bloom
pkgdesc="ROS - cpp_common contains C++ code for doing things that are not necessarily ROS related, but are useful for multiple packages. This includes things like the ROS_DEPRECATED and ROS_FORCE_INLINE macros, as well as code for getting backtraces. This package is a component of <a href="http://www.ros.org/wiki/roscpp">roscpp</a>."
url='http://www.ros.org/wiki/cpp_common'

pkgname='ros-melodic-cpp-common'
pkgver='0.6.9_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'console-bridge'
'ros-melodic-catkin'
)

depends=('boost'
'console-bridge'
)

conflicts=()
replaces=()

_dir=cpp_common
source=()
md5sums=()

prepare() {
    cp -R $startdir/cpp_common $srcdir/cpp_common
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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

