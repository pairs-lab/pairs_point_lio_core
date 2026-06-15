# pairs_point_lio_core

**PAIRS Point-LIO core** metapackage. Runs the PAIRS UAV system with Point-LIO LiDAR-inertial
state estimation (launch / config / rviz / tmux for several LiDAR rigs).

The LiDAR-odometry backend `point_lio` (HKU Point-LIO, CTU fork; bundles the
`ikd-Tree` and `IKFoM` submodules) and the LiDAR driver `livox_ros_driver2`
(bundles Livox-SDK2) are kept under their upstream names (third-party) and
provided as separate `.deb` packages — they are NOT renamed to `pairs_*`.

Component repositories are managed via `ros_packages/.gitman.yml` (`gitman install`).

## Branches
- `ros1` — ROS 1 Noetic (catkin)
- `ros2` — ROS 2 Jazzy (ament_cmake)

## License
BSD 3-Clause. Derived from the CTU-MRS `pairs_point_lio_core`; original copyright
retained in [LICENSE](LICENSE).