cmake_minimum_required(VERSION 2.8.3)
project(luh_youbot_vrep_api)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  nav_msgs
  roscpp
  std_msgs
  std_srvs
  tf
  youbot_driver
  roslib
  luh_youbot_kinematics
  luh_youbot_driver_api
)

catkin_package(
 INCLUDE_DIRS include
 LIBRARIES luh_youbot_vrep_api
)

# include_directories(include)
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

## Declare a cpp library
add_library(luh_youbot_vrep_api
  #include/${PROJECT_NAME}/common.h
  include/${PROJECT_NAME}/youbot_interface.h
  src/youbot_interface.cpp
  include/${PROJECT_NAME}/arm_interface.h
  src/arm_interface.cpp
  include/${PROJECT_NAME}/base_interface.h
  src/base_interface.cpp
)

add_dependencies(luh_youbot_vrep_api luh_youbot_driver_api)
