# Tunnel-Scout

A drone on a fiber-optic tether for checking out caves and mines. The fiber carries the controls, telemetry and video, so it keeps working underground where radio doesn't. On board: a NoIR camera with IR lights, a 360° lidar for mapping, distance sensors so it doesn't hit walls, and gas sensors to check the air before anyone goes in.

UF CpE capstone (CEN3907C), Fall 2026, with Prof. Blanchard and our TA Minh. Test site: Warren Cave Nature Preserve.

**Team:** Hope Carter (hup) · Alex Hommerding (moon) · Roberto Zaldana-Arguello (royboitoe) · Gabriel Bendix (Gabe)

![Drone assembled](project-updates/week-11-nov-02-to-nov-08/2026-11-03_drone-assembled.jpg)

## What's in here

- `code/`: scripts that run on the Pi (camera stream, distance sensor). See `code/README.md`.
- `docs/`: the important stuff: how-to doc, Pi pinout, parts and expenses spreadsheet, wiring diagrams.
- `project-updates/`: one folder per week (week 1 = Aug 24 through week 15 = Dec 3 presentation week), with a file for each day we worked plus that week's pics.

## Posting an update

1. Copy `project-updates/TEMPLATE.md` into this week's folder as `YYYY-MM-DD.md`. If someone already made today's file, just add your section.
2. Drop your pics in the same folder as `YYYY-MM-DD_what-it-is.jpg`.
3. Commit as `update: YYYY-MM-DD <name> <what>` and push.
4. Someone writes the week's `WEEKLY-SUMMARY.md` on Sunday.
