# Code

Scripts that run on the drone's companion computer.

## Hardware target

- **Computer:** Raspberry Pi 5 (4 GB), Raspberry Pi OS 64-bit (Bookworm), user `tunnelscout`.
  The team is moving the Pi to Ubuntu Server 24.04 with ROS 2. See the [How-To Doc v2](../docs/how-to/how-to-doc-v2.pdf).
- **Camera:** Raspberry Pi Camera Module 3 Wide NoIR (IMX708, 120°), on the Pi's CSI port.
- **Collision sensor:** Adafruit VL53L1X time-of-flight sensor on I²C bus 1 (address `0x29`):
  VIN → pin 1 (3.3 V), GND → pin 6, SDA → pin 3, SCL → pin 5.

## Layout

| Folder | Script | What it does |
| --- | --- | --- |
| `camera/` | [`ir-cam.py`](camera/ir-cam.py) | Streams the NoIR camera as MJPEG over HTTP on port 8000 (1280×720). Adapted from the [picamera2](https://github.com/raspberrypi/picamera2) `mjpeg_server.py` example. |
| `sensors/` | [`tof-sensor.py`](sensors/tof-sensor.py) | Reads the VL53L1X in long-range mode (100 ms timing budget) and prints the distance in cm. |

## Dependencies

- `picamera2`: install with `sudo apt install -y python3-picamera2` (not pip).
- `adafruit-circuitpython-vl53l1x`: install with pip inside a venv. See [`requirements.txt`](requirements.txt).
- I²C must be enabled: `sudo raspi-config` → Interface Options → I2C, then reboot. Check with `i2cdetect -y 1`.

## How to run

SSH into the Pi first (see the How-To Doc), then:

```bash
# Camera stream: open http://<pi-address>:8000/ in a browser, Ctrl+C to stop
python3 camera/ir-cam.py

# ToF sensor: prints "Distance: NN cm", Ctrl+C to stop
source ~/tof/bin/activate
python3 sensors/tof-sensor.py
```

Only one program can use the camera at a time, so stop any `rpicam-*` command first.

> **Note:** these files were renamed to kebab-case in this repo (they were `irCam.py` and `tofSensor.py`).
> The How-To Docs and the copies on the Pi still use the old names.
