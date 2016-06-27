cmake_minimum_required(VERSION 2.8.3)
project(rtimulib_ros)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  sensor_msgs
)

catkin_package(
    LIBRARIES rtimulib_ros
    CATKIN_DEPENDS roscpp sensor_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

#add_executable(rtimulib_ros src/rtimulib_ros.cpp)
# add_executable(mpu9255_imu_ros src/mpu9255_imu_ros.cpp)
# add_executable(mpu9255_compass_ros src/mpu9255_compass_ros.cpp)
add_executable(mpu9255_ros src/mpu9255_ros.cpp)

target_link_libraries(mpu9255_ros
  ${catkin_LIBRARIES}
  RTIMULib
)

# target_link_libraries(mpu9255_imu_ros
#   ${catkin_LIBRARIES}
#   RTIMULib
# )
# 
# 
# target_link_libraries(mpu9255_compass_ros
#   ${catkin_LIBRARIES}
#   RTIMULib
# )
