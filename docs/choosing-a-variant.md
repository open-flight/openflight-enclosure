# Choosing a variant

The enclosure is modular. You print **one rear shell**, **one screen bezel**, **one radar front**, **one camera front**, **one set of feet**, and an adapter when you skip the UPS or when the board requires it.

All STL paths below are relative to [`stls/`](../stls/). Print from **`v1/`**. Files under `experimental/` are not the release set. Current shells have **Ethernet, a DC jack, and a power button**. The current radar is **no-fill**; the current camera front includes the **sound detector** and puts the camera in line with the IWR. Withdrawn files live under each part’s `eol/` folder.

## Decision tree

```
1. Board / UPS (shell filename must match; files in shell/v1/)
   ├─ x1202 UPS          → Shell-x1202
   ├─ no UPS             → still Shell-x1202 + adapters/v1/x1202 Pi Adapater.stl
   ├─ x1206              → Shell-x1206
   └─ x1209              → Shell-x12-a1 + adapters/v1/x1209 PI Adapater.stl
                           (do not use the x12-a1 shell on its own)

2. Screen
   ├─ 800×480
   ├─ 1024×600
   ├─ Raspberry Pi Display
   └─ Raspberry Pi Display 2

3. Radar front — no-fill (`radar/v1/Front-Radar-No-Fill.stl`; filled front is EOL)

4. Camera front — sound detector (`camera/v1/Front-Camera-Sound-Detector.stl` **and** `Sound-Detector-Retainer.stl`; camera-only and the previous strip are EOL)

5. Feet
   ├─ Solid
   └─ Adjustable
```

## Print list (copy and fill)

| Slot | Your pick | STL |
| --- | --- | --- |
| Shell | Board / UPS | `shell/v1/Shell-<board>.stl` |
| Adapter | none / no-UPS / x1209 | `adapters/v1/x1202 Pi Adapater.stl` if skipping UPS; `adapters/v1/x1209 PI Adapater.stl` with the x12-a1 shell |
| Screen | | `screen/v1/Screen-….stl` |
| Radar | no-fill | `radar/v1/Front-Radar-No-Fill.stl` |
| Camera | sound detector | `camera/v1/Front-Camera-Sound-Detector.stl` **and** `camera/v1/Sound-Detector-Retainer.stl` |
| Feet | Solid / Adjustable | `feet/v1/Feet-….stl` |

## Compatibility matrix

### Shell × board

| Board | Current shell | Extra adapter |
| --- | --- | --- |
| x1202 (UPS) | `shell/v1/Shell-x1202.stl` | — |
| no UPS | same x1202 shell | `adapters/v1/x1202 Pi Adapater.stl` (recommended) |
| x1206 | `shell/v1/Shell-x1206.stl` | — |
| x1209 | `shell/v1/Shell-x12-a1.stl` | `adapters/v1/x1209 PI Adapater.stl` (required) |

Withdrawn (do not print for a new unit): USB-C rear shells (`shell/eol/`), filled radar (`radar/eol/Front-Radar.stl`), camera-only front (`camera/eol/Front-Camera.stl`), previous sound-detector camera front (`camera/eol/Front-Camera-Sound-Detector.stl`).

Do not print `Shell-x12-a1` without the x1209 adapter. That shell is only for x1209.

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

### Feet (independent)

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

**x1202 UPS, 1024×600, adjustable feet**

- `shell/v1/Shell-x1202.stl`
- `radar/v1/Front-Radar-No-Fill.stl`
- `camera/v1/Front-Camera-Sound-Detector.stl`
- `camera/v1/Sound-Detector-Retainer.stl`
- `screen/v1/Screen-1024x600.stl`
- `feet/v1/Feet-Adjustable.stl`

**Same layout with no UPS** — still print `Shell-x1202`, plus `adapters/v1/x1202 Pi Adapater.stl` so the Pi mounts without the UPS board.

Hardware for whichever list you print: [Required hardware](hardware.md).

## CAD overview

Close-up order is radar, then camera, then screen. See [Assembly](assembly.md) for the CAD stills.

![Pi in shell](drawings/assy-01-boards.png)
![Radar on shell](drawings/assy-03-radar.png)
![Camera on shell](drawings/assy-04-camera.png)
![Screen last](drawings/assy-05-screen.png)

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
