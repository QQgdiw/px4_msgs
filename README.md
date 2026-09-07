# px4_msgs

## QQgdiw Hybrid Quad/Rover compatibility pin

The `hybrid-rover-v1.16.1` branch is synchronized from
`QQgdiw/PX4-Autopilot` branch `feature/testc4-rover-tuning` at commit
`7c4fb9e638787435351437c4dfc99e417adffd85`. It is the required ROS 2 message
package for the `zeroone_x6_hybrid` companion-computer DDS interface.

Do not replace this branch with the upstream `release/1.16` package: the
upstream package does not define this project's exact-one-bit
`OffboardControlMode.rover_velocity` contract or its matching
`RoverVelocitySetpoint` type. MAVLink bindings are versioned separately and
are not provided by this repository.

[![GitHub license](https://img.shields.io/github/license/PX4/px4_msgs.svg)](https://github.com/PX4/px4_msg/blob/master/LICENSE) [![Build package](https://github.com/PX4/px4_msgs/workflows/Build%20package/badge.svg)](https://github.com/PX4/px4_msgs/actions)

[![Discord Shield](https://discordapp.com/api/guilds/1022170275984457759/widget.png?style=shield)](https://discord.gg/dronecode)

ROS 2 message definitions for the [PX4 Autopilot](https://px4.io/) project.

Building this package generates all the required interfaces to interface ROS 2 nodes with the PX4 internals.

## Supported versions and compatibility

Depending on the PX4 and ROS versions you want to use, you need to checkout the appropriate branch of this package:

| PX4            | ROS 2   | Ubuntu       | branch                                                            |
|----------------|---------|--------------|-------------------------------------------------------------------|
| [v1.13](https://github.com/PX4/px4_msgs/tree/release/1.13)           | Foxy    | Ubuntu 20.04 | [release/1.13](https://github.com/PX4/px4_msgs/tree/release/1.13) |
| [v1.14](https://github.com/PX4/px4_msgs/tree/release/1.14)           | Foxy    | Ubuntu 20.04 | [release/1.14](https://github.com/PX4/px4_msgs/tree/release/1.14) |
| [v1.14](https://github.com/PX4/px4_msgs/tree/release/1.14)           | Humble  | Ubuntu 22.04 | [release/1.14](https://github.com/PX4/px4_msgs/tree/release/1.14) |
| [v1.14](https://github.com/PX4/px4_msgs/tree/release/1.14)           | Rolling | Ubuntu 22.04 | [release/1.14](https://github.com/PX4/px4_msgs/tree/release/1.14) |
| [v1.15](https://github.com/PX4/px4_msgs/tree/release/1.15)           | Foxy    | Ubuntu 20.04 | [release/1.15](https://github.com/PX4/px4_msgs/tree/release/1.15) |
| [v1.15](https://github.com/PX4/px4_msgs/tree/release/1.15)           | Humble  | Ubuntu 22.04 | [release/1.15](https://github.com/PX4/px4_msgs/tree/release/1.15) |
| [v1.15](https://github.com/PX4/px4_msgs/tree/release/1.15)           | Rolling | Ubuntu 22.04 | [release/1.15](https://github.com/PX4/px4_msgs/tree/release/1.15) |
| [main](https://github.com/PX4/px4_msgs/tree/main)                    | Foxy    | Ubuntu 22.04 | [main](https://github.com/PX4/px4_msgs)                           |
| [main](https://github.com/PX4/px4_msgs/tree/main)                    | Humble  | Ubuntu 22.04 | [main](https://github.com/PX4/px4_msgs)                           |
| [main](https://github.com/PX4/px4_msgs/tree/main)                    | Rolling | Ubuntu 22.04 | [main](https://github.com/PX4/px4_msgs)                           |

### Messages Sync from PX4

When PX4 message definitions in the `main` branch of [PX4 Autopilot](https://github.com/PX4/PX4-Autopilot) change, a [CI/CD pipeline](https://github.com/PX4/PX4-Autopilot/blob/main/.github/workflows/metadata.yml#L119) automatically copies and pushes updated ROS message definitions to this repository. This ensures that this repository `main` branch and the PX4-Autopilot `main` branch are always up to date.
However, if you are using a custom PX4 version and you modified existing messages or created new one, then you have to manually synchronize them in this repository:
### Manual Message Sync

- Checkout the correct branch associated to the PX4 version from which you detached you custom version.
- Delete all `*.msg` and `*.srv` files in `msg/` and  `srv/`.
- Copy all `*.msg` and  `*.srv` files from `PX4-Autopilot/msg/` and `PX4-Autopilot/srv/` in  `msg/` and  `srv/`, respectively. Assuming that this repository and the PX4-Autopilot repository are placed in your home folder, you can run:
  ```sh
  rm -f ~/px4_msgs/msg/*.msg
  rm -f ~/px4_msgs/srv/*.srv
  cp ~/PX4-Autopilot/msg/*.msg ~/px4_msgs/msg/
  cp ~/PX4-Autopilot/msg/versioned/*.msg ~/px4_msgs/msg/
  cp ~/PX4-Autopilot/srv/*.srv ~/px4_msgs/srv/
  ```
**Note:** The ROS 2 message generation pipeline requires all messages to be directly under `msg/` and doesn't support sub-directories.

## Install, build and usage

Check [Using colcon to build packages](https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Creating-Your-First-ROS2-Package.html#build-a-package) to understand how this can be built inside a workspace. Check the [PX4 ROS 2 User Guide](https://docs.px4.io/main/en/ros/ros2_comm.html) section on the PX4 documentation for further details on how this integrates PX4 and how to exchange messages with the autopilot.

## Bug tracking and feature requests

Use the [Issues](https://github.com/PX4/px4_msgs/issues) section to create a new issue. Report your issue or feature request [here](https://github.com/PX4/px4_msgs/issues/new).

## Questions and troubleshooting

Reach the PX4 development team on the [PX4 Discord Server](https://discord.gg/dronecode).
