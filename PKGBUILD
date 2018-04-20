# Script generated with Bloom
pkgdesc="ROS - Interface for using ROS with the <a href="http://gazebosim.org/">Gazebo</a> simulator."
url='http://gazebosim.org/tutorials?cat=connect_ros'

pkgname='ros-lunar-gazebo-ros-pkgs'
pkgver='2.7.3_1'
pkgrel=1
arch=('any')
license=('BSD,LGPL,Apache 2.0'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-gazebo-dev'
'ros-lunar-gazebo-msgs'
'ros-lunar-gazebo-plugins'
'ros-lunar-gazebo-ros'
)

conflicts=()
replaces=()

_dir=gazebo_ros_pkgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/gazebo_ros_pkgs $srcdir/gazebo_ros_pkgs
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

