cmake_minimum_required(VERSION 2.8.3)
project(drone_application)

## Find catkin and any catkin packages
find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs genmsg geometry_msgs tf)

## Declare a catkin package
catkin_package()

## Build talker and listener
include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(listener src/tf_listener1.cpp)
target_link_libraries(listener ${catkin_LIBRARIES})

add_executable(drone_application src/ar_outerloop_node.cpp)
#add_executable(drone_application1 src/ar_ol_new.cpp)
 target_link_libraries(
   drone_application
   ${catkin_LIBRARIES}
 )
