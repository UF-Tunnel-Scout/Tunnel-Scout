# Friday, Nov 13

The new BEC (Matek BEC12S PRO) came in. Gabriel bench tested it, soldered on the wires and input capacitor, and covered it in heat shrink so it's ready to go on the drone.

## Gabriel

- **Bench test before soldering.** Powered the BEC from the Rigol DP832A supply with a Rigol DMM on the output:
  - 9.0 V in, about 13 mA draw: **5.2596 V out**.
  - 22 V in (close to a 6S pack): **5.2593 V out**. The output didn't move with input voltage, which is what we want.
  - Left both 8V/12V jumpers open, so it stays at the 5.2 V factory setting for the Pi rail.
- **Soldering.** Soldered on the power leads with **18 AWG wire** (18 AWG is what the BEC output needs to carry 5 A continuous / 9 A peak to the Pi) and added an electrolytic capacitor across the input to soak up voltage spikes when the battery is plugged in.
- **Heat shrink.** Wrapped the whole board in heat shrink. The BEC **must not touch the carbon fiber frame**. Carbon fiber conducts, so bare pads touching it could short the board.
- **Test after soldering.** Re-ran it at 22 V in (about 11 mA) with the heat shrink on: **5.2597 V out**. The soldering and shrink wrap didn't change anything.
- Copied the BEC pad diagram (IN / G / G / OUT, and the 8V/12V jumpers) into the design docs: [`docs/design/bec12s-pro-connections.png`](../../docs/design/bec12s-pro-connections.png).
- Worked through the BEC setup with Claude and saved the notes: [TunnelScout_BEC_Bench_Notes.docx](Gabriels-BEC-solder-Job/TunnelScout_BEC_Bench_Notes.docx). They cover:
  - Pinout, jumper settings and how to wire it on the bench.
  - Voltage spikes on the 6S drone: plugging in the battery can ring up to about 40 to 50 V, against the BEC's 55 V max. The fix is a low-ESR input cap and tapping the BEC from the ESC battery pads.
  - Current budget for the 5.2 V rail: Pi 5, RPLIDAR C1 and the camera come out to about 2.5 to 4 A steady, under the BEC's 5 A limit.
  - How to check what gauge an unmarked wire is (calipers, strand count or resistance) and which gauge to use for each connection.
  - Motor phase wiring and the ArduPilot Quad X motor order.

## Problems / what's next

- Mount the BEC on the drone, wired from the ESC battery pads, and keep it off the carbon fiber.
- Scope the BEC input when the 6S battery is plugged in to make sure the spikes stay well under 55 V.
- Load test the 5.2 V output with the real Pi + lidar + camera, and check `vcgencmd get_throttled` on the Pi.

## Pics & files

BEC pads and jumpers (also in `docs/design/`):

![BEC12S PRO connections](Gabriels-BEC-solder-Job/bec-info.png)

First test, 9 V in → 5.2596 V out:

![First test at 9 V](Gabriels-BEC-solder-Job/first-test.png)

22 V in → 5.2593 V out:

![Test at 22 V](Gabriels-BEC-solder-Job/22V-test.png)

Soldering setup, with the capacitor on the input pads and the 18 AWG leads:

![Solder setup](Gabriels-BEC-solder-Job/solder-setup.png)

Solder joints up close:

![Finished solder joints](Gabriels-BEC-solder-Job/solder-finished-job.png)

Heat shrunk and done:

![Finished BEC in heat shrink](Gabriels-BEC-solder-Job/isnt-she-lovely-finished-job-picture.png)

Test after soldering, 22 V in → 5.2597 V out:

![Test after soldering](Gabriels-BEC-solder-Job/post-solder-job.png)

## Sources

- Gabriel, Nov 13 (photos and notes)
- Claude chat summary: `Gabriels-BEC-solder-Job/TunnelScout_BEC_Bench_Notes.docx`
