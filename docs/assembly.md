# Assembly

Mount every module to its printed part first. Close the case in this order: **radar, then camera, then screen**. Attach cables to the Pi **before** any of those fronts go on.

Tighten nothing fully until the screen, camera strip, radar front, and shell close without pinch.

## Before you start

- Printed parts from your [variant list](choosing-a-variant.md)
- Raspberry Pi, plus your battery (UPS) board if you are using one: X1202, X1206 or X1209 ([what the codes mean](choosing-a-variant.md#what-x1202-x1206-and-x1209-mean)). With no battery board, the x1202 Pi adapter instead
- Display, camera, radar (OPS / IWR), and Adafruit modules for your build
- Fasteners from [Required hardware](hardware.md) — heat-set inserts **before** you stack boards
- **2.5 mm ball-end hex key** with **at least 90 mm of reach** for the case screws (see [Required hardware](hardware.md#tools))
- IWR firmware tools (current no-fill radar can be flashed after the module is mounted)

## 1. Inserts

Heat-set inserts before you stack boards. Print and assemble from each part’s **`v1/`** folder. The shell uses **three different insert jobs** plus **through-holes that must stay empty**.

| Location | Size | What it is |
| --- | --- | --- |
| Rear wall of the cavity | **M2.5** | Battery board / Pi (or adapter). Four bosses the board stack screws into; screw length depends on the shell, see [Board-stack screws per shell](hardware.md#board-stack-screws-per-shell). |
| Floor of the shell (four corner bosses) | **M3** | Adjustable feet only. Skip all four with solid feet or no feet (feet are optional). |
| Three floor bays | **M2.5** | Adafruit modules. 2 inserts per bay you populate; skip empty bays. A side-wall pair is only if that bay needs 4 screws. |
| Perimeter holes around the rim | — | **Through-holes.** No inserts. The ten case screws pass through the shell into inserts in the fronts. |

The camera front takes **4× M2** inserts (2 OV9281 + 2 sound-detector retainer). Other front inserts are listed in [Required hardware](hardware.md).

## 2. Mount components to their printed parts

Do this on the bench, not in the closed case.

| Module | Mounts to |
| --- | --- |
| Battery board / Pi (and x1202 or x1209 adapter if required) | [Shell](parts/shell.md) |
| Adafruit modules | Shell (three floor bays; optional extra pair on the side wall) |
| OPS and IWR | [Radar front](parts/radar.md) — current no-fill front can be flashed after mounting |
| Camera (Innomaker OV9281) and sound detector | [Camera front](parts/camera.md) — sound board in the pocket on the back of the strip (behind the front bar), then the printed retainer from behind |
| Display | [Screen bezel](parts/screen.md) (1024×600 uses the extra 4 inserts) |

**X1209 battery board:** x12-a1 shell plus the x1209 adapter. Do not use that shell without the adapter.

**No battery board:** x1202 shell plus the x1202 Pi adapter.

![Pi and battery board in the shell](drawings/assy-01-boards.png)

![Camera on the camera front](drawings/assy-01-camera-mount.png)

![Sound detector under the retainer](drawings/assy-01-camera-sound-retainer.png)

![OPS / IWR on the radar front](drawings/assy-01-radar-mount.png)

![Display in the screen bezel](drawings/assy-01-screen-mount.png)

## 3. Cables to the Pi

With the board stack in the shell and the fronts still off, connect every cable that must reach the Pi:

- Power / battery board
- Power (DC jack) and Ethernet; use the rear power button to switch the unit
- Display (DSI / HDMI / USB)
- Camera CSI
- Radar (OPS / IWR)
- Sound detector

You will not have room to mate these after the fronts are on.

**Camera ribbon cable — take care.** On the current camera front (`camera/v1/`) the camera sits in line with the IWR, so the CSI ribbon has to be routed around the radar module so it does not cover the IWR. Ribbon cables are delicate: bend them gently in a smooth curve, never crease or sharply fold them, and do not force the cable into place when fitting the camera front. A damaged ribbon typically shows up as the camera not being detected. If that happens, reseat both ends first, then try a replacement cable.

## 4. Fronts onto the shell

Use the **10 M3×8/10/12 socket head** screws and a **2.5 mm ball-end hex key** with **at least 90 mm of reach**. They go in from the back of the shell, down narrow channels: the Ø5.5 mm socket head fits, wider pan or flanged heads do not ([why](hardware.md#tools)). Fit in this order:

1. **Radar**
2. **Camera**
3. **Screen** last

![Radar front on the shell](drawings/assy-03-radar.png)

![Camera strip on](drawings/assy-04-camera.png)

![Screen last](drawings/assy-05-screen.png)

## 5. Feet (optional)

Feet are optional; skip this step if you did not print them. Otherwise fit [feet](parts/feet.md) last. Adjustable feet screw into the 4 M3 inserts in the shell. Set them so the unit sits level.

## IWR flashing

| Radar front | When to flash |
| --- | --- |
| No-fill (`radar/v1/Front-Radar-No-Fill.stl`) | After mounting is fine; nothing covers the radar faces |
| Filled (`radar/eol/Front-Radar.stl`, EOL) | **Before** mounting — the cover blocks access |

## Checks

- IWR is flashed (current no-fill front can be done after mounting).
- Every Pi cable is seated before the fronts go on.
- Fronts went on radar → camera → screen.
- Power connector does not stress the battery board.
- Display is square in the bezel.
- Camera / radar windows are unobstructed.
- Camera ribbon is not creased or pinched, and the camera is detected after closing.
- Unit does not rock; adjustable feet take the load, not the shell corners.

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
