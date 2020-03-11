# ROS-log
-1. In the Ros launch file, the name of the node is the name you give while initializing the ROS node, 
and the type of the node is the name you give while adding executables in the CMakeLists.txt.
-2. In order for the message to be used correctly in Rviz, the "msg.header.stamp = ros::Time::now()" may not be forgotten.
