# Script generated with Bloom
pkgdesc="ROS - gazebo_ros_control"
url='http://ros.org/wiki/gazebo_ros_control'

pkgname='ros-lunar-gazebo-ros-control'
pkgver='2.7.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-angles'
'ros-lunar-catkin'
'ros-lunar-control-toolbox'
'ros-lunar-controller-manager'
'ros-lunar-gazebo-dev'
'ros-lunar-hardware-interface'
'ros-lunar-joint-limits-interface'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-std-msgs'
'ros-lunar-transmission-interface'
'ros-lunar-urdf'
)

depends=('ros-lunar-angles'
'ros-lunar-control-toolbox'
'ros-lunar-controller-manager'
'ros-lunar-gazebo-ros'
'ros-lunar-hardware-interface'
'ros-lunar-joint-limits-interface'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-std-msgs'
'ros-lunar-transmission-interface'
'ros-lunar-urdf'
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

