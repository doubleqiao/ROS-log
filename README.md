# ROS-log
- 1.In the Ros launch file, the name of the node is the name you give while initializing the ROS node, 
and the type of the node is the name you give while adding executables in the CMakeLists.txt.

- 2.In order for the message to be used correctly in Rviz, the "msg.header.stamp = ros::Time::now()" may not be forgotten.

- 3.In the **geometry_msgs/Quaternion** type, the quaternion is expressed as a vector \[x,y,z,w\]. The quaternion can be written as:
    <pre>
    w + x*<b>i</b> + y*<b>j</b> + z*<b>k</b>. 
    </pre>
    
    This quaternion can be used to obtain the rotation matrix by using the formulas in [Quaternion and spatial rotation wiki](https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation). But pay attention to the sequence of the symbols where a,b,c,d are used with the expression 
    <pre>
    a + b*<b>i</b> + c*<b>j</b> + d*<b>k</b>. 
    </pre>
    
    Also, the relationship between four elements of the quaternion is:  
    <pre>
    a^2 + b^2 + c^2 + d^2 = 1.  
    </pre>

    Sometimes the RPY parameters are provided, and the rotation matrix can be calculated by using the expression: R = Rx\*Ry\*Rz. But note that the rotaion sequence is roll-pitch-yaw.

- 4.In ROS, a node can be started by using two methods:
     - command line: 
     ```
     rosrun pkg_name binary_file_name 
     ```
     The binary_file_name is actually the name of the executable generated. Its name is defind in CMakeLists.tex with the line:
     ```
     add_executable($binary_file_name src/XXX.cpp).
     ```
     The name of the node in the graph generated by using the rqt_graph tool is defined by the line 
     ```
     ros::init(argc, argv, "node_name")
     ```
     in the source file.
     Using this method, the ros master should be started first by typing 
     ```
     roscore
     ```
     - launch file: The node can be started in the launch file by using the line:
     ```
     <node pkg="package_name", type="binary_file_name", name="node_name_defined_by_yourself" />". 
     ```
     In this case, the name in the node tag is the name of the node shown in the rqt_graph, and it can be totally different from the node name you defined in the source file by uisng 
     ```
     init(argc, argv, "node_name")".
     ```
     The name you defined in the launch file will be the final one shown in the rqt_graph. In addition, by using the launch file, the roscore will be automatically started.  
     
     It seems that the "launch" method has relatively higher level.
