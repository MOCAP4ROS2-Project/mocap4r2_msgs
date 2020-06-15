cmake_minimum_required(VERSION 3.5)
project(mocap4ros_msgs)

find_package(ament_cmake)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

set(msg_files
  "msg/Marker.msg"
  "msg/Markers.msg"
)

set(srv_files
  "srv/ViconCalibSeg.srv"
  "srv/ViconGrabPose.srv"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  ${srv_files}
  DEPENDENCIES builtin_interfaces std_msgs geometry_msgs
)

ament_export_dependencies(rosidl_default_runtime std_msgs geometry_msgs)
ament_package()
