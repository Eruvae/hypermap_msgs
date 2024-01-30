cmake_minimum_required(VERSION 3.3)
project(hypermap_msgs)

set(CMAKE_CXX_STANDARD 14)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

set(msg_files
  "msg/LayerMetaData.msg"
  "msg/HypermapMetaData.msg"
  "msg/SemanticObject.msg"
  "msg/SemanticMap.msg"
  "msg/SemanticMapUpdate.msg"
)

set(srv_files
  "srv/GetIntAtPoint.srv"
  "srv/GetIntsByArea.srv"
  "srv/GetLocationsByInt.srv"
  "srv/GetLocationsByString.srv"
  "srv/GetSemanticByArea.srv"
  "srv/GetSemanticByString.srv"
  "srv/GetStringAtPoint.srv"
  "srv/GetStringsByArea.srv"
  "srv/LoadMap.srv"
  "srv/StoreMap.srv"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  ${srv_files}
  DEPENDENCIES std_msgs geometry_msgs
)

ament_export_dependencies(std_msgs geometry_msgs)

ament_package()