# Ament_cmake user documentation

  ### 1. Basic
  A basic CMake outline can be produced using `ros2 pkg create <package_name>`
  on the command line. The basic build infomation is then gathered in two files:
  the *package.xml* and the *CMakelists.txt*. The *package.xml* must contain all
  dependencies and a bit of metadata to allow colcon to find the correct build
  order for your packages, to install the your requireddependencies in CI as well
  as provide the information for a release with *bloom*. The *CMakelists.txt*
  contains the commands to build and package executables and libraries and
  will be the main focus of this documentation.

  ### 2. basic project outline
  The basic outline of the *CMakelists.txt* of an ament package contains:
  ```
  cmake_mininum_required(VERSION 3.5)
  project(my_project)

  ament_package()
  ```
  The argument to *project* will be the project name and must be identical to the
  package name in the *package.xml*
  The project setup is done by **ament_package()** and this call must occur exactly once per package. *ament_package()* installs the package.xml, registers
  the package with the ament index, and installs config (and possibly target) files for CMake so that it can be found by other packages using **find_package**. Since *ament_package()* gathers a lot of information from the
  *CMakelists.txt* it should be the last call in your *CMakelists.txt*. Although
  it is possible to follow calls to *ament_package()* by calls to install functions coping files and directions, it is simpler to just keep *ament_package()* the last call.

  3.
