# Required hardware

Install inserts with a soldering iron, square to the boss, flush with the plastic. Do not drive a screw into bare plastic in an insert hole.

## Standard parts (buy these)

| Part | Spec | Used for |
| --- | --- | --- |
| Heat-set insert | **M3 × 4 mm** short knurled brass | Fronts, screen, adjustable-feet bosses in the shell |
| Heat-set insert | **M2.5 × 4 mm** short knurled brass | UPS / Pi and Adafruit bays in the shell |
| Heat-set insert | **M2 × 4 mm** short knurled brass | Camera module (OV9281) and sound-detector retainer |
| Case screw | **M3×8**, **M3×10**, or **M3×12** | 10 screws that mount the fronts to the shell |

Pick M3 length after a dry fit (start with **M3×10**).

## Tools

The M3 case screws sit deep in the shell. A short hex driver will not reach. You need a **2.5 mm ball-end hex key** with **at least 90 mm of reach** on the long arm for case mounting. [This long-arm pair](https://www.amazon.co.uk/dp/B0D4H8CHNR) is one option (~114 mm); any equivalent with ≥90 mm reach is fine.

A soldering iron is also required to heat-set the inserts.

## Per printed piece

### Shell

Same on every current `v1` shell (Ethernet, DC jack, power button). Old USB-C rear shells are [end of life](../stls/shell/eol/README.md). The x12-a1 shell is only for x1209 (with its adapter).

| Qty | Item | Role |
| --- | --- | --- |
| 4 | M2.5 insert | UPS and Raspberry Pi |
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

The current strip is camera + sound detector (`camera/v1/`). Compatible with **UART and USB OPS**. Camera-only is [EOL](../stls/camera/eol/README.md).

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
| x1202 Pi adapter (no UPS) | None | 6× M3×10 or M3×12 through the 6 mm plate |
| x1209 Pi adapter | None | 8× M2.5×5 or M2.5×6 (Pi / HAT) |

## Example carts

**800×480, x1206, solid feet, no Adafruit modules**

- **4× M2.5** inserts (UPS / Pi)
- **4× M2** inserts (2 camera + 2 sound-detector retainer)
- **6× M3** inserts (4 screen case + 2 camera case)
- **10× M3×8/10/12** (fronts to shell)

**Same with adjustable feet**

- Add **4× M3** (feet in the shell)

**1024×600 radar**

- Screen: **8× M3** inserts
- Radar: **12× M3** inserts (4 OPS + 4 IWR + 4 case)
- Shell: still **4× M2.5** (UPS / Pi), **10× M3** screws, plus feet/Adafruit as above
- Camera: **4× M2** (2 OV9281 + 2 retainer) plus **2× M3** case inserts

**x1209** — add the x12-a1 shell (not standalone) and **8× M2.5** for the adapter.

**No UPS** — add **6× M3×10/12** for the x1202 Pi adapter.

## Install order

Follow [Assembly](assembly.md). Short version:

1. Heat-set inserts.
2. Mount every module to its printed part (current no-fill radar can be flashed after mounting).
3. Connect cables to the Pi.
4. Screw fronts to the shell: radar, then camera, then screen.
5. Feet last.

If you like the design, [buy me a coffee](https://buymeacoffee.com/cormacmcgrath).
