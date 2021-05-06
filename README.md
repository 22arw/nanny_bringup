# nanny_bringup
<h3>SRC</h3> 
The src folder contains transform frames.  Transform frames keep track of coordinate frames overtime by putting them in a tree like structure.
Transform frames can be created in matlab using the tf2_ros tool

<h3>Launch</h3>
This folder contains launch files.  To launch a file, in the terminal type roslaunch <folder name> <launch file name>
  </br>
coach_nanny_robot_gazebo.launch - launches the starting pen environment in gazebo
  </br>
coach_nanny_robot_rviz_bringup.launch - launches rviz with the robot
 </br>
nanny_robot_full_sim.launch - launches the store, the robot, gmapping, localization, and rviz
  </br>
nanny_robot_gmap_grocery.launch - launches the store, the robot, and gmapping
 </br>
nanny_robot_localization.launch - launches the store, the robot, and the amcl localization
 </br>
nanny_robot_store_world.launch - launches the robot and store in gazebo
 </br>
nanny_robot_tfs.launch - file for all the transform frames. You can add these to other launch files using: 
</br>
<p><include file="$(find nanny_bringup)/launch/nanny_robot_tfs.launch"/></p>

<h3>Transform frames</h3>
Tf(transform frames) is a package that lets the user keep track of multiple coordinate frames over time. Tf maintains the relationship between coordinate frames in a tree structure buffered in time, and lets the user transform points, vectors, etc between any two coordinate frames at any desired point in time.
These transform frames allow us to keep track of parts of our robot in relation to the odometry in our world by using broadcasters and listeners. Broadcasters can relay useful information about our frame, such as the relative pose of coordinate frames to the rest of the system. Listeners allow us to receive this information and buffer these frames that are broadcasted, we can then query for specific transforms between different frames and have them behave as we wish at certain poses/transforms (which in turn can affect other transform frames).

CMakeList.txt - everytime you add a new broadcaster/listener, you need to add it to the CMakeList
#front laser broadcaster
add_executable(nanny_front_laser_tf_br src/nanny_front_laser_tf_br.cpp)
target_link_libraries(nanny_front_laser_tf_br
 ${catkin_LIBRARIES}
)
 
#front laser listener
add_executable(nanny_front_laser_tf_ls src/nanny_front_laser_tf_ls.cpp)
target_link_libraries(nanny_front_laser_tf_ls
 ${catkin_LIBRARIES}
)
 
install(TARGETS nanny_front_laser_tf_br nanny_front_laser_tf_ls
