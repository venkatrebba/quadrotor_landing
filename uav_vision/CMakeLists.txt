cmake_minimum_required(VERSION 2.8.3)
project(uav_vision)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  sensor_msgs
  std_msgs
  geometry_msgs
  OpenCV
  image_view
  tf
  std_srvs
  cvg_sim_msgs
  ardrone_autonomy
)

## System dependencies are found with CMake's conventions
find_package(Boost REQUIRED COMPONENTS system)
find_package(Boost REQUIRED COMPONENTS thread)

## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
 CATKIN_DEPENDS 
  cv_bridge 
  image_transport 
  roscpp 
  sensor_msgs
  std_msgs
  geometry_msgs
  image_view
  tf
  std_srvs
  cvg_sim_msgs
  ardrone_autonomy
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(${catkin_INCLUDE_DIRS})
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(${Boost_INCLUDE_DIRS})


#########################################################################################################
# platform_detection NODE
add_executable(platform_detection src/platform_detection.cpp)
target_link_libraries(platform_detection ${catkin_LIBRARIES} ${OpenCV_LIBRARIES})

#########################################################################################################
# platform_tracking NODE
add_executable(platform_tracking src/platform_tracking.cpp)
target_link_libraries(platform_tracking ${catkin_LIBRARIES} ${OpenCV_LIBRARIES})
