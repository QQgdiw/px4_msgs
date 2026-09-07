# Engineering log

## 2026-09-07 Initial Hybrid/Rover px4_msgs pin

- `QQgdiw/px4_msgs` did not previously exist. A public fork of
  `PX4/px4_msgs` was created under the authenticated `QQgdiw` account.
- The compatibility line starts from upstream `release/1.16` commit
  `392e831c1f659429ca83902e66820d7094591410`.
- The upstream documented manual synchronization procedure was followed:
  existing generated ROS messages/services were replaced by the complete
  flattened message/service set from PX4 firmware commit `7c4fb9e638`.
- This repository pins DDS/ROS types only. Private Hybrid MAVLink definitions
  remain in the separately versioned `QQgdiw/mavlink` repository.
- Exact synchronization verification reports 236 expected and 236 actual
  messages with no missing, extra or changed files; the single service also
  matches byte-for-byte. A local dependency scan finds no unresolved message
  type. `git diff --check` passes.
- ROS 2 and `colcon` are not installed in this WSL environment, so an actual
  `colcon build` remains a companion-workspace acceptance item and is not
  claimed as completed here.
