# QQgdiw px4_msgs Hybrid/Rover state

## 2026-10-29 local-heading release

- New branch: `hybrid-rover-local-heading-v1.16.1`; release annotated tag
  `hybrid-rover-v1.16.1-r2` (r1 must not move).
- Published r2 peeled commit `3b569db54de24ff3e7311ccb407693975f5601f6`, matched
  PX4 firmware `2f04e0cf2aa7b6c4a2a8588d6fd1b8d4b9a92512`; remote refs verified.
- VehicleLocalPosition v1 adds heading_good_for_local_control. DDS topic gains
  `_v1`; r1 is not automatically compatible. Existing MAVLink is unchanged.
- Complete flattened message/service comparison against current testc4 firmware
  passed. ROS/colcon and live DDS verification remain companion-side tasks.
- Server-side protection for the new tag has not been verified; do not infer
  immutability enforcement from the annotation or r1 ruleset.

## Historical r1 release

- Repository: `https://github.com/QQgdiw/px4_msgs.git`.
- Upstream base: `PX4/px4_msgs` branch `release/1.16`, commit
  `392e831c1f659429ca83902e66820d7094591410`.
- Compatibility branch: `hybrid-rover-v1.16.1`.
- Immutable compatibility tag: `hybrid-rover-v1.16.1-r1`, annotated tag object
  `6c0f64065af728ea1013e33793648dab7821e789`, peeled message commit
  `e0f41fb57ed9217ba15730854f6c7c92b0262134`.
- GitHub ruleset `22433564` is active for that exact tag and prohibits deletion
  and non-fast-forward updates.
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
