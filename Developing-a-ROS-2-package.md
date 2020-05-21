# Developing a ROS 2 package

1. Creating a package

  `ros2 pkg create <pkg-name> --dependencies <deps> --build-type ament-cmake`

    You can then update the package.xml with your package info such as dependencies,
    and authorship.

2. Config

    You will mostly use the `add_executable()` CMake macro along with

`ament_target_dependencies(<executable-name> [dependencies])`

    to create executable nodes and link dependencies.

    To install your launch files and nodes, you can use the `install()` macro placed
    towards the end of the file but before the `ament_package()` macro.
    An example for launch files and nodes:
```
# Install launch files
install(
  DIRECTORY launch
  DESTINATION share/${PROJECT_NAME}
)

# Install nodes
install(
  TARGETS [node-names]
  DESTINATION lib/${PROJECT_NAME}
)
```
