Functional requirements:

* functionality and API equivalent to ROS2 C++ client library (C++ client library has most advanced feature set right now)
  * Reference - C++ client library: [rclcpp](https://github.com/ros2/rclcpp)
* functionality equivalent to ROS2 C++ client library (C++ client library user code depends on idl generator)
  * Reference - C++ idl generator: [rosidl_generator_cpp](https://github.com/ros2/rosidl/tree/master/rosidl_generator_cpp)

Non-functional requirements:

* integration of tool based static code analysis into build tool (other client libraries aim at integration of tools extensively)
  * C++ client library reference: integration of CppCheck (common code flaw checking) into Ament (non-/CMake based) built environment for C++ client library [ament_cppcheck](https://github.com/ament/ament_lint/tree/master/ament_cppcheck) / [ament_cmake_cppcheck](https://github.com/ament/ament_lint/tree/master/ament_cmake_cppcheck)
  * C++ client library reference: integration of CppLint and clang format (style guide checking) into Ament (non-/CMake based) build environment for C++ client library [ament_cpplint](https://github.com/ament/ament_lint/tree/master/ament_cpplint) / [ament_cmake_cpplint](https://github.com/ament/ament_lint/tree/master/ament_cmake_cpplint) / [ament_clang_format](https://github.com/ament/ament_lint/tree/master/ament_clang_format)
* design by contract (C++ does not support this but will probably support it if ROS2 begins to support C++17)
* unit tests (other client libraries aim at extensive unit testing as well)
  * C++ client library reference: [rclcpp/test](https://github.com/ros2/rclcpp/tree/master/rclcpp/test)
* rmw (ROS2 middleware) integration tests (C++ client library aims at extensive middleware integration testing as well)
  * C++ client library reference: [system_tests/test_communication](https://github.com/ros2/system_tests/tree/master/test_communication)
  * test of communiaction (publish/subscribe/request/response)
  * test with all primitive and builtin types
  * test with every available rmw implementation
* security tests (C++ client library aims at extensive security testing):
  * C++ client library reference: [system_tests/test_security](https://github.com/ros2/system_tests/tree/master/test_security))
  * test nodes, publishers and subscribers with DDS-Security
* API tests (other client libraries like C++ client library aims at extensive API testing as well)
  * [C++ client library API tests](https://github.com/ros2/system_tests/tree/master/test_rclcpp)
  * Reference - ROS2 launch (test runner): [launch](https://github.com/ros2/launch/tree/master/launch)
  * Reference - Helper scripts for tests using the launch tool: [launch_testing](https://github.com/ros2/launch/tree/master/launch_testing)
* code coverage (right now Danalyze supports statement coverage)
* support for real-time

# ROS2 Architecture

How a client library (here: C++) fits into the big picture.

![](diagrams/ros2_layer_pattern.png)

![](diagrams/ros2_hour_glass_pattern_generic.png)

![](diagrams/ros2_hour_glass_pattern_cpp.png)

[ROS-I Consortium 2017 Presentation: Looking forward to ROS2](https://static1.squarespace.com/static/51df34b1e4b08840dcfd2841/t/598be660f9a61ea2b0da7bac/1502340717919/4_ROS-I+AP+Consortium+Presentation+ROS2+Tully.pdf)
