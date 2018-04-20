# Script generated with Bloom
pkgdesc="ROS - gazebo_ros_control"
url='http://ros.org/wiki/gazebo_ros_control'

pkgname='ros-kinetic-gazebo-ros-control'
pkgver='2.5.14_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-angles'
'ros-kinetic-catkin'
'ros-kinetic-control-toolbox'
'ros-kinetic-controller-manager'
'ros-kinetic-gazebo-dev'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-limits-interface'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-transmission-interface'
'ros-kinetic-urdf'
)

depends=('ros-kinetic-angles'
'ros-kinetic-control-toolbox'
'ros-kinetic-controller-manager'
'ros-kinetic-gazebo-ros'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-limits-interface'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-transmission-interface'
'ros-kinetic-urdf'
)

conflicts=()
replaces=()

_dir=gazebo_ros_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/gazebo_ros_control $srcdir/gazebo_ros_control
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

