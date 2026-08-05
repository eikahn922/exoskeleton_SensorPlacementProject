# Pelvis IMU Mounting System

This subsystem mounts the compact IMU electronics package to the pelvis/back-plate region of the hip-knee exoskeleton. Its adjustable configuration provides controlled translation along the mounting structure so the sensor can be placed at a more comparable relative location across participants.

## Design objective

The design aims to preserve:

- a repeatable initial sensor-frame orientation;
- a defined relative position referenced to the exoskeleton mounting structure;
- rigid support during gait;
- practical adjustment and locking;
- cable clearance and access to the local electronics package.

The adjustment direction is intentionally described without assigning it to Y or Z. The global CAD coordinate-frame convention still needs to be verified, and the meaningful engineering question is translation relative to the pelvis mounting structure.

## Why both static and adjustable versions are included

The [Static Version](CAD/Static%20Version) is a completed alternative configuration with no translation adjustment. The [Final Version](CAD/Final%20Version) is the completed adjustable configuration.

Both are preserved because it is not yet established that translational adjustment provides enough benefit at the pelvis to justify the additional mechanism. Comparative fitting and gait testing will determine whether it materially improves placement and alignment repeatability.

## Start here

- [CAD guide and design history](CAD)
- [Pelvis IMU Mounting Design Notes](Notes%20and%20Specifications/Pelvis%20IMU%20Mounting%20Design%20Notes.md)
- [OPEN THIS FIRST – Final Version](CAD/Final%20Version/OPEN%20THIS%20FIRST%20-%20Final%20Version)
- [OPEN THIS FIRST – Full Assembly](CAD/Full%20Assembly/OPEN%20THIS%20FIRST%20-%20Full%20Assembly)
