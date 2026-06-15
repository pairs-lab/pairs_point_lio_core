# pairs_point_lio_core

Metapackage that runs the PAIRS UAV system with Point-LIO LiDAR-inertial state
estimation. It ties together the Point-LIO odometry backend, the Livox LiDAR
driver, and the PAIRS estimator plugin, and ships the launch files, configs,
RViz layouts, Gazebo model, and ready-to-run tmux sessions for several LiDAR
rigs (Livox MID360, Ouster OS64).

## Contents

Aggregated component repositories (pulled into `ros_packages/` via `.gitman.yml`):
- `point_lio` — Point-LIO LiDAR-inertial odometry backend (bundles `ikd-Tree` and `IKFoM`).
- `livox_ros_driver2` — Livox LiDAR driver (bundles Livox-SDK2).
- `pairs_point_lio_estimator_plugin` — exposes Point-LIO odometry as a PAIRS state-estimation plugin.

`point_lio` and `livox_ros_driver2` are third-party packages kept under their
upstream names and shipped as separate `.deb` packages; they are not renamed to
`pairs_*`.

This package also provides:
- Launch files for simulation and bag replay (`point_lio_gazebo_mid360`, `point_lio_gazebo_os64`, `point_lio_livox_mid360`, `rosbag_core`, `rosbag_estimation_manager`, `rviz`).
- tmux sessions: `simulation/livox_mid360`, `simulation/ouster_os64`, `just_flying_point_lio`, `rosbag_estimation`.
- A Gazebo `x500_mid360` model and the matching PX4 airframe.

## Branches
- `ros1` — ROS 1 Noetic (catkin)
- `ros2` — ROS 2 Jazzy (ament_cmake)

## Install (ROS 1 Noetic)
```bash
sudo apt install ros-noetic-pairs-point-lio-core
```

## Usage

Run a Point-LIO simulation directly:

```bash
roslaunch pairs_point_lio_core point_lio_livox_mid360.launch
```

Or start a full tmux session, for example:

```bash
cd ros_packages/pairs_point_lio_core/tmux/simulation/livox_mid360 && ./simulation.sh
```

## License
BSD 3-Clause. Derived from the CTU-MRS `pairs_point_lio_core`; original copyright
retained in [LICENSE](LICENSE).
