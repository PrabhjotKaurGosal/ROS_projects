cmake_minimum_required(VERSION 3.0.2)
project(socially_compliant_navigation)

find_package(catkin REQUIRED COMPONENTS
  gazebo_ros
  joint_state_publisher
  robot_state_publisher
  roscpp
  rospy
  rviz
)

## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES hello_vs_code
#  CATKIN_DEPENDS roscpp rospy std_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

## Declare a C++ executable
add_executable(vs_talker src/talker.cpp)
add_executable(vs_listener src/listener.cpp)
add_executable(vs_listener2 src/listener2.cpp)

## Specify libraries to link a library or executable target against
# target_link_libraries(${PROJECT_NAME}_node
#   ${catkin_LIBRARIES}
# )
target_link_libraries(vs_talker
                      ${catkin_LIBRARIES})
target_link_libraries(vs_listener
                      ${catkin_LIBRARIES})
target_link_libraries(vs_listener2
                      ${catkin_LIBRARIES})




