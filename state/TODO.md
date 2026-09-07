# TODO

## 2026-09-07 Hybrid/Rover compatibility release

- [x] Create the `QQgdiw/px4_msgs` public fork from `PX4/px4_msgs`.
- [x] Create branch `hybrid-rover-v1.16.1` from upstream `release/1.16` at
      `392e831c1f659429ca83902e66820d7094591410`.
- [x] Synchronize all PX4 messages and services from firmware commit
      `7c4fb9e638787435351437c4dfc99e417adffd85`.
- [x] Verify 236/236 message files and 1/1 service file are byte-identical to
      the flattened firmware source; verify all message type dependencies and
      `git diff --check`.
- [ ] Run an actual `colcon build` in the companion ROS 2 environment; this
      WSL workspace does not have ROS 2 or `colcon` installed.
- [ ] Commit and push the branch, then publish an annotated immutable release
      tag `hybrid-rover-v1.16.1-r1`.
