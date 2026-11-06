# Choosing a variant

The enclosure is modular. You print **one rear shell**, **one screen bezel**, **one radar front**, **one camera front**, optionally **one set of feet**, and an adapter when you skip the battery board or when the board requires it.

## What X1202, X1206 and X1209 mean

**X1202, X1206 and X1209 are Geekworm battery boards** (also called UPS boards or UPS HATs). A battery board bolts underneath the Raspberry Pi 5, holds rechargeable cells, and keeps the Pi running when you unplug the power, so the monitor works away from a wall socket. The X1202 takes four 18650 cells, the X1206 four larger 21700 cells; the X1209 is another board in the same Geekworm family. Each board has a different size and screw pattern, so **the shell is named after the battery board it holds**: `Shell-x1202`, `Shell-x1206`, and `Shell-x12-a1` for the X1209.

Pick the shell **before you print**, even if you plan to run from a wall supply for now:

- **No battery board, mains power only:** print `Shell-x1202` with the [x1202 Pi adapter](parts/adapters.md). The adapter plate takes the place of the battery board. You can fit an X1202 later in the same shell without reprinting it.
- **Battery power:** print the shell that matches the board you buy. The OpenFlight software reads battery level from the X1202 and X1206; see the [battery guide](https://github.com/open-flight/openflight/blob/main/docs/build/battery.md) and [Powering OpenFlight](https://github.com/open-flight/openflight/blob/main/docs/get-started/power.md) in the main repository for cells, adapters and wiring.

All STL paths below are relative to [`stls/`](../stls/). Print from **`v1/`**. Files under `experimental/` are not the release set. Current shells have **Ethernet, a DC jack, and a power button**. The current radar is **no-fill**; the current camera front includes the **sound detector** and puts the camera in line with the IWR. Withdrawn files live under each part’s `eol/` folder.

## Decision tree

```
1. Battery (UPS) board (shell filename must match; files in shell/v1/)
   ├─ X1202 battery board   → Shell-x1202
   ├─ no battery board      → still Shell-x1202 + adapters/v1/x1202 Pi Adapater.stl (needed)
   ├─ X1206 battery board   → Shell-x1206
   └─ X1209 battery board   → Shell-x12-a1 + adapters/v1/x1209 PI Adapater.stl
                              (do not use the x12-a1 shell on its own)

2. Screen
   ├─ 800×480
   ├─ 1024×600
   ├─ Raspberry Pi Display
   └─ Raspberry Pi Display 2

3. Radar front — no-fill (`radar/v1/Front-Radar-No-Fill.stl`; filled front is EOL)

4. Camera front — sound detector (`camera/v1/Front-Camera-Sound-Detector.stl` **and** `Sound-Detector-Retainer.stl`; camera-only and the previous strip are EOL)

5. Feet (optional; without them the shell sits directly on its base)
   ├─ None
   ├─ Solid
   └─ Adjustable
```

## Print list (copy and fill)

| Slot | Your pick | STL |
| --- | --- | --- |
| Shell | Battery (UPS) board | `shell/v1/Shell-<board>.stl` |
| Adapter | none / no battery board / X1209 | `adapters/v1/x1202 Pi Adapater.stl` if you skip the battery board; `adapters/v1/x1209 PI Adapater.stl` with the x12-a1 shell |
| Screen | | `screen/v1/Screen-….stl` |
| Radar | no-fill | `radar/v1/Front-Radar-No-Fill.stl` |
| Camera | sound detector | `camera/v1/Front-Camera-Sound-Detector.stl` **and** `camera/v1/Sound-Detector-Retainer.stl` |
| Feet (optional) | None / Solid / Adjustable | `feet/v1/Feet-….stl`, or nothing |

## Compatibility matrix

### Shell × battery board

| Battery (UPS) board | Current shell | Extra adapter |
| --- | --- | --- |
| X1202 battery board | `shell/v1/Shell-x1202.stl` | — |
| no battery board | same x1202 shell | `adapters/v1/x1202 Pi Adapater.stl` (needed) |
| X1206 battery board | `shell/v1/Shell-x1206.stl` | — |
| X1209 battery board | `shell/v1/Shell-x12-a1.stl` | `adapters/v1/x1209 PI Adapater.stl` (required) |

Withdrawn (do not print for a new unit): USB-C rear shells (`shell/eol/`), filled radar (`radar/eol/Front-Radar.stl`), camera-only front (`camera/eol/Front-Camera.stl`), previous sound-detector camera front (`camera/eol/Front-Camera-Sound-Detector.stl`).

Do not print `Shell-x12-a1` without the x1209 adapter. That shell is only for the X1209 battery board.

### Screen (independent of shell)

| Variant | STL |
| --- | --- |
| 800×480 | `screen/v1/Screen-800x480.stl` |
| 1024×600 | `screen/v1/Screen-1024x600.stl` |
| Raspberry Pi Display | `screen/v1/Screen-RPI-Display.stl` |
| Raspberry Pi Display 2 | `screen/v1/Screen-RPI-Display-2.stl` |

### Radar front

| Variant | STL |
| --- | --- |
| No-fill (current) | `radar/v1/Front-Radar-No-Fill.stl` |
| Filled (EOL) | `radar/eol/Front-Radar.stl` |

### Camera front

UART vs USB OPS does not change the camera STL. The strip clears both.

| Variant | STL |
| --- | --- |
| Camera + sound detector, camera in line with the IWR (current) | `camera/v1/Front-Camera-Sound-Detector.stl` **and** `camera/v1/Sound-Detector-Retainer.stl` |
| Camera + sound detector, previous strip (EOL) | `camera/eol/Front-Camera-Sound-Detector.stl` |
| Camera only (EOL) | `camera/eol/Front-Camera.stl` |

### Feet (optional, independent)

Feet are optional. Skip them and the shell sits directly on its base; no inserts go in the foot bosses.

| Variant | STL |
| --- | --- |
| Solid | `feet/v1/Feet-Solid.stl` |
| Adjustable | `feet/v1/Feet-Adjustable.stl` |

## Worked examples

**Typical DC-powered unit**

- `shell/v1/Shell-x1206.stl`
- `radar/v1/Front-Radar-No-Fill.stl`
- `camera/v1/Front-Camera-Sound-Detector.stl`
- `camera/v1/Sound-Detector-Retainer.stl`
- `screen/v1/Screen-800x480.stl`
- `feet/v1/Feet-Solid.stl`

**X1202 battery board, 1024×600, adjustable feet**

- `shell/v1/Shell-x1202.stl`
- `radar/v1/Front-Radar-No-Fill.stl`
- `camera/v1/Front-Camera-Sound-Detector.stl`
- `camera/v1/Sound-Detector-Retainer.stl`
- `screen/v1/Screen-1024x600.stl`
- `feet/v1/Feet-Adjustable.stl`

**Same layout with no battery board** — still print `Shell-x1202`, plus `adapters/v1/x1202 Pi Adapater.stl` so the Pi mounts without the X1202 battery board.

Hardware for whichever list you print: [Required hardware](hardware.md).

## CAD overview

Close-up order is radar, then camera, then screen. See [Assembly](assembly.md) for the CAD stills.

![Pi in shell](drawings/assy-01-boards.png)
![Radar on shell](drawings/assy-03-radar.png)
![Camera on shell](drawings/assy-04-camera.png)
![Screen last](drawings/assy-05-screen.png)

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
