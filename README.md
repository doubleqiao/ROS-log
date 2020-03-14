# ROS-log
- 1.In the Ros launch file, the name of the node is the name you give while initializing the ROS node, 
and the type of the node is the name you give while adding executables in the CMakeLists.txt.

- 2.In order for the message to be used correctly in Rviz, the "msg.header.stamp = ros::Time::now()" may not be forgotten.

- 3.In the geometry_msgs/Quaternion type, the quaternion is expressed as a vector $[x,y,z,w]$. The quaternion can be expressed as w + x*i + y*j + z*k. The quaternion can be used to obtain the rotation matrix by using the formulas in [Quaternion and spatial rotation wiki](https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation). But pay attention to the symbol where a,b,c,d are used with the expression a + b*i + c*j + d*k.
