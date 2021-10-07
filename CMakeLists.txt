cmake_minimum_required(VERSION 3.10.2)
project(dragoon_messages VERSION 0.0.1)
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-std=c++17 -pthread")

# since this is just a message package, no need to call the executables
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  sensor_msgs
  nav_msgs
  rostest
  rosunit
  actionlib_msgs
  geometry_msgs
)

add_message_files(
  FILES
  watchHeartbeat.msg
  watchStatus.msg
  ObjectInfo.msg
  Objects.msg
  driveCmd.msg
  stateCmd.msg
)

generate_messages(
  DEPENDENCIES actionlib_msgs std_msgs geometry_msgs
)

catkin_package(CATKIN_DEPENDS
  roscpp
  rospy
  std_msgs
  sensor_msgs
  nav_msgs
  tf
  geometry_msgs
  actionlib_msgs
)
