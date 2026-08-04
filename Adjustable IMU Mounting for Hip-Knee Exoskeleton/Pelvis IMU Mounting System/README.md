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

The [Static Reference](CAD/01%20Static%20Reference) provides a baseline with no translation adjustment. The [Final Adjustable Mount](CAD/05%20Final%20Adjustable%20Mount) represents the final adjustable CAD iteration.

Both are preserved because it is not yet established that translational adjustment provides enough benefit at the pelvis to justify the additional mechanism. Comparative fitting and gait testing will determine whether it materially improves placement and alignment repeatability.

## Start here

- [CAD guide and design history](CAD)
- [Pelvis IMU Mounting Design Notes](Notes%20and%20Specifications/Pelvis%20IMU%20Mounting%20Design%20Notes.md)
- [OPEN THIS FIRST – Final Adjustable Pelvis IMU Mount](CAD/05%20Final%20Adjustable%20Mount/OPEN%20THIS%20FIRST%20-%20Final%20Adjustable%20Pelvis%20IMU%20Mount)
- [OPEN THIS FIRST – Full Exoskeleton Integration Context](CAD/06%20Full%20Exoskeleton%20Integration%20Context/OPEN%20THIS%20FIRST%20-%20Full%20Exoskeleton%20Integration%20Context)
