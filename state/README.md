# QQgdiw px4_msgs Hybrid/Rover state

- Repository: `https://github.com/QQgdiw/px4_msgs.git`.
- Upstream base: `PX4/px4_msgs` branch `release/1.16`, commit
  `392e831c1f659429ca83902e66820d7094591410`.
- Compatibility branch: `hybrid-rover-v1.16.1`.
- Firmware source: `QQgdiw/PX4-Autopilot` branch
  `feature/testc4-rover-tuning`, commit
  `7c4fb9e638787435351437c4dfc99e417adffd85`.
- Message files are a complete flattened synchronization of firmware
  `msg/*.msg` plus `msg/versioned/*.msg`; service files are synchronized from
  `srv/*.srv`, following the upstream px4_msgs manual-sync procedure.
- The companion Rover Offboard contract requires
  `OffboardControlMode.rover_velocity` and `RoverVelocitySetpoint` with signed
  body-forward speed in m/s and PX4-positive yaw rate in rad/s.
- MAVLink is a separate compatibility boundary. The matching firmware dialect
  remains `hybrid_vehicle` from `QQgdiw/mavlink` tag
  `qgc-hybrid-rover-tuning-v1.16.1-r1`, peeled commit
  `21922689c6fb113884df0f66582d8e602286fdc1`.
