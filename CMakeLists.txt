cmake_minimum_required(VERSION 3.0.2)
project(nanny_bringup)

find_package(catkin REQUIRED COMPONENTS geometry_msgs roscpp tf tf2_ros)

catkin_package()

###########
## Build ##
###########

include_directories(${catkin_INCLUDE_DIRS})

# Nanny Broadcaster
add_executable(nanny_tf_broadcaster src/nanny_tf_broadcaster.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(nanny_tf_broadcaster ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(nanny_tf_broadcaster ${catkin_LIBRARIES})

# Nanny Base_link Broadcaster
add_executable(nanny_base_link_tf_br src/nanny_base_link_tf_br.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(nanny_base_link_tf_br ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(nanny_base_link_tf_br ${catkin_LIBRARIES})

# Nanny Listener
add_executable(nanny_tf_listener src/nanny_tf_listener.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(nanny_tf_listener ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(nanny_tf_listener ${catkin_LIBRARIES})

# Nanny Base Link Listener
add_executable(nanny_base_link_tf_ls src/nanny_base_link_tf_ls.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(nanny_base_link_tf_ls ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(nanny_base_link_tf_ls ${catkin_LIBRARIES})

#front laser broadcaster
add_executable(nanny_front_laser_tf_br src/nanny_front_laser_tf_br.cpp)
target_link_libraries(nanny_front_laser_tf_br
 ${catkin_LIBRARIES}
)
#rear laser broadcaster
add_executable(nanny_rear_laser_tf_br src/nanny_rear_laser_tf_br.cpp)
target_link_libraries(nanny_rear_laser_tf_br
 ${catkin_LIBRARIES}
)
#left wheel broadcaster
add_executable(nanny_left_wheel_tf_br src/nanny_left_wheel_tf_br.cpp)
target_link_libraries(nanny_left_wheel_tf_br
 ${catkin_LIBRARIES}
)
#right wheel broadcaster
add_executable(nanny_right_wheel_tf_br src/nanny_right_wheel_tf_br.cpp)
target_link_libraries(nanny_right_wheel_tf_br
 ${catkin_LIBRARIES}
)
#front left swivel broadcaster
add_executable(nanny_front_left_swivel_tf_br src/nanny_front_left_swivel_tf_br.cpp)
target_link_libraries(nanny_front_left_swivel_tf_br
 ${catkin_LIBRARIES}
)
#front right swivel broadcaster
add_executable(nanny_front_right_swivel_tf_br src/nanny_front_right_swivel_tf_br.cpp)
target_link_libraries(nanny_front_right_swivel_tf_br
 ${catkin_LIBRARIES}
)
#front right caster broadcaster
add_executable(nanny_front_right_caster_tf_br src/nanny_front_right_caster_tf_br.cpp)
target_link_libraries(nanny_front_right_caster_tf_br
 ${catkin_LIBRARIES}
)
#front left caster broadcaster
add_executable(nanny_front_left_caster_tf_br src/nanny_front_left_caster_tf_br.cpp)
target_link_libraries(nanny_front_left_caster_tf_br
 ${catkin_LIBRARIES}
)
#back left swivel broadcaster
add_executable(nanny_back_left_swivel_tf_br src/nanny_back_left_swivel_tf_br.cpp)
target_link_libraries(nanny_back_left_swivel_tf_br
 ${catkin_LIBRARIES}
)
#back right swivel broadcaster
add_executable(nanny_back_right_swivel_tf_br src/nanny_back_right_swivel_tf_br.cpp)
target_link_libraries(nanny_back_right_swivel_tf_br
 ${catkin_LIBRARIES}
)
#back right caster broadcaster
add_executable(nanny_back_right_caster_tf_br src/nanny_back_right_caster_tf_br.cpp)
target_link_libraries(nanny_back_right_caster_tf_br
 ${catkin_LIBRARIES}
)
#back left caster broadcaster
add_executable(nanny_back_left_caster_tf_br src/nanny_back_left_caster_tf_br.cpp)
target_link_libraries(nanny_back_left_caster_tf_br
 ${catkin_LIBRARIES}
)
#back left caster broadcaster
add_executable(nanny_imu_tf_br src/nanny_imu_tf_br.cpp)
target_link_libraries(nanny_imu_tf_br
 ${catkin_LIBRARIES}
)

#front camera broadcaster
add_executable(nanny_front_camera_tf_br src/nanny_front_camera_tf_br.cpp)
target_link_libraries(nanny_front_camera_tf_br
 ${catkin_LIBRARIES}
)

#rear camera broadcaster
add_executable(nanny_rear_camera_tf_br src/nanny_rear_camera_tf_br.cpp)
target_link_libraries(nanny_rear_camera_tf_br
 ${catkin_LIBRARIES}
)

#front laser listener
add_executable(nanny_front_laser_tf_ls src/nanny_front_laser_tf_ls.cpp)
target_link_libraries(nanny_front_laser_tf_ls
 ${catkin_LIBRARIES}
)
#rear laser listener
add_executable(nanny_rear_laser_tf_ls src/nanny_rear_laser_tf_ls.cpp)
target_link_libraries(nanny_rear_laser_tf_ls
 ${catkin_LIBRARIES}
)
#left wheel listener
add_executable(nanny_left_wheel_tf_ls src/nanny_left_wheel_tf_ls.cpp)
target_link_libraries(nanny_left_wheel_tf_ls
 ${catkin_LIBRARIES}
)
#right wheel listener
add_executable(nanny_right_wheel_tf_ls src/nanny_right_wheel_tf_ls.cpp)
target_link_libraries(nanny_right_wheel_tf_ls
 ${catkin_LIBRARIES}
)
#front left swivel listener
add_executable(nanny_front_left_swivel_tf_ls src/nanny_front_left_swivel_tf_ls.cpp)
target_link_libraries(nanny_front_left_swivel_tf_ls
 ${catkin_LIBRARIES}
)
#front right swivel listener
add_executable(nanny_front_right_swivel_tf_ls src/nanny_front_right_swivel_tf_ls.cpp)
target_link_libraries(nanny_front_right_swivel_tf_ls
 ${catkin_LIBRARIES}
)
#front right caster listener
add_executable(nanny_front_right_caster_tf_ls src/nanny_front_right_caster_tf_ls.cpp)
target_link_libraries(nanny_front_right_caster_tf_ls
 ${catkin_LIBRARIES}
)
#front left caster listener
add_executable(nanny_front_left_caster_tf_ls src/nanny_front_left_caster_tf_ls.cpp)
target_link_libraries(nanny_front_left_caster_tf_ls
 ${catkin_LIBRARIES}
)
#back left swivel listener
add_executable(nanny_back_left_swivel_tf_ls src/nanny_back_left_swivel_tf_ls.cpp)
target_link_libraries(nanny_back_left_swivel_tf_ls
 ${catkin_LIBRARIES}
)
#back right swivel listener
add_executable(nanny_back_right_swivel_tf_ls src/nanny_back_right_swivel_tf_ls.cpp)
target_link_libraries(nanny_back_right_swivel_tf_ls
 ${catkin_LIBRARIES}
)
#back right caster listener
add_executable(nanny_back_right_caster_tf_ls src/nanny_back_right_caster_tf_ls.cpp)
target_link_libraries(nanny_back_right_caster_tf_ls
 ${catkin_LIBRARIES}
)
#back left caster listener
add_executable(nanny_back_left_caster_tf_ls src/nanny_back_left_caster_tf_ls.cpp)
target_link_libraries(nanny_back_left_caster_tf_ls
 ${catkin_LIBRARIES}
)
#imu listener
add_executable(nanny_imu_tf_ls src/nanny_imu_tf_ls.cpp)
target_link_libraries(nanny_imu_tf_ls
 ${catkin_LIBRARIES}
)

# Install the executable
install(TARGETS nanny_tf_broadcaster nanny_base_link_tf_br nanny_front_laser_tf_br nanny_rear_laser_tf_br nanny_left_wheel_tf_br nanny_right_wheel_tf_br nanny_front_left_swivel_tf_br nanny_front_right_swivel_tf_br nanny_front_right_caster_tf_br nanny_front_left_caster_tf_br nanny_back_left_swivel_tf_br nanny_back_right_swivel_tf_br nanny_back_right_caster_tf_br nanny_back_left_caster_tf_br nanny_tf_listener nanny_base_link_tf_ls  nanny_front_laser_tf_ls nanny_rear_laser_tf_ls nanny_left_wheel_tf_ls nanny_right_wheel_tf_ls nanny_front_left_swivel_tf_ls nanny_front_right_swivel_tf_ls nanny_front_right_caster_tf_ls nanny_front_left_caster_tf_ls nanny_back_left_swivel_tf_ls nanny_back_right_swivel_tf_ls nanny_back_right_caster_tf_ls nanny_back_left_caster_tf_ls nanny_imu_tf_ls nanny_front_camera_tf_br nanny_rear_camera_tf_br
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})


