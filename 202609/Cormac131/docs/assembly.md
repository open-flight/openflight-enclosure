# Assembly

Mount every module to its printed part first. Close the case in this order: **radar, then camera, then screen**. Attach cables to the Pi **before** any of those fronts go on.

Tighten nothing fully until the screen, camera strip, radar front, and shell close without pinch.

## Before you start

- Printed parts from your [variant list](choosing-a-variant.md)
- Raspberry Pi, plus the x1202 UPS if you are using one (otherwise the x1202 Pi adapter)
- Display, camera, radar (OPS / IWR), and Adafruit modules for your build
- Fasteners from [Required hardware](hardware.md) — heat-set inserts **before** you stack boards
- IWR firmware tools, unless you are using a **no-fill** radar front (you can flash that one after it is mounted)

## 1. Inserts

Heat-set all M3, M2.5, and M2 inserts. M3 inserts for adjustable feet go in the [shell](parts/shell.md); skip those if using solid feet. The camera front takes **2× M2** inserts for the OV9281, plus **2× M2** more if you printed the sound-detector retainer.

## 2. Mount components to their printed parts

Do this on the bench, not in the closed case.

| Module | Mounts to |
| --- | --- |
| UPS / Pi (and x1202 or x1209 adapter if required) | [Shell](parts/shell.md) |
| Adafruit modules | Shell (three bays on the left wall) |
| OPS and IWR | [Radar front](parts/radar.md) — **flash the IWR before you mount it**, unless you printed a no-fill radar front |
| Camera (Innomaker OV9281) and sound detector | [Camera front](parts/camera.md) — sound board in the pocket, then the printed retainer |
| Display | [Screen bezel](parts/screen.md) (1024×600 uses the extra 4 inserts) |

**x1209:** x12-a1 shell plus the x1209 adapter. Do not use that shell without the adapter.

**No UPS:** x1202 shell plus the x1202 Pi adapter.

![Pi and UPS in the shell](drawings/assy-01-boards.png)

![Camera on the camera front](drawings/assy-01-camera-mount.png)

![Sound detector under the retainer](drawings/assy-01-camera-sound-retainer.png)

![OPS / IWR on the radar front](drawings/assy-01-radar-mount.png)

![Display in the screen bezel](drawings/assy-01-screen-mount.png)

## 3. Cables to the Pi

With the board stack in the shell and the fronts still off, connect every cable that must reach the Pi:

- Power / UPS
- Ethernet or USB-C (as your shell allows)
- Display (DSI / HDMI / USB)
- Camera CSI
- Radar (OPS / IWR)
- Sound detector, if fitted

You will not have room to mate these after the fronts are on.

## 4. Fronts onto the shell

Use the **10 M3×8/10/12** screws. Fit in this order:

1. **Radar**
2. **Camera**
3. **Screen** last

![Radar front on the shell](drawings/assy-03-radar.png)

![Camera strip on](drawings/assy-04-camera.png)

![Screen last](drawings/assy-05-screen.png)

## 5. Feet

Fit [feet](parts/feet.md) last. Adjustable feet screw into the 4 M3 inserts in the shell. Set them so the unit sits level.

## IWR flashing

| Radar front | When to flash |
| --- | --- |
| Standard (`Front-Radar.stl`) | **Before** mounting the IWR on the radar front |
| No-fill (`Front-Radar-No-Fill.stl`) | Can be done after mounting; nothing covers the radar faces |

## Checks

- IWR was flashed before it went on a standard (filled) radar front.
- Every Pi cable is seated before the fronts go on.
- Fronts went on radar → camera → screen.
- Power connector does not stress the HAT.
- Display is square in the bezel.
- Camera / radar windows are unobstructed.
- Unit does not rock; adjustable feet take the load, not the shell corners.

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
