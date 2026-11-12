# Week 45: Nov 2 – Nov 8, 2026

## Highlights

- **Pi 5 and fiber link up** (Nov 2): Raspberry Pi OS flashed, SSH over Ethernet, laptop ↔ Pi through the fiber converters, first camera still.
- **Motors soldered and drone assembled** (Nov 3). The NoIR camera streamed live video from the Pi (Hope, then Gabriel from a Mac).
- **Pre-Alpha submitted** (Nov 4) with the camera and ToF code, How-To Doc and parts list on GitHub.
- **BEC failed at 30% throttle** during the first motor tests (Nov 6). A 55 V Matek BEC12S-PRO was ordered, and Roberto wrote the failure analysis and a power design review (Nov 7–8).
- **Team visited Warren Cave** to see the demo site (Nov 7).

## Daily updates

- [2026-11-02 (Mon)](2026-11-02.md): FC setup, Pi OS, SSH, fiber link, camera install; soldering prep
- [2026-11-03 (Tue)](2026-11-03.md): motors soldered, drone assembled, camera streaming, How-To Doc
- [2026-11-04 (Wed)](2026-11-04.md): code and docs on GitHub; Pre-Alpha submitted
- [2026-11-05 (Thu)](2026-11-05.md): stakeholder meeting; Pi on bench supply; BEC jumper issue
- [2026-11-06 (Fri)](2026-11-06.md): BEC set to 5 V; motor tests; BEC failure; replacement ordered
- [2026-11-07 (Sat)](2026-11-07.md): Warren Cave visit; failure analysis; wiring v2
- [2026-11-08 (Sun)](2026-11-08.md): BEC protection research

## Undated work

These are in Hope's summaries, which were written up on Nov 10. They fall in or around this week, but the exact day isn't recorded:

- Hope: troubleshot the unmarked IR LED board's polarity. A bench supply at 3.3 V with a 0.1 A limit worked; the Arduino's 3.3 V and 5 V pins didn't.
  (`IR LED Board Troubleshooting Report.pdf`; same board result as Gabriel's Nov 3 bench test.)
- Hope: brought up the VL53L1X ToF sensor on the Pi 5 over I²C. Fixed an empty bus scan and a script that stalled after one reading, and moved to static IPs.
  (`VL53L1X ToF Sensor on Raspberry Pi 5 Work Summary.pdf`; script committed Nov 4.)
- Hope: planned collision avoidance. The VL53L1X sensors go on the Pi, and the Pi sends MAVLink DISTANCE_SENSOR to ArduPilot, with FC parameters and UART wiring worked out.
  (`Drone Collision Avoidance and Lidar Mapping Setup Report.pdf`)
- Hope and Roberto: programmed the flight controller and calibrated its sensors (`Hope Carter Work Summary Pre 11_10 (1).pdf`).

## Sources

- Discord #general, #announcements, #build_drone, #git_hub (Nov 2–8); git log (Nov 4, Nov 6)
- Drive: `Tunnel Scout/Roberto_s Media/Pre 11_10/`, `Tunnel Scout/Gabriel_s Media/Pre 11_10/`, `Tunnel Scout/Hope_s Media/Pre 11_10/`, `Tunnel Scout/First Cave Trip/`
- Claude summaries: `TunnelScout Drone Build — Conversation Report.docx`, `Pi 5 Bench Bring-Up — Conversation Report.docx`, `TunnelScout ESC Soldering Session Report.docx`, `TunnelScout Pi Camera and IR Bring-Up Log.docx`, `TunnelScout UBEC & Battery Bench Session Report.docx`
- Roberto's semester work report: [docs/reports](../../docs/reports/2026-11-10_tunnelscout-work-report-fall-2026.pdf)
