# Script generated with Bloom
pkgdesc="ROS - Robot-independent Gazebo plugins for sensors, motors and dynamic reconfigurable components."
url='http://gazebosim.org/tutorials?cat=connect_ros'

pkgname='ros-lunar-gazebo-plugins'
pkgver='2.7.3_1'
pkgrel=1
arch=('any')
license=('BSD, Apache 2.0'
)

makedepends=('ros-lunar-angles'
'ros-lunar-camera-info-manager'
'ros-lunar-catkin'
'ros-lunar-cv-bridge'
'ros-lunar-diagnostic-updater'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-gazebo-dev'
'ros-lunar-gazebo-msgs'
'ros-lunar-geometry-msgs'
'ros-lunar-image-transport'
'ros-lunar-message-generation'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-polled-camera'
'ros-lunar-rosconsole'
'ros-lunar-roscpp'
'ros-lunar-rosgraph-msgs'
'ros-lunar-rospy'
'ros-lunar-rostest'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
'ros-lunar-tf'
'ros-lunar-tf2-ros'
'ros-lunar-trajectory-msgs'
'ros-lunar-urdf'
)

depends=('ros-lunar-angles'
'ros-lunar-camera-info-manager'
'ros-lunar-cv-bridge'
'ros-lunar-diagnostic-updater'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-gazebo-dev'
'ros-lunar-gazebo-msgs'
'ros-lunar-geometry-msgs'
'ros-lunar-image-transport'
'ros-lunar-message-runtime'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-polled-camera'
'ros-lunar-rosconsole'
'ros-lunar-roscpp'
'ros-lunar-rosgraph-msgs'
'ros-lunar-rospy'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
'ros-lunar-tf'
'ros-lunar-tf2-ros'
'ros-lunar-trajectory-msgs'
'ros-lunar-urdf'
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

