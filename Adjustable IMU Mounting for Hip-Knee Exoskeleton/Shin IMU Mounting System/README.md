# Shin IMU Mounting System

**Status: work in progress**

This subsystem develops an adjustable shin-mounted IMU interface for the knee portion of the hip-knee exoskeleton. It is intended to let the sensor be repositioned both along the shin and side-to-side around the mounting region while preserving a consistent initial orientation relative to the leg and exoskeleton.

## Why this design exists

Participants have different limb lengths and circumferences. A fixed attachment point can therefore place the same sensor at a different relative location from one person to another. The adjustable shin mount is being developed to create a repeatable fitting procedure that can:

- place the IMU at a comparable relative height along each participant's shin;
- adjust its side-to-side position around the mounting region;
- preserve a consistent initial sensor-frame orientation;
- keep the sensor rigidly coupled to the wearer and exoskeleton during gait;
- reduce placement-driven differences in recorded gait signals.

More repeatable placement should make training data more consistent and may improve transfer of control or estimation algorithms between participants. That algorithmic benefit is a design hypothesis and still requires experimental validation.

## Mechanical concept

- The large cylinder in the visualization represents the participant's shin.
- The shin cuff is designed to accept a strap routed through the attachment on the knee exoskeleton, securing the cuff to the wearer.
- A foam interface is included to increase friction against the wearer and reduce slipping during movement.
- The shank-bar and cuff iterations explore the geometry needed to combine adjustment, secure attachment, and integration with the knee exoskeleton.

## Start here

| View | Purpose | Recruiter entry point |
| --- | --- | --- |
| **Zoomed-In Shin IMU Assembly** | Closest view of the sensor, foam interface, cuff, representative shin, and shank-bar connection | [OPEN THIS FIRST](CAD/Zoomed-In%20Shin%20IMU%20Assembly/OPEN%20THIS%20FIRST%20-%20Zoomed-In%20Shin%20IMU%20Assembly) |
| **Full Knee Exoskeleton Assembly** | System-level context showing the shin mount on the complete knee exoskeleton | [OPEN THIS FIRST](CAD/Full%20Knee%20Exoskeleton%20Assembly/OPEN%20THIS%20FIRST%20-%20Full%20Knee%20Exoskeleton%20Assembly) |
| **Component Iterations** | Two shin-cuff iterations and four shank-bar iterations | [Browse the design history](CAD/Component%20Iterations) |

- [CAD guide](CAD)
- [Shin IMU Mounting Design Notes](Notes%20and%20Specifications/Shin%20IMU%20Mounting%20Design%20Notes.md)

## Current development questions

- How much longitudinal and side-to-side adjustment is needed to fit the expected participant population?
- Does the strap-and-foam interface prevent migration during gait?
- Can the final fitting procedure reproduce both relative sensor position and initial orientation across participants?
- Does the resulting placement consistency measurably reduce cross-participant variation in the gait data?
