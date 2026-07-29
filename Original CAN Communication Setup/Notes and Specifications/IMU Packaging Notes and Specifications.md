# IMU Packaging Notes and Specifications

## Project brief

A collaborator is setting up the inter-device communications used for distributed computing on the exoskeleton. This work covers the complementary hardware side: electronics packaging for the IMU and associated communication hardware.

The IMU setup requires a dedicated enclosure. Depending on the most efficient motor architecture, the motor setup may also need a bolt-on housing for its microprocessor.

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

These values come from the original project notes and must be checked against the physical hardware before a final print.

| Item | Source information |
| --- | --- |
| IMU | 25.7 mm × 17.7 mm × 4.6 mm |
| Microcontroller | 60.96 mm × 4.64 mm × 17.84 mm; units assumed to be millimeters from context |
| IMU board | Adafruit ICM-20948 STEMMA QT |
| CAN interface | 5708 CAN Pal appears in the later CAD |
| STEMMA connector | JST-SH, 1 mm pitch, 4-pin female |
| STEMMA cable candidates | 50 mm Adafruit cable or approximately 30 mm cable |
| USB cable | Anker cable; measure the actual plug and bend radius before finalizing the opening |

## Requirements carried forward from the original notes

- Maintain at least 2 mm of material around holes where geometry permits.
- Add a positive feature that clamps or captures the Teensy rather than relying only on cable friction.
- Elevate the Teensy from the enclosure floor with standoffs or an equivalent support feature.
- Lengthen the enclosure or reposition the CAN retention features so the lid does not clamp onto the CAN hardware.
- For the stacked QT-Py-style arrangement, allow the boards to stack while routing three interfaces toward the front.
- Size the USB opening from a physical connector. The original note suggests starting from a Micro-USB-width opening with roughly 3 mm additional height, but this is a preliminary rule and not a released dimension.
- Allow side clearance for wire routing instead of matching the bare board width exactly.
- Preserve the existing enclosure height where possible when the IMU is omitted; with the IMU installed, account for the current IMU-and-lid height plus the CAN connector stack.

## Recommended packaging architecture

The following are engineering recommendations based on the brief, not yet approved requirements:

1. Use a common electronics enclosure with interchangeable V2 and V2.5 mounting plates. This isolates bolt-pattern changes from the electronics cavity.
2. Use a two-piece enclosure with captive or retained hardware so servicing does not release small fasteners near the exoskeleton.
3. Add a recessed cable channel or printed cable comb near each exit. The cable jacket should be captured before the connector, with a smooth bend radius and no sharp printed edges.
4. Use opaque material around indicator LEDs. A hinged shutter, sliding cover, or light-tight removable plug can provide debug access without exposing the LEDs during motion capture.
5. Add board supports under mounting holes or safe board regions. Do not press directly on surface-mounted components.
6. Keep connector openings large enough for finger access and plug overmolds, while minimizing line-of-sight paths from LEDs to motion-capture cameras.
7. Prefer self-supporting chamfers and print orientations that minimize supports, reduce print time, and keep layer lines out of thin strain-relief features.

## Mounting variants

Two mechanical interfaces must be supported:

- **V2:** bolt pattern and available envelope are still to be measured and recorded.
- **V2.5:** final IMU mounting pattern and available envelope are still to be measured and recorded.

Do not release a housing for printing until both interfaces are represented by controlled dimensions or verified reference CAD.

## Open questions

- What are the exact V2 and V2.5 bolt patterns, fastener sizes, and allowable screw engagement depths?
- Does the motor architecture need a separate processor enclosure, or can it use the common electronics package?
- Which connectors must remain accessible while the enclosure is mounted?
- What are the actual cable overmold dimensions, minimum bend radii, and expected pull loads?
- How much airflow or thermal conduction do the Teensy and CAN hardware require in the intended operating duty cycle?
- Which opaque print material and wall thickness reliably block the relevant infrared camera wavelengths?
- Should debug-light access be tool-free, captive, and operable while worn?
- What environmental exposure should be expected: sweat, impact, abrasion, dust, or repeated cleaning?

## Prototype validation checklist

- [ ] Verify every board and connector dimension against physical hardware.
- [ ] Verify V2 and V2.5 mounting-hole locations with reference CAD or a physical gauge.
- [ ] Confirm all components can be installed and removed without bending a board.
- [ ] Confirm plugs can be inserted and removed with the enclosure mounted.
- [ ] Apply a representative cable-yank load and verify the enclosure takes the load before the connector.
- [ ] Check that cables meet their minimum bend radii.
- [ ] Confirm the lid does not contact the CAN hardware, Teensy, or connectors.
- [ ] Confirm status lights are not detected by the motion-capture cameras with the cover closed.
- [ ] Confirm status lights remain visible enough for debugging when the access feature is open.
- [ ] Record print orientation, material, layer height, support usage, mass, and print time.
- [ ] Inspect thin walls, heat-set inserts, hinges, snaps, and fastener bosses after repeated service cycles.

## Source references

- [Adafruit ICM-20948 product page](https://www.adafruit.com/product/4600)
- [50 mm STEMMA QT cable](https://www.adafruit.com/product/4399)
- [JST SHR-04V-S-B connector](https://www.mouser.com/ProductDetail/JST-Commercial/SHR-04V-S-B)
- [OpenIMU MiniLogger top-cover reference](https://github.com/introlab/OpenIMU-MiniLogger/blob/master/Hardware/Solidworks/Top%20Cover.STL)
