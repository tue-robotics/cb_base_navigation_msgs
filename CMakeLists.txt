cmake_minimum_required(VERSION 2.8.3)
project(cb_base_navigation_msgs)

find_package(catkin REQUIRED COMPONENTS
  actionlib
  actionlib_msgs
  geometry_msgs
  message_generation
  std_msgs
)

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  PositionConstraint.msg
  OrientationConstraint.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  GetPlan.srv
  CheckPlan.srv
)

## Generate actions in the 'action' folder
add_action_files(
  FILES
  LocalPlanner.action
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  actionlib_msgs
  geometry_msgs
)

###################################
## catkin specific configuration ##
###################################
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES cb_base_navigation_msgs
   CATKIN_DEPENDS actionlib actionlib_msgs geometry_msgs message_runtime std_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
# include_directories(include)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
