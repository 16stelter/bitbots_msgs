cmake_minimum_required(VERSION 3.5)
project(bitbots_msgs)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(actionlib_msgs REQUIRED)
#find_package(bitbots_docs REQUIRED)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Buttons.msg"
  "msg/ColorLookupTable.msg"
  "msg/Config.msg"
  "msg/Cpu.msg"
  "msg/FloatStamped.msg"
  "msg/Filesystem.msg"
  "msg/FootPressure.msg"
  "msg/JointCommand.msg"
  "msg/JointTorque.msg"
  "msg/NetworkInterface.msg"
  "msg/Workload.msg"
  "srv/AccelerometerCalibration.srv"
  "srv/ComplementaryFilterParams.srv"
  "srv/FootScale.srv"
  "srv/IMURanges.srv"
  "srv/Leds.srv"
  "srv/ManualPenalize.srv"
  "srv/SetAccelerometerCalibrationThreshold.srv"
  "srv/SetObjectPose.srv"
  "srv/SetObjectPosition.srv"
  "action/Dynup.action"
  "action/Kick.action"
  DEPENDENCIES
  actionlib_msgs
  sensor_msgs
  std_msgs
)

#include(${CMAKE_BINARY_DIR}/../bitbots_docs/enable_bitbots_docs.cmake)
#enable_bitbots_docs()

ament_package()
