# Adjustable IMU Mounting for a Hip-Knee Exoskeleton

This is the repository's primary sensor-placement project. It develops adjustable IMU mounting hardware so participants with different body geometries can be fitted with sensors at a comparable relative location and initial orientation.

## Engineering motivation

Inconsistent placement can introduce setup-dependent differences into gait signals. The mount is intended to reduce that variation by providing a controlled mechanical reference instead of selecting a new sensor location for every participant.

More repeatable placement is expected to:

- improve consistency across gait datasets;
- reduce variation caused by setup rather than movement;
- simplify comparison between participants;
- support control and estimation models that transfer more effectively from person to person.

These are design goals. The effect on model performance will be evaluated experimentally.

## Current subsystems

| Subsystem | Scope | Status |
| --- | --- | --- |
| [Pelvis IMU Mounting System](Pelvis%20IMU%20Mounting%20System) | Static Version, Iterations 1–3, Final Version, and Full Assembly | Final CAD complete; static-versus-adjustable comparison planned |
| [Thigh IMU Mounting System](Thigh%20IMU%20Mounting%20System) | Strap-adjustable thigh cuff with bounded vertical and side-to-side positioning | Work in progress; fit, retention, slip, and placement-repeatability validation planned |
| [Shin IMU Mounting System](Shin%20IMU%20Mounting%20System) | Zoomed-in assembly, full knee-exoskeleton context, two cuff iterations, and four shank-bar iterations | Work in progress; fit, slip, placement-repeatability, and gait validation planned |

The distributed electronics packages elsewhere in this repository support the same system by placing computing near the sensors and actuators, reducing long cable runs and wiring complexity.
