# Enclosure documentation

Use this folder as the user guide. The GitHub README is the landing page; everything here is how to pick parts, print them, and put the unit together.

## Start here

1. [Choose a variant](choosing-a-variant.md) — one option from each module.
2. [Required hardware](hardware.md) — inserts and screws per piece.
3. [Print](printing.md) — face-down fronts, shell on its back; **220 × 220 mm** bed minimum.
4. [Assemble](assembly.md) — mount modules to each printed part, cables to the Pi, then radar → camera → screen.

## Parts

Each part page lists the STL, when to use it, and hardware.

- [Shell and power](parts/shell.md)
- [Pi adapters](parts/adapters.md)
- [Feet](parts/feet.md)
- [Screen bezel](parts/screen.md)
- [Camera front](parts/camera.md)
- [Radar front](parts/radar.md)

## Drawings

The seven assembly stills and print-orientation shots live in [`drawings/`](drawings/README.md).

## File layout in this repo

```
202609/Cormac131/
  docs/          This guide
  step/          CAD source
  renders/       Marketing / overview images
  stls/
    shell/       Rear body + power cutouts + adapters + feet
    screen/      Display bezels
    camera/      Lower front with camera (+ sound-detector retainer)
    radar/       Lower front with radar
```

## Support

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
