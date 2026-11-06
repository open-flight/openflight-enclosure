# Pi adapters

Small plates that sit between the Pi and the shell. Print only when the table says to.

X1202, X1206 and X1209 are Geekworm **battery (UPS) boards** that sit under the Pi ([what the codes mean](../choosing-a-variant.md#what-x1202-x1206-and-x1209-mean)). The **x1202 shell is shaped for the X1202 battery board**. If you run from a wall supply with no battery board, keep that shell. The x1202 Pi adapter is optional, only for builders who use the x1202 shell without the X1202 board; you do not need to print it.

| Battery (UPS) board | STL | Print? |
| --- | --- | --- |
| X1202 battery board | — | No — the X1202 fills the shell |
| no battery board | [`stls/adapters/v1/x1202 Pi Adapater.stl`](../../stls/adapters/v1/x1202%20Pi%20Adapater.stl) | Optional — not needed. Only for the x1202 shell without the X1202 board |
| X1206 battery board | — | No |
| X1209 battery board | [`stls/adapters/v1/x1209 PI Adapater.stl`](../../stls/adapters/v1/x1209%20PI%20Adapater.stl) | Yes — required. Pairs with the **x12-a1 shell** (do not use that shell without this adapter) |

Filenames keep the original spelling (`Adapater`).

## Hardware

See [Required hardware](../hardware.md).

| Part | Inserts | Screws |
| --- | --- | --- |
| x1202 Pi adapter | None | 6× M3×10 or M3×12 (Ø3.4–3.5 mm through, plate is 6 mm thick) |
| x1209 Pi adapter | None | 8× M2.5×5 or M2.5×6 (Ø2.7 mm, Pi / HAT) |

## Print notes

TODO: layer orientation so mounting holes are round; avoid supports in the holes.
