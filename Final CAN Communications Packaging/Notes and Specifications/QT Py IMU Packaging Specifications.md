# QT Py IMU Packaging Specifications

## Completion status

**Complete and fully validated.** This compact QT Py + IMU package is the implemented final communications-packaging architecture for its intended exoskeleton configuration.

## Architecture and selection rationale

The package integrates:

- **one** Adafruit QT Py SAMD21 development board with STEMMA QT;
- **one** IMU and its dedicated enclosure region;
- the enclosure, clamp, and interface geometry required by the communication-node arrangement.

The final configuration therefore contains exactly **1 QT Py and 1 IMU**.

This architecture was selected and implemented because the QT Py enabled a more compact package than the earlier Teensy-based enclosure while preserving the same mechanical, service, and motion-capture requirements.

## Shared requirements inherited from the original package

- Keep the package lightweight and quick to 3D print.
- Shield status lights from infrared motion-capture cameras.
- Preserve deliberate access to status lights for debugging.
- Keep required plugs accessible while the enclosure is mounted.
- Use enclosure-level strain relief so cable loads do not reach board-mounted connectors first.
- Support the validated exoskeleton mounting interface.
- Constrain boards without pressing on surface-mounted components.
- Maintain adequate component, lid, wire-routing, and connector clearances.

## Final Version design requirements

The advisor notes defining the compact QT Py setup apply to the Final Version implementation:

- Stack the three functional elements in the compact arrangement and route the three required interfaces toward the front.
- Size the USB opening for the intended Anker USB cable. The early note proposed a Micro-USB-width opening with approximately 3 mm of additional height; the final validated CAD is authoritative.
- With the IMU installed, accommodate the IMU-and-lid height plus the communication connector stack.
- Keep the enclosure width close to the IMU width while retaining practical side clearance for wires.
- When the IMU is omitted, preserve the height of the established enclosure configuration.

## Source component dimensions

The source notes list the IMU envelope as **25.7 mm × 17.7 mm × 4.6 mm**. These values were planning inputs; the completed Final Version CAD and validated physical configuration are authoritative for manufacturing.

## CAD version history

| Version | Source archive | Design role |
| --- | --- | --- |
| Version 1 | `qtpi#1 (2).zip` | Initial compact QT Py, IMU, enclosure, and clamp assembly |
| Final Version | `qtpi#1.zip` | Refined final assembly containing 1 QT Py and 1 IMU |

## Completed validation

- [x] Verified QT Py and IMU fit in the completed enclosure.
- [x] Verified board support and component clearances.
- [x] Verified connector access with the package mounted.
- [x] Verified cable routing, bend clearance, and strain relief.
- [x] Verified lid and enclosure clearances across the assembled stack.
- [x] Verified status-light shielding during infrared motion capture.
- [x] Verified deliberate status-light access for debugging.
- [x] Verified mounting compatibility for the intended exoskeleton configuration.
- [x] Validated printability, assembly, service access, and repeated-use durability.

## Component reference

- [Adafruit QT Py SAMD21 Dev Board with STEMMA QT](https://www.adafruit.com/product/4600)
