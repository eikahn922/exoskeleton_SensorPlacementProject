# Final Compact CAN Communications Packaging

This is the completed, fully validated compact implementation of the exoskeleton's IMU and communications electronics package. It uses an Adafruit QT Py SAMD21 development board with the IMU packaging and was implemented because it provides a smaller package than the earlier Teensy-based architecture.

## Project at a glance

| | |
| --- | --- |
| **Status** | Complete and fully validated for its intended exoskeleton configuration |
| **Controller** | Adafruit QT Py SAMD21 development board |
| **Sensor** | IMU package represented by the Adafruit and `qtpiBox1_imu` CAD parts |
| **Why this architecture** | Reduced enclosure size while preserving the original packaging requirements |
| **CAD history** | Version 1 initial compact package; Version 2 final validated refinement |

The CAD directly models the QT Py, IMU, enclosure components, clamp, and final assembly. It supports the communication-node hardware arrangement without carrying forward the larger Teensy enclosure geometry.

## Shared engineering requirements

The compact implementation preserved the requirements established for the original package:

- lightweight and quick to 3D print;
- shield status lights during infrared motion capture while retaining deliberate debug access;
- make required connectors easy to reach;
- transfer cable loads into the enclosure rather than board-mounted connectors;
- constrain electronics without loading surface-mounted components;
- maintain the validated exoskeleton mounting interface;
- preserve practical assembly and service access.

## Explore the work

- [`CAD/Version 1`](CAD/Version%201) contains the initial compact assembly, its original ZIP, and extracted SolidWorks files.
- [`CAD/Version 2`](CAD/Version%202) contains the final validated refinement, its original ZIP, and extracted SolidWorks files.
- [`QT Py IMU Packaging Specifications`](Notes%20and%20Specifications/QT%20Py%20IMU%20Packaging%20Specifications.md) records the compact architecture, inherited requirements, version-specific constraints, and completed validation.
