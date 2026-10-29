# Engineering log

## 2026-10-29 VehicleLocalPosition v1 local-heading qualification

- User authorized a new independent local-heading qualification and coordinated
  PX4/px4_msgs release. Absolute heading qualification retains its meaning.
- VehicleLocalPosition MESSAGE_VERSION incremented 0 -> 1; topic gains `_v1`.
  New branch preserves the original r1 tag and source branch.
- All firmware messages and services compared byte-for-byte with the package;
  only VehicleLocalPosition changes relative to r1 package contents.
- No ROS installation is available here: no colcon or live DDS claim is made.
  Firmware contains an optional conversion source; it is not deployed by this
  package and v0 -> v1 sets the unprovable new flag false.

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
- Message commit `e0f41fb57ed9217ba15730854f6c7c92b0262134` was pushed on
  `hybrid-rover-v1.16.1`. Annotated tag `hybrid-rover-v1.16.1-r1` has object
  `6c0f64065af728ea1013e33793648dab7821e789` and peels to that commit.
- GitHub ruleset `22433564` was created and read back as active for exactly
  `refs/tags/hybrid-rover-v1.16.1-r1`; it prohibits deletion and
  non-fast-forward tag updates.
