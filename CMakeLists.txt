cmake_minimum_required(VERSION 2.8.12)

project(stalker_ros_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    sensor_msgs
    std_msgs
    message_generation
)

add_message_files(
  FILES
    BoundingBox.msg
    TrackerResult.msg
)

add_service_files(
  FILES
    InitTracker.srv
)

generate_messages(
  DEPENDENCIES
    sensor_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    sensor_msgs
    std_msgs
    message_runtime
)