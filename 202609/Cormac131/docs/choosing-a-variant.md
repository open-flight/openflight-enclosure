# Choosing a variant

The enclosure is modular. You print **one rear shell**, **one screen bezel**, **one radar front**, **one camera front**, **one set of feet**, and an adapter when you skip the UPS or when the board requires it.

All STL paths below are relative to [`stls/`](../stls/).

## Decision tree

```
1. Power I/O
   ├─ Barrel DC jack     →  shell/dc-jack/
   └─ USB-C + Ethernet   →  shell/usbc-ethernet/

2. Board / UPS (shell filename must match)
   ├─ x1202 UPS          → Shell-x1202
   ├─ no UPS             → still Shell-x1202 + shell/x1202 Pi Adapater.stl
   ├─ x1206              → Shell-x1206
   └─ x1209              → Shell-x12-a1 + shell/x1209 PI Adapater.stl
                           (do not use the x12-a1 shell on its own)

3. Screen
   ├─ 800×480
   ├─ 1024×600
   ├─ Raspberry Pi Display
   └─ Raspberry Pi Display 2

4. Radar front
   ├─ Standard (cover in front of the radars)
   └─ No-fill (open in front of the radars; does not block RF)

5. Camera front (same strip for UART or USB OPS)
   ├─ Camera only
   └─ Camera + sound detector  (+ print Sound-Detector-Retainer.stl)

6. Feet
   ├─ Solid
   └─ Adjustable
```

## Print list (copy and fill)

| Slot | Your pick | STL |
| --- | --- | --- |
| Shell | DC jack / USB-C Ethernet + board | `shell/<power>/Shell-<board>.stl` |
| Adapter | none / no-UPS / x1209 | `shell/x1202 Pi Adapater.stl` if skipping UPS; `shell/x1209 PI Adapater.stl` with the x12-a1 shell |
| Screen | | `screen/Screen-….stl` |
| Radar | | `radar/Front-Radar….stl` |
| Camera | | `camera/Front-Camera….stl` (+ `camera/Sound-Detector-Retainer.stl` if using sound) |
| Feet | Solid / Adjustable | `shell/feet/Feet-….stl` |

## Compatibility matrix

### Shell × power × board

| Board | DC jack | USB-C + Ethernet | Extra adapter |
| --- | --- | --- | --- |
| x1202 (UPS) | `shell/dc-jack/Shell-x1202.stl` | `shell/usbc-ethernet/Shell-x1202.stl` | — |
| no UPS | same x1202 shells | same x1202 shells | `shell/x1202 Pi Adapater.stl` (recommended) |
| x1206 | `shell/dc-jack/Shell-x1206.stl` | `shell/usbc-ethernet/Shell-x1206.stl` | — |
| x1209 | `shell/dc-jack/Shell-x12-a1.stl` | `shell/usbc-ethernet/Shell-x12-a1.stl` | `shell/x1209 PI Adapater.stl` (required) |

Do not print `Shell-x12-a1` without the x1209 adapter. That shell is only for x1209.

### Screen (independent of shell)

| Variant | STL |
| --- | --- |
| 800×480 | `screen/Screen-800x480.stl` |
| 1024×600 | `screen/Screen-1024x600.stl` |
| Raspberry Pi Display | `screen/Screen-RPI-Display.stl` |
| Raspberry Pi Display 2 | `screen/Screen-RPI-Display-2.stl` |

### Radar front

| Variant | STL |
| --- | --- |
| Radar | `radar/Front-Radar.stl` |
| Radar, no-fill (no cover in front of the radars) | `radar/Front-Radar-No-Fill.stl` |

### Camera front

UART vs USB OPS does not change the camera STL. The strip clears both.

| Variant | STL |
| --- | --- |
| Camera | `camera/Front-Camera.stl` |
| Camera + sound detector | `camera/Front-Camera-Sound-Detector.stl` **and** `camera/Sound-Detector-Retainer.stl` |

### Feet (independent)

| Variant | STL |
| --- | --- |
| Solid | `shell/feet/Feet-Solid.stl` |
| Adjustable | `shell/feet/Feet-Adjustable.stl` |

## Worked examples

**Typical DC-powered unit**

- `shell/dc-jack/Shell-x1206.stl`
- `radar/Front-Radar.stl`
- `camera/Front-Camera.stl`
- `screen/Screen-800x480.stl`
- `shell/feet/Feet-Solid.stl`

**USB-C / Ethernet with x1202 UPS, 1024×600, sound detector, adjustable feet**

- `shell/usbc-ethernet/Shell-x1202.stl`
- `radar/Front-Radar.stl`
- `camera/Front-Camera-Sound-Detector.stl`
- `camera/Sound-Detector-Retainer.stl`
- `screen/Screen-1024x600.stl`
- `shell/feet/Feet-Adjustable.stl`

**Same layout with no UPS** — still print `Shell-x1202`, plus `shell/x1202 Pi Adapater.stl` so the Pi mounts without the UPS board.

Hardware for whichever list you print: [Required hardware](hardware.md).

## CAD overview

Close-up order is radar, then camera, then screen. See [Assembly](assembly.md) for the CAD stills.

![Pi in shell](drawings/assy-01-boards.png)
![Radar on shell](drawings/assy-03-radar.png)
![Camera on shell](drawings/assy-04-camera.png)
![Screen last](drawings/assy-05-screen.png)

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
