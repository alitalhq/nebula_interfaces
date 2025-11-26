cmake_minimum_required(VERSION 3.8)
project(nebula_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/GimbalCommand.msg"
  "msg/GimbalMotorFeedback.msg"
  "msg/GimbalStatus.msg"
  "msg/OpState.msg"
  "msg/Target.msg"
  "msg/TargetArray.msg"
  "msg/UiMouseTarget.msg"
  "srv/FireCommand.srv"
  "srv/SetMode.srv"
  DEPENDENCIES std_msgs
)

ament_export_dependencies(rosidl_default_runtime)
ament_package()
