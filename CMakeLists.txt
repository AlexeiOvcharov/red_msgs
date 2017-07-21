cmake_minimum_required(VERSION 2.8.3)
project(red_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  roscpp
  rospy
  std_msgs
  actionlib_msgs
  geometry_msgs
)

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  Object.msg
  ListObjects.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  CameraStop.srv
  CameraTask.srv
  ManipulationObjects.srv
  GetRange.srv
)

## Generate actions in the 'action' folder
add_action_files(
  DIRECTORY action
  FILES Dest.action
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
  actionlib_msgs
)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
  CATKIN_DEPENDS roscpp rospy std_msgs
)

# include_directories(include)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
