# Script generated with Bloom
pkgdesc="ROS - Wrapper of the Allied Vision Technologies (AVT) VIMBA Ethernet and Firewire SDK."
url='http://wiki.ros.org/avt_vimba_ros'

pkgname='ros-lunar-avt-vimba-camera'
pkgver='0.0.10_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-camera-info-manager'
'ros-lunar-catkin'
'ros-lunar-diagnostic-updater'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-image-geometry'
'ros-lunar-image-transport'
'ros-lunar-message-filters'
'ros-lunar-polled-camera'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
)

depends=('ros-lunar-camera-info-manager'
'ros-lunar-diagnostic-updater'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-image-geometry'
'ros-lunar-image-transport'
'ros-lunar-message-filters'
'ros-lunar-polled-camera'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
)

conflicts=()
replaces=()

_dir=avt_vimba_camera
source=()
md5sums=()

prepare() {
    cp -R $startdir/avt_vimba_camera $srcdir/avt_vimba_camera
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

