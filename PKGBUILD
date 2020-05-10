# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - ROS communications-related packages, including core client libraries (roscpp, rospy) and graph introspection tools (rostopic, rosnode, rosservice, rosparam)."
url='https://wiki.ros.org/ros_comm'

pkgname='ros-noetic-ros-comm'
pkgver='1.15.4'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=1
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-std-srvs
	ros-noetic-rosbag
	ros-noetic-rosmsg
	ros-noetic-rosout
	ros-noetic-rosparam
	ros-noetic-topic-tools
	ros-noetic-rosgraph
	ros-noetic-message-filters
	ros-noetic-rospy
	ros-noetic-ros
	ros-noetic-roslisp
	ros-noetic-roswtf
	ros-noetic-rosmaster
	ros-noetic-rostopic
	ros-noetic-rosconsole
	ros-noetic-roscpp
	ros-noetic-xmlrpcpp
	ros-noetic-rostest
	ros-noetic-rosnode
	ros-noetic-rosgraph-msgs
	ros-noetic-roslaunch
	ros-noetic-rosservice
)

depends=(
	${ros_depends[@]}
)

_dir="ros_comm-${pkgver}/ros_comm"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/ros_comm/archive/${pkgver}.tar.gz")
sha256sums=('d5c96a81e0c8554b77666bca5dcc68e03083a761a117038ff9b65f9643751c9e')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCMAKE_BUILD_TYPE=Release \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python3 \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
