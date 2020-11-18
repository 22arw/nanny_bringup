cmake_minimum_required(VERSION 3.0.2)
project(nanny_bringup)

find_package(catkin REQUIRED COMPONENTS geometry_msgs roscpp tf)

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

# Nanny Listener
add_executable(nanny_tf_listener src/nanny_tf_listener.cpp)

if(geometry_msgs_EXPORTED_TARGETS)
  add_dependencies(nanny_tf_listener ${geometry_msgs_EXPORTED_TARGETS})
endif()

target_link_libraries(nanny_tf_listener ${catkin_LIBRARIES})

# Install the executable
install(TARGETS nanny_tf_broadcaster nanny_tf_listener
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})


