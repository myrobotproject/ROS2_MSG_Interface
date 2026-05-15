cmake_minimum_required(VERSION 3.13)
project(gnss_comm)

# cmake_minimum_required(VERSION 2.8.3)
# project(gnss_comm)
# set(CMAKE_BUILD_TYPE "release")
# set(CMAKE_CXX_FLAGS "-std=c++11 ")
# set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -fPIC")

set(CMAKE_BUILD_TYPE "Release")
# set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -g")

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  # msg
  "msg/GnssTimeMsg.msg"
  "msg/GnssEphemMsg.msg"
  "msg/GnssGloEphemMsg.msg"
  "msg/GnssObsMsg.msg"
  "msg/GnssMeasMsg.msg"
  msg/GnssBestXYZMsg.msg
  msg/GnssPVTSolnMsg.msg
  msg/GnssSvsMsg.msg
  msg/GnssTimePulseInfoMsg.msg
  msg/StampedFloat64Array.msg
  msg/LocalSensorExternalTrigger.msg
  DEPENDENCIES std_msgs
)

ament_export_dependencies(rosidl_default_runtime std_msgs)

ament_package()
