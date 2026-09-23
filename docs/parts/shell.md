# Shell and power

The rear body. Pick one board-specific file. Every current `v1` shell has the same rear I/O:

- **Ethernet** — 16.0 × 14.0 mm opening with two Ø4.0 mm screw holes
- **Barrel DC jack** — Ø12.5 mm
- **Power button** — Ø12.5 mm

Full dimensions and what fits them: [Rear I/O openings](#rear-io-openings).

USB-C rear shells are **EOL** (USB-C spec compatibility) — see [`stls/shell/eol/`](../../stls/shell/eol/README.md).

![Pi and UPS mounted in the shell](../drawings/assy-01-boards.png)

## Rear I/O openings

Every current `v1` shell carries the same three openings on one sloped rear
face, so these numbers apply to `Shell-x1202`, `Shell-x1206` and
`Shell-x12-a1` alike.

**The face is 3.0 mm thick.** That is the panel thickness a threaded connector
has to clamp, so check that each part's panel-thickness range covers 3 mm
before you buy it. Many panel connectors are cut for thin sheet metal and will
not close on 3 mm of plastic.

| Opening | Size | Centre (model X) |
| --- | --- | --- |
| **Ethernet** | **16.0 × 14.0 mm** rectangular cut-out (16.0 across the shell, 14.0 up the face), plus **two Ø4.0 mm screw holes 27.0 mm apart**, on the cut-out's horizontal centreline | 40.0 mm |
| **DC power** | **Ø12.5 mm** round | 73.0 mm |
| **Power button** | **Ø12.5 mm** round | 161.8 mm |

All three centres sit at the same height on the face. Across the 200 mm-wide
shell they run Ethernet, then DC jack, then power button: 33.0 mm from the
Ethernet centre to the DC centre, and 88.8 mm from the DC centre to the button
centre. Measured from the release STLs.

### What fits the Ethernet opening

A **panel-mount RJ45 feed-through coupler with a two-screw flange** — the kind
that takes a patch lead on each side, not a punch-down keystone. Check three
numbers on the datasheet before ordering:

1. the part of the body that passes through the panel is **no larger than
   16.0 × 14.0 mm**;
2. the flange screw holes are **27.0 mm apart** and take **M3** screws — the
   shell's Ø4.0 mm holes are clearance, so an M3 screw with a nut behind, or an
   M3 self-tapper into the plastic, both work;
3. it is rated for a **3 mm** panel.

> [!NOTE]
> **Do not buy from the reference model for this opening.**
> [`reference-models/connectors/Ethernet_Panel_Coupler.step`](../../reference-models/connectors/Ethernet_Panel_Coupler.step)
> is a **round coupler with a 21.7 mm thread**, contributed in
> [#8](https://github.com/open-flight/openflight-enclosure/pull/8) as a
> dimensional reference for *other* enclosure projects. This shell has no
> round Ethernet bore at all — its opening is the 16.0 × 14.0 mm rectangle
> above — so that part does not fit a `v1` shell. Match the three numbers
> instead; no specific product is endorsed here.

### What fits the DC opening

A **panel-mount DC barrel jack** with:

- a threaded barrel of **Ø12 mm or less** — the common 12 mm-thread panel jack
  is the snug fit; an M11 jack also goes in, with 0.75 mm of slop per side that
  its flange covers;
- a **flange or bezel wider than Ø12.5 mm**, so it seats against the face;
- a **panel thickness rating that reaches 3 mm**;
- a **5.5 × 2.1 mm** socket, if you are feeding a Geekworm X1202 or X1206 —
  that is the barrel size those boards use.

Buy one that comes **pre-wired with a flying lead**. This build keeps soldering
to a minimum, and a jack with solder tags adds a joint you would otherwise not
have to make. You will still need an iron for the heat-set inserts, as
[Required hardware](../hardware.md) says.

Unlike the Ethernet one, the
[reference DC jack](../../reference-models/connectors/DC_5.5x2.1_Panel_Jack.step)
is representative: it is a round jack with an Ø11 mm threaded barrel behind an
Ø15.5 mm flange, 18.5 mm long overall. That drops into the Ø12.5 mm hole with
0.75 mm of slop per side, which the flange covers.

> [!WARNING]
> **Barrel-jack polarity — get this wrong and you can destroy the Pi, the UPS
> and the radars at once.** A 5.5 × 2.1 mm plug carries no keying: a
> centre-negative supply mates perfectly with a centre-positive jack and
> reverses the rail. The Geekworm **X1202 and X1206 both expect centre pin
> positive (+)** — confirmed by Geekworm in
> [this exchange](https://github.com/open-flight/openflight/pull/273#issuecomment-5779406632);
> their wiki pages do not state it either way, so do not go looking there.
> When you wire the panel jack, the **centre/tip contact goes to +** and the
> sleeve to −, and the supply you plug in must also be centre positive. Buzz
> the jack out with a multimeter before the first power-up rather than
> trusting wire colour. The openflight
> [power guide](https://github.com/open-flight/openflight/blob/main/docs/get-started/power.md)
> covers the wiring end to end.

### What fits the button opening

A **12 mm panel-mount momentary push button**. It must be **momentary**
(spring-back): the X1202/X1206 read how long the button is held, so a latching
or toggle switch will not work.

## Board-specific shells

| Board | STL |
| --- | --- |
| x1209 (uses x12-a1 shell + adapter) | [`stls/shell/v1/Shell-x12-a1.stl`](../../stls/shell/v1/Shell-x12-a1.stl) |
| x1202 (UPS; also use this shell with no UPS) | [`stls/shell/v1/Shell-x1202.stl`](../../stls/shell/v1/Shell-x1202.stl) |
| x1206 | [`stls/shell/v1/Shell-x1206.stl`](../../stls/shell/v1/Shell-x1206.stl) |

**x12-a1 is not a standalone build.** Print `Shell-x12-a1` only with the [x1209 Pi adapter](adapters.md).

**x1202 is the UPS shell.** With the UPS board, print that shell only. With no UPS, still print an x1202 shell and add the [x1202 Pi adapter](adapters.md).

![Rear render](../../renders/rear.png)

## Hardware

See [Required hardware](../hardware.md).

| Qty | Item | Role |
| --- | --- | --- |
| 4 | M2.5 insert | UPS and Raspberry Pi |
| 2 or 4 per bay | M2.5 insert | Each of 3 Adafruit bays you populate |
| 10 | M3×8 / M3×10 / M3×12 | Mount screen and lower front to the shell |
| 4 | M3 insert | Adjustable feet only — none if using solid feet |

Same counts on every current shell.

## Print notes

Print **flat on its back** (rear of the enclosure on the bed). **Supports required; tree recommended.** Minimum bed **220 × 190 mm**.

![Shell print orientation](../drawings/print-shell.png)
