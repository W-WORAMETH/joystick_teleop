cmake_minimum_required(VERSION 2.8.3)
project(joystick_teleop)

set (CMAKE_CXX_STANDARD 11)

set (MAIN_SRC "${CMAKE_SOURCE_DIR}")
set (JOYSTICK_TELEOP "${MAIN_SRC}/joystick_teleop")
set (JOYSTICK_SRC "${JOYSTICK_TELEOP}/src")

message("===========================")
message(${JOYSTICK_SRC})

find_package(catkin REQUIRED COMPONENTS std_msgs geometry_msgs roscpp)

catkin_package(INCLUDE_DIRS include)

include_directories(include "${catkin_INCLUDE_DIRS}")


add_executable(
	joystick_teleop_node
	${JOYSTICK_SRC}/joystick_teleop
	${JOYSTICK_SRC}/joystick
	)


target_link_libraries(joystick_teleop_node ${catkin_LIBRARIES})
add_dependencies(joystick_teleop_node ${catkin_EXPORTED_TARGETS})

