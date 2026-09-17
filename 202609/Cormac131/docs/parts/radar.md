# Radar front

Lower housing for OPS and IWR. Print this **and** a [camera front](camera.md). Pick one radar STL. UART and USB OPS both use this radar front; the [camera strip](camera.md) is the part that clears both connector types.

![OPS / IWR on the radar front](../drawings/assy-01-radar-mount.png)

![Radar front on the shell](../drawings/assy-03-radar.png)

| Variant | STL | Use when |
| --- | --- | --- |
| Standard | [`Front-Radar.stl`](../../stls/radar/Front-Radar.stl) | Cover in front of the radars |
| No-fill | [`Front-Radar-No-Fill.stl`](../../stls/radar/Front-Radar-No-Fill.stl) | No cover in front of the radars, so the plastic does not affect RF |

## Hardware

See [Required hardware](../hardware.md). Same inserts on standard and no-fill fronts.

**12× M3 inserts:** 4 OPS, 4 IWR, 4 case mounting.

**IWR:** flash firmware **before** mounting the module on a **standard** radar front (the cover blocks access). On a **no-fill** front you can flash after it is mounted. See [Assembly](../assembly.md).

## Print notes

No-fill is **not** a slicer infill setting. It means there is no wall covering the radar faces.

**Standard:** print with the **face on the build plate**.

![Standard radar print orientation](../drawings/print-radar.png)

**No-fill:** print **on its back**. **Tree supports required.**

![No-fill radar print orientation](../drawings/print-radar-nofill.png)
