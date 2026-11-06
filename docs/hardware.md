# Required hardware

Install inserts with a soldering iron, square to the boss, flush with the plastic. Do not drive a screw into bare plastic in an insert hole.

## Standard parts (buy these)

| Part | Spec | Used for |
| --- | --- | --- |
| Heat-set insert | **M3 × 4 mm** long, **Ø4.8–5.2 mm** outer (knurl) diameter | Fronts, screen, adjustable-feet bosses in the shell |
| Heat-set insert | **M2.5 × 4 mm** long, **Ø3.5–3.8 mm** outer diameter | Battery board / Pi and Adafruit bays in the shell |
| Heat-set insert | **M2 × 4 mm** long, **Ø3.2–3.5 mm** outer diameter | Camera module (OV9281) and sound-detector retainer |
| Case screw | **M3×8**, **M3×10**, or **M3×12** | 10 screws that mount the fronts to the shell |
| Board-stack screw | **M2.5**, length depends on the shell | 4 screws that hold the battery board / Pi stack; see [Board-stack screws per shell](#board-stack-screws-per-shell) |

Pick M3 length after a dry fit (start with **M3×10**).

### Insert sizes: what the modelled holes take

Inserts are sold by thread (M3), **length** and **outer diameter** (the knurl). The thread alone does not tell you whether an insert fits: an "M3" insert can be anything from Ø4.0 to Ø5.7 across the knurl. Check both numbers on the listing before you order.

The holes below are the diameters **as modelled** in the release STLs. Printed holes usually come out 0.1–0.2 mm smaller.

| Thread | Modelled hole Ø | Hole depth | Insert outer Ø that grips | Longest insert | Where |
| --- | --- | --- | --- | --- | --- |
| **M3** | **4.4 mm** | 4.2–10 mm | **4.8–5.2 mm** (the common "M3 × 4 × 5" size) | **4 mm** (the 1024×600 panel pockets are 4.2 mm deep; everywhere else takes up to 5 mm) | Radar front, camera front, screen bezels, adjustable-feet bosses |
| **M2.5** | **3.3 mm** (board-stack bosses in `Shell-x1202` and `Shell-x1206`), **3.4 mm** (floor bays, `Shell-x12-a1` bosses) | 6.0–9.7 mm | **3.5–3.8 mm** | **5.5 mm** (floor bays are 6.0 mm deep) | Shell |
| **M2** | **3.0 mm** (OV9281), **2.8 mm** (sound-detector retainer) | 6.0 mm | **3.2–3.5 mm** | **5.5 mm** | Camera front |

Rule of thumb: the knurl should be **0.4–0.8 mm wider than the hole**. Less and the insert spins or pulls out; more and it pushes a ring of plastic up around the rim and can split a thin boss.

> [!IMPORTANT]
> **If your inserts have a different outer diameter, change the hole size before you print, not after.** The holes are sized for the short knurled inserts above. Some common inserts do **not** fit as modelled:
>
> - PEM **IUTB** inserts (the Mouser line, OD 3.73 / 4.55 / 4.55 mm for M2 / M2.5 / M3) want Ø3.2 / Ø4.0 / Ø4.0 mm holes. The M2 and M2.5 holes here are too small for them, and the M3 holes are too big.
> - CNC Kitchen "Standard" inserts (OD 3.6 / 4.6 / 4.6 mm) also want Ø3.2 / Ø4.0 / Ø4.0 mm holes. The M3 size grips only 0.2 mm in a Ø4.4 hole, which is loose.
>
> To fit other inserts, aim for a hole about **0.5 mm smaller than the insert's outer diameter** and **at least 0.5 mm deeper than the insert is long**. Either edit the hole in [`step/Open-Flight-Monitor-3.step`](../step/Open-Flight-Monitor-3.step) and re-export the part, or use your slicer's hole compensation for that part (PrusaSlicer / OrcaSlicer: *X-Y hole compensation*; Cura: *Hole Horizontal Expansion*). Print one test boss before you print the whole set.

### Board-stack screws per shell

The four M2.5 screws that hold the battery board and the Pi go into the inserts in the bosses on the shell's rear wall. Those bosses are different in each shell, so **the screw length depends on which battery board (and shell) you print**.

How to work out the length (under the head):

> **screw length = everything the screw passes through above the boss + 3 mm or more into the insert**, and no more than the pocket depth below the boss face, or the tip bottoms out before the head clamps.

| Shell | Boss pocket (Ø × depth) | Hole pattern | What the screw passes through | Screw |
| --- | --- | --- | --- | --- |
| `Shell-x1202` with the **X1202 battery board** | Ø3.3 × 9.5 mm | 89.0 × 58.0 mm | The Raspberry Pi 5 board, then the X1202's mounting threads, then into the brass insert | **M2.5 × 10 or M2.5 × 12** (used on a real build). M2.5 × 8 does not reach far enough into the insert |
| `Shell-x1202` with **no battery board** | Ø3.3 × 9.5 mm | 89.0 × 58.0 mm | The 6 mm x1202 Pi adapter plate, if you print that optional plate | See [Adapters](#adapters) |
| `Shell-x1206` with the **X1206 battery board** | Ø3.3 × 7.5 mm | 101.0 × 58.0 mm | The X1206 board and whatever spacers sit between it and the boss | Not yet checked on a build: measure your stack, then add 3–7 mm |
| `Shell-x12-a1` with the **X1209 battery board** | Ø3.4 × 7.5 mm | 86.9 × 58.0 mm | The x1209 Pi adapter plate (4.5–4.7 mm thick at these holes) | Not yet checked on a build: by the rule above, M2.5 × 8 to M2.5 × 12 |

The holes all run 10° off square to the rear wall (the board stack leans with the case), so drive the screws along the hole.

## Tools

The M3 case screws sit deep in the shell. A short hex driver will not reach. You need a **2.5 mm ball-end hex key** with **at least 90 mm of reach** on the long arm for case mounting. [This long-arm pair](https://www.amazon.co.uk/dp/B0D4H8CHNR) is one option (~114 mm); any equivalent with ≥90 mm reach is fine.

A soldering iron is also required to heat-set the inserts.

## Per printed piece

### Shell

Same on every current `v1` shell (Ethernet, DC jack, power button). Old USB-C rear shells are [end of life](../stls/shell/eol/README.md). The x12-a1 shell is only for the X1209 battery board (with its adapter).

| Qty | Item | Role |
| --- | --- | --- |
| 4 | M2.5 insert | Battery board and Raspberry Pi |
| 4 | M2.5 screw | Battery board / Pi stack; length per shell in [Board-stack screws per shell](#board-stack-screws-per-shell) |
| 2 or 4 each | M2.5 insert | Each of **3 Adafruit module bays** you populate (skip empty bays) |
| 10 | M3×8 / M3×10 / M3×12 | Mount screen + lower front to the shell |
| 4 | M3 insert | **Adjustable feet only** — omit if using solid feet |
| 2 | M3 screw + nut, or M3 self-tapper | **Ethernet coupler only** — the flange screws into the two Ø4.0 mm rear holes, 27.0 mm apart. No insert: the holes are clearance, not insert pockets |

Adafruit total if all three bays are used: **6 or 12** extra M2.5 inserts (2 or 4 per bay).

The rear DC jack and power button clamp into their own Ø12.5 mm holes with the
nuts they ship with — no screws or inserts. See
[Rear I/O openings](parts/shell.md#rear-io-openings) for every rear hole
dimension and what fits it.

### Screen bezel

| Variant | M3 inserts |
| --- | --- |
| 800×480 | 4 — case mounting |
| Raspberry Pi Display | 4 — case mounting |
| Raspberry Pi Display 2 | 4 — case mounting |
| 1024×600 | 4 — case mounting, plus **4** for the panel (**8** total) |

The 10 case screws from the shell go into the 4 case-mounting inserts (shared with the lower front’s case inserts).

### Camera front

The current strip is camera + sound detector (`camera/v1/`). Compatible with **UART and USB OPS**. Camera-only and the previous sound-detector strip are [EOL](../stls/camera/eol/README.md).

| Qty | Item | Role |
| --- | --- | --- |
| 2 | M3 insert | Case mounting |
| 2 | M2 insert | OV9281 |
| 2 | M2 insert | Sound-detector retainer |

Print `Sound-Detector-Retainer.stl` with the camera front. The retainer screws into the two extra M2 inserts.

### Radar front (`stls/radar/v1/` — no-fill)

The filled front is [EOL](../stls/radar/eol/README.md).

**12× M3 inserts:**

| Qty | Role |
| --- | --- |
| 4 | OPS |
| 4 | IWR |
| 4 | Case mounting |

### Feet

Inserts for adjustable feet go in the **shell**, not in the foot STL.

| Variant | Shell | Foot |
| --- | --- | --- |
| Solid | No M3 inserts for feet | No inserts |
| Adjustable | 4× M3 insert (see shell) | Screws into those shell inserts |

### Adapters

| Part | Inserts | Screws |
| --- | --- | --- |
| x1202 Pi adapter (no battery board) | None | 6× M3×10 or M3×12 through the 6 mm plate |
| x1209 Pi adapter | None | 8× M2.5×5 or M2.5×6 (Pi / HAT) |

## Example carts

**800×480, X1206 battery board, solid feet, no Adafruit modules**

- **4× M2.5** inserts (battery board / Pi)
- **4× M2** inserts (2 camera + 2 sound-detector retainer)
- **6× M3** inserts (4 screen case + 2 camera case)
- **10× M3×8/10/12** (fronts to shell)

**Same with adjustable feet**

- Add **4× M3** (feet in the shell)

**1024×600 radar**

- Screen: **8× M3** inserts
- Radar: **12× M3** inserts (4 OPS + 4 IWR + 4 case)
- Shell: still **4× M2.5** (battery board / Pi), **10× M3** screws, plus feet/Adafruit as above
- Camera: **4× M2** (2 OV9281 + 2 retainer) plus **2× M3** case inserts

**X1209 battery board** — add the x12-a1 shell (not standalone) and **8× M2.5** for the adapter.

**No battery board** — nothing extra. Only if you print the optional x1202 Pi adapter: add **6× M3×10/12**.

## Install order

Follow [Assembly](assembly.md). Short version:

1. Heat-set inserts.
2. Mount every module to its printed part (current no-fill radar can be flashed after mounting).
3. Connect cables to the Pi.
4. Screw fronts to the shell: radar, then camera, then screen.
5. Feet last.

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
