cmake_minimum_required(VERSION 3.0.2)
project(gazebo_simulator)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  gazebo_ros
  std_msgs
  tf
  genmsg
  gazebo_sfm_plugin
)

find_package(gazebo REQUIRED)

include_directories(
    ${Boost_INCLUDEDIR}
    ${catkin_INCLUDE_DIRS}
)

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)
install(DIRECTORY worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/worlds
)
install(DIRECTORY models
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/models
)
install(DIRECTORY urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/urdf
)
install(DIRECTORY meshes
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/meshes
)
install(DIRECTORY rviz
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/rviz
)

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch/hospital.launch)
endif()