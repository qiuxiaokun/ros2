# Understanding ROS 2 nodes
## 1. The ROS 2 graph  
The ROS graph is a network of ORS 2 elements processing data together at one time. It encompasses all executables and the connections between them if you were to map them all out and visualize them.


## 2. Nodes in ROS 2
在ROS中，每一个node都应该被设计为具有单一功能的node，比如控制电机的功能代码写在一个node，控制激光雷达的功能代码写在另一个node等；每一个node都能够通过topics、services、actions以及parameters与另一个node进行发送数据或者接收数据；一个完整的机器人系统包含许多node进行协同工作。在ROS 2中，一个可执行文件可以包含一个获多个node。


## 3. ros2 run
The command ***ros2 run*** launches an executable from a package.  
`ros2 run <package_name> <executable_name>`

## 4. ros2 ndoe list
***ros2 node list***命令可以输出当前所有在运行中的node名称。这条命令在你想要跟一个node进行互动，或者在你的系统中同时运行着许多node，而你需要实时跟踪它们的时候显得尤为重要。

## 5. Remapping
Remapping允许你使用custom values重新指定default node properties, like node name, topic names, service names, etc.

## 6. ros2 node info
Now that you know the names of your nodes, you can access more information about them with:  
`ros2 node info <node_name>`  
***ros2 node info*** returns a list of subscribers, publishers, and actions (the ROS graph connections) that interact with that node, The output should like this:

```
/my_turtle
  Subscribers:
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /turtle1/cmd_vel: geometry_msgs/msg/Twist
  Publishers:
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
    /turtle1/color_sensor: turtlesim/msg/Color
    /turtle1/pose: turtlesim/msg/Pose
  Services:
    /clear: std_srvs/srv/Empty
    /kill: turtlesim/srv/Kill
    /reset: std_srvs/srv/Empty
    /spawn: turtlesim/srv/Spawn
    /turtle1/set_pen: turtlesim/srv/SetPen
    /turtle1/teleport_absolute: turtlesim/srv/TeleportAbsolute
    /turtle1/teleport_relative: turtlesim/srv/TeleportRelative
    /my_turtle/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /my_turtle/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /my_turtle/get_parameters: rcl_interfaces/srv/GetParameters
    /my_turtle/list_parameters: rcl_interfaces/srv/ListParameters
    /my_turtle/set_parameters: rcl_interfaces/srv/SetParameters
    /my_turtle/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Action Servers:
    /turtle1/rotate_absolute: turtlesim/action/RotateAbsolute
  Action Clients:
```




