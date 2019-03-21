cmake_minimum_required(VERSION 2.8.3)
project(gps)

add_compile_options(-std=c++11 -std=c++14)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  serial
)

catkin_package(
  CATKIN_DEPENDS
    roscpp
    rospy
    std_msgs
    serial
    sensor_msgs

)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(gps_serial src/gps_serial.cpp)
target_link_libraries(gps_serial ${catkin_LIBRARIES})

add_executable(gps_parse src/gps_parse.cpp src/gps_parse.cpp)
target_link_libraries(gps_parse ${catkin_LIBRARIES})
