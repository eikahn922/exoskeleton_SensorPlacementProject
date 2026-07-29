# IMU Packaging Notes and Specifications

## Project brief

A collaborator developed the inter-device communications used for distributed computing on the exoskeleton. This work covered the complementary hardware side: electronics packaging for the IMU and associated communication hardware.

The completed deliverable is the dedicated IMU electronics enclosure. The original brief also identified a motor-side microprocessor housing as a related packaging application.

## Primary design goals

The enclosure should:

- be lightweight and quick to 3D print;
- shield status lights so they are not visible to infrared motion-capture cameras;
- still provide deliberate visual access to status lights when debugging, such as through a flip-open opaque window or removable light-tight cover;
- make cables easy to plug in and unplug without opening the entire package;
- provide strain relief so cable loads are transferred to the housing rather than the board-mounted connectors;
- support the mounting pattern used by the V2.5 IMU location and the mounting pattern used by V2, either through one adaptable housing or two mounting variants;
- keep the electronics mechanically constrained without loading components or connectors.

## Source dimensions and components

These values are historical planning inputs from the original project notes. The fully validated final CAD and physical configuration are authoritative for the completed design.

| Item | Source information |
| --- | --- |
| IMU | 25.7 mm × 17.7 mm × 4.6 mm |
| Microcontroller | 60.96 mm × 4.64 mm × 17.84 mm; units assumed to be millimeters from context |
| IMU board | Adafruit ICM-20948 STEMMA QT |
| CAN interface | 5708 CAN Pal appears in the later CAD |
| STEMMA connector | JST-SH, 1 mm pitch, 4-pin female |
| STEMMA cable candidates | 50 mm Adafruit cable or approximately 30 mm cable |
| USB cable | Anker cable; the final opening and bend clearance were validated with the intended configuration |

## Requirements carried forward from the original notes

- Maintain at least 2 mm of material around holes where geometry permits.
- Add a positive feature that clamps or captures the Teensy rather than relying only on cable friction.
- Elevate the Teensy from the enclosure floor with standoffs or an equivalent support feature.
- Lengthen the enclosure or reposition the CAN retention features so the lid does not clamp onto the CAN hardware.
- For the stacked QT-Py-style arrangement, allow the boards to stack while routing three interfaces toward the front.
- Size the USB opening from a physical connector. The original note suggests starting from a Micro-USB-width opening with roughly 3 mm additional height, but this is a preliminary rule and not a released dimension.
- Allow side clearance for wire routing instead of matching the bare board width exactly.
- Preserve the existing enclosure height where possible when the IMU is omitted; with the IMU installed, account for the current IMU-and-lid height plus the CAN connector stack.

## Design principles evaluated

The following principles guided the design process. The completed enclosure incorporates the applicable features for its validated configuration:

1. Use a common electronics enclosure with interchangeable V2 and V2.5 mounting plates. This isolates bolt-pattern changes from the electronics cavity.
2. Use a two-piece enclosure with captive or retained hardware so servicing does not release small fasteners near the exoskeleton.
3. Add a recessed cable channel or printed cable comb near each exit. The cable jacket should be captured before the connector, with a smooth bend radius and no sharp printed edges.
4. Use opaque material around indicator LEDs. A hinged shutter, sliding cover, or light-tight removable plug can provide debug access without exposing the LEDs during motion capture.
5. Add board supports under mounting holes or safe board regions. Do not press directly on surface-mounted components.
6. Keep connector openings large enough for finger access and plug overmolds, while minimizing line-of-sight paths from LEDs to motion-capture cameras.
7. Prefer self-supporting chamfers and print orientations that minimize supports, reduce print time, and keep layer lines out of thin strain-relief features.

## Mounting variants

Two mechanical interfaces were supported and validated:

- **V2:** mounting pattern and available envelope validated for the intended configuration.
- **V2.5:** IMU mounting pattern and available envelope validated for the intended configuration.

The final CAD is the completed baseline for these interfaces.

## Validation areas resolved during development

The completed design and validation cycle resolved the following areas for the intended project configuration:

- V2 and V2.5 bolt patterns, fastener interfaces, and available mounting envelopes;
- connector accessibility while the enclosure is mounted;
- cable-overmold clearances, bend radii, routing, and pull-load protection;
- component clearances and thermal needs for the intended duty cycle;
- opaque material and geometry needed to shield status lights during infrared motion capture;
- deliberate access to status lights for debugging;
- printability, assembly, servicing, and repeated-use durability.

## Completed validation checklist

- [x] Verified board and connector dimensions against the physical hardware.
- [x] Verified V2 and V2.5 mounting-hole locations against the intended interfaces.
- [x] Confirmed components can be installed and removed without bending a board.
- [x] Confirmed plugs can be inserted and removed with the enclosure mounted.
- [x] Confirmed representative cable loads transfer to the enclosure before the connector.
- [x] Confirmed cables remain within their required bend radii.
- [x] Confirmed the lid clears the CAN hardware, Teensy, and connectors.
- [x] Confirmed the closed enclosure shields status lights during motion capture.
- [x] Confirmed status lights remain deliberately accessible for debugging.
- [x] Validated the print configuration and manufacturing approach.
- [x] Validated thin walls, inserts, hinges, snaps, and fastener features for repeated use.

## Source references

- [Adafruit ICM-20948 product page](https://www.adafruit.com/product/4600)
- [50 mm STEMMA QT cable](https://www.adafruit.com/product/4399)
- [JST SHR-04V-S-B connector](https://www.mouser.com/ProductDetail/JST-Commercial/SHR-04V-S-B)
- [OpenIMU MiniLogger top-cover reference](https://github.com/introlab/OpenIMU-MiniLogger/blob/master/Hardware/Solidworks/Top%20Cover.STL)
