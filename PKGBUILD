# Script generated with Bloom
pkgdesc="ROS - Robot-independent Gazebo plugins for sensors, motors and dynamic reconfigurable components."
url='http://gazebosim.org/tutorials?cat=connect_ros'

pkgname='ros-kinetic-gazebo-plugins'
pkgver='2.5.14_2'
pkgrel=1
arch=('any')
license=('BSD, Apache 2.0'
)

makedepends=('ros-kinetic-angles'
'ros-kinetic-camera-info-manager'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-gazebo-dev'
'ros-kinetic-gazebo-msgs'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-message-generation'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-polled-camera'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-rosgraph-msgs'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
'ros-kinetic-tf2-ros'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-urdf'
)

depends=('ros-kinetic-angles'
'ros-kinetic-camera-info-manager'
'ros-kinetic-cv-bridge'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-gazebo-dev'
'ros-kinetic-gazebo-msgs'
'ros-kinetic-geometry-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-message-runtime'
'ros-kinetic-nav-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-polled-camera'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-rosgraph-msgs'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
'ros-kinetic-tf2-ros'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-urdf'
)

conflicts=()
replaces=()

_dir=gazebo_plugins
source=()
md5sums=()

prepare() {
    cp -R $startdir/gazebo_plugins $srcdir/gazebo_plugins
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

