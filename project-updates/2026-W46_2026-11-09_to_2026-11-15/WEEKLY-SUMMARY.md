# Week 46: Nov 9 – Nov 15, 2026 (current week, through Nov 11)

## Highlights

- **First flight** (Nov 9): the drone armed and lifted on battery through the full Xbox → laptop → fiber → Pi → FC path, then pitched forward and was stopped with the kill switch.
- **GitHub tracking required** by the lab manager and TA (Nov 10). Gabriel set up the process. Roberto, Hope and Alex documented their work so far.
- Roberto's **semester work report** (24 pages) and daily logs. FC errors cleared, now on ArduCopter v4.7.2 (Nov 10).
- Gabriel worked through the RPLIDAR C1 bench test (USB-C cable issue found) and the lidar mounting plan (Nov 10).
- Borrowed **TBS Tango II** set up as a joystick; flight setup and test plan sent to the team (Nov 11).

## Daily updates

- [2026-11-09 (Mon)](2026-11-09.md): first flight test
- [2026-11-10 (Tue)](2026-11-10.md): documentation, lidar bench test, FC tuning
- [2026-11-11 (Wed)](2026-11-11.md): Tango II joystick and flight plan

## Undated work

From Hope's summaries, written up on Nov 10. The exact days aren't recorded:

- Hope: Pi-to-FC MAVLink link with MAVProxy on the Pi (`/dev/ttyACM0` → TCP 5760). QGroundControl "Drone Tether" TCP link through the fiber.
  Xbox joystick input. Cleared the rangefinder/proximity arming blockers. This was after the Nov 6 BEC failure, which is listed as open, and by Nov 9 ("got the controller controlling the motors").
  (`Tethered Drone Pi-to-FC Link and QGroundControl Setup Report.pdf`, `Tethered Drone Bring-Up Work Summary.pdf`, `Tethered Drone Setup Work Summary.pdf`)
- Hope: researched cave mapping with the RPLIDAR C1, covering SLAM, ROS 2 Jazzy on Ubuntu 24.04, and HC-SR04 test rigs to use before the lidar arrives.
  (`Cave Mapping with a Lidar Drone Chat Summary.pdf`)

## Coming up (from the logs)

- Replacement BEC due Nov 12. Set up the Tango II in QGC and run the motor-order and throttle-only tests. Retry the flight in AltHold on Fri Nov 13.
- New Pi OS (Ubuntu + ROS 2) from Alex. Camera, lidar and gas sensors working together on the Pi.

## Sources

- Discord #general, #build_drone, #lidar, #git_hub (Nov 9–10); git log (Nov 10–11)
- Roberto's daily logs (assets/), work report ([docs/reports](../../docs/reports/2026-11-10_tunnelscout-work-report-fall-2026.pdf))
- Drive: `Tunnel Scout/Gabriel_s Media/11_10/`, `Tunnel Scout/Hope_s Media/Pre 11_10/`
- Claude summaries: `TunnelScout LiDAR Session Report.docx`, `TunnelScout Drone Stack — Chat Report.docx`
