# ROS-log
- 1.In the Ros launch file, the name of the node is the name you give while initializing the ROS node, 
and the type of the node is the name you give while adding executables in the CMakeLists.txt.

- 2.In order for the message to be used correctly in Rviz, the "msg.header.stamp = ros::Time::now()" may not be forgotten.

- 3.In the geometry_msgs/Quaternion type, the quaternion is expressed as a vector \[x,y,z,w\]. The quaternion can be written as w + x\***i** + y\***j** + z\***k**. This quaternion can be used to obtain the rotation matrix by using the formulas in [Quaternion and spatial rotation wiki](https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation). But pay attention to the sequence of the symbols where a,b,c,d are used with the expression a + b\***i** + c\***j** + d\***k**. Also, the relationship between four elements of the quaternion is a\^2 + b\^2 + c\^2 + d\^2 = 1.

Also, sometimes the RPY parameters are provided, and the rotation matrix can be calculated by using the expression: R = Rx\*Ry\*Rz. But note that the rotaion sequence is roll-pitch-yaw.
