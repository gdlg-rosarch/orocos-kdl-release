# Script generated with Bloom
pkgdesc="ROS - This package depends on a recent version of the Kinematics and Dynamics Library (KDL), distributed by the Orocos Project. It is a meta-package that depends on kdl which contains the c++ version and pykdl which contains the generated python bindings."


pkgname='ros-lunar-orocos-kinematics-dynamics'
pkgver='1.3.1'_'1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-orocos-kdl'
'ros-lunar-python-orocos-kdl'
)

conflicts=()
replaces=()

_dir=orocos_kinematics_dynamics
source=()
md5sums=()

prepare() {
    cp -R $startdir/orocos_kinematics_dynamics $srcdir/orocos_kinematics_dynamics
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

