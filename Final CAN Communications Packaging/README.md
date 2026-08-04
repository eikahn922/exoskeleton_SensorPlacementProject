# Final Compact CAN Communications Packaging

This is the completed, fully validated compact implementation of the exoskeleton's IMU and distributed-communications electronics package. The final configuration contains exactly **1 Adafruit QT Py SAMD21 and 1 IMU**.

The QT Py architecture was selected because it reduced package size relative to the earlier Teensy-based enclosure while preserving the mechanical, service, and motion-capture requirements. Locating this hardware near the sensing point also supports the distributed system's practical goal of reducing long cable runs and simplifying wiring across the exoskeleton.

## Project at a glance

| | |
| --- | --- |
| **Status** | Complete and fully validated for its intended exoskeleton configuration |
| **Controller quantity** | 1 Adafruit QT Py SAMD21 |
| **Sensor quantity** | 1 IMU |
| **Why this architecture** | Smaller local electronics package with simpler system wiring |
| **CAD history** | Version 1 initial compact package; Final Version validated refinement |

## Shared engineering requirements

- Remain lightweight and quick to 3D print.
- Shield status lights during infrared motion capture while retaining deliberate debug access.
- Keep required connectors accessible.
- Transfer cable loads into the enclosure rather than board-mounted connectors.
- Constrain electronics without loading surface-mounted components.
- Maintain the validated exoskeleton mounting interface.
- Preserve practical assembly and service access.

## Explore the work

- [CAD overview](CAD) explains the two entry assemblies and file structure.
- [Version 1 – OPEN THIS FIRST](CAD/Version%201/OPEN%20THIS%20FIRST%20-%20Compact%20QT%20Py%20Package%20-%20Version%201) opens the initial compact-package stage.
- [Final Version – OPEN THIS FIRST](CAD/Final%20Version/OPEN%20THIS%20FIRST%20-%20Compact%20QT%20Py%20Package%20-%20Final) opens the completed, fully validated stage.
- [QT Py IMU Packaging Specifications](Notes%20and%20Specifications/QT%20Py%20IMU%20Packaging%20Specifications.md) records the architecture, inherited requirements, and completed validation.
