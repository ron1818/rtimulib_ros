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

add_executable(rtimulib_ros src/rtimulib_ros.cpp)
target_link_libraries(rtimulib_ros
  ${catkin_LIBRARIES}
  RTIMULib
)
# add_executable(mpu9255_imu_ros src/mpu9255_imu_ros.cpp)
# add_executable(mpu9255_compass_ros src/mpu9255_compass_ros.cpp)
add_executable(rtimulib_imu_mag src/rtimulib_imu_mag.cpp)

target_link_libraries(rtimulib_imu_mag
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
