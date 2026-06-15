# pairs_point_lio_core

Metapackage that runs the PAIRS UAV system with Point-LIO LiDAR-inertial state
estimation. It ties together the Point-LIO odometry backend, the Livox LiDAR
driver, and the PAIRS estimator plugin, and ships the configs, RViz layouts, and
ready-to-run tmux sessions for simulation and real-world flights.

## Contents

Aggregated component repositories (pulled into `ros_packages/` via `.gitman.yml`):
- `point_lio` — Point-LIO LiDAR-inertial odometry backend (bundles `ikd-Tree` and `IKFoM`).
- `livox_ros_driver2` — Livox LiDAR driver (bundles Livox-SDK2).
- `pairs_point_lio_estimator_plugin` — exposes Point-LIO odometry as a PAIRS state-estimation plugin.

`point_lio` and `livox_ros_driver2` are third-party packages kept under their
upstream names and shipped as separate `.deb` packages; they are not renamed to
`pairs_*`.

This package also provides tmux sessions: `gazebo`, `flightforge`, and
`realworld_mid360`.

## Branches
- `ros1` — ROS 1 Noetic (catkin)
- `ros2` — ROS 2 Jazzy (ament_cmake)

## Install (ROS 2 Jazzy)
```bash
sudo apt install ros-jazzy-pairs-point-lio-core
```

## Usage

Start a tmux session, for example the Gazebo simulation:

```bash
cd ros_packages/pairs_point_lio_core/tmux/gazebo && ./start.sh
```

## License
BSD 3-Clause. Derived from the CTU-MRS `pairs_point_lio_core`; original copyright
retained in [LICENSE](LICENSE).
