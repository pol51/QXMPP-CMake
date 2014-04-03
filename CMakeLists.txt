cmake_minimum_required(VERSION 2.8.11)

project(qxmpp)



################################################################################
# Qt5
################################################################################
set(CMAKE_AUTOMOC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
find_package(Qt5Core REQUIRED)
find_package(Qt5Network REQUIRED)
find_package(Qt5Xml REQUIRED)
################################################################################



################################################################################
# qxmpp
################################################################################
file(GLOB_RECURSE qxmpp_cpp src/QXmpp*.cpp)
file(GLOB_RECURSE qxmpp_h src/QXmpp*.h)

include_directories(src/base src/client)
add_library(qxmpp SHARED ${qxmpp_cpp} ${qxmpp_h})

target_link_libraries(qxmpp Qt5::Core Qt5::Xml Qt5::Network)
################################################################################
