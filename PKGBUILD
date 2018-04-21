# Script generated with Bloom
pkgdesc="ROS - Twist multiplexer, which multiplex several velocity commands (topics) and allows to priorize or disable them (locks)."


pkgname='ros-kinetic-twist-mux'
pkgver='3.0.0_1'
pkgrel=1
arch=('any')
license=('CC BY-NC-SA 4.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-geometry-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-rostopic'
'ros-kinetic-std-msgs'
'ros-kinetic-visualization-msgs'
)

depends=('ros-kinetic-diagnostic-updater'
'ros-kinetic-geometry-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-twist-mux-msgs'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=twist_mux
source=()
md5sums=()

prepare() {
    cp -R $startdir/twist_mux $srcdir/twist_mux
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

