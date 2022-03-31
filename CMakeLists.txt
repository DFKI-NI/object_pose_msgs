cmake_minimum_required(VERSION 3.0.2)
project(object_pose_msgs)

add_compile_options(-std=c++17)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  geometry_msgs
  message_generation
)

add_message_files(
  DIRECTORY msg
  FILES
  ObjectPose.msg
  ObjectList.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

catkin_package(
  CATKIN_DEPENDS roscpp rospy geometry_msgs std_msgs message_runtime
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
