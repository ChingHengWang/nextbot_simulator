# Created Or Edited on: 09/07/2015
#     Author: Dott. Antonio Mauro Galiano
#		antoniomauro.galiano@gmail.com


cmake_minimum_required(VERSION 2.8.3)
project(nextbot_teleop)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS roscpp geometry_msgs joy)

include_directories(${catkin_INCLUDE_DIRS})

catkin_package(
  INCLUDE_DIRS
  CATKIN_DEPENDS roscpp geometry_msgs joy
  DEPENDS
)

###########
## Build ##
###########

add_executable(nextbot_teleop_key src/nextbot_teleop_key.cpp)
target_link_libraries(nextbot_teleop_key ${catkin_LIBRARIES})
#############
## Install ##
#############

## Mark executable scripts (Python etc.) for installation
install(PROGRAMS
  scripts/nextbot_teleop_key
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

## Mark executables and/or libraries for installation
#install(TARGETS nextbot_teleop_joy
#  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
#)

## Mark all other useful stuff for installation
install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
