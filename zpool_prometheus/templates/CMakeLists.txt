cmake_minimum_required(VERSION 3.7)
project(zpool_prometheus C)

# by default Ubuntu installs the header files and libraries in /usr
# be sure to (apt) install the header files package, libzfslinux-dev
set(INSTALL_DIR /usr)
set(CMAKE_C_STANDARD 11)

include_directories(${INSTALL_DIR}/include/libspl ${INSTALL_DIR}/include/libzfs)
link_directories(${INSTALL_DIR}/lib)
add_executable(zpool_prometheus
        zpool_prometheus.c)
target_link_libraries(zpool_prometheus zfs nvpair)
install(TARGETS zpool_prometheus DESTINATION ${INSTALL_DIR}/bin)

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_SHLIBDEPS "ON")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "RE")
INCLUDE(CPack)