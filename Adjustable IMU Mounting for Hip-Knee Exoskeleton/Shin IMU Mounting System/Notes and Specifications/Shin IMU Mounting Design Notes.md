# Shin IMU Mounting Design Notes and Specifications

## Project status

This shin subsystem is **still in development**. The CAD captures the current mechanical concept and iteration history; it should not be presented as a fully validated final design.

## Functional objective

Provide an adjustable attachment for the shin IMU that allows repeatable placement across participants with different leg geometries. Adjustment is described relative to the leg and mounting structure rather than assigned to a global SolidWorks axis:

1. **Longitudinal adjustment:** move the sensor up or down along the shin.
2. **Side-to-side adjustment:** reposition the sensor around the shin/mounting region.
3. **Orientation control:** keep the initial IMU frame aligned consistently after fitting.

The target outcome is reduced setup-dependent variation in gait signals. More consistent inputs may improve cross-participant comparison and model transfer, but those data and algorithm effects still require experimental testing.

## Physical interpretation of the CAD

| CAD element | Intended physical role |
| --- | --- |
| Large cylinder (`Shin.SLDPRT`) | Simplified representation of a human shin for packaging and fit visualization |
| Shin cuff | Wearable interface surrounding the shin region |
| Strap feature | Route for a strap that passes through the knee-exoskeleton attachment and secures the cuff to the participant |
| Foam insert (`foamShinIMU.SLDPRT`) | High-friction interface intended to reduce slipping and improve comfort/contact |
| Shank bar | Structural knee-exoskeleton component used to support and locate the shin mounting system |
| IMU package components | Local sensor enclosure and attachment hardware |

## Design requirements

- Support repeatable longitudinal and side-to-side sensor placement.
- Preserve a consistent initial sensor-frame orientation.
- Remain fixed relative to the wearer and exoskeleton during gait.
- Accommodate realistic variation in shin length and circumference.
- Provide a practical strap path through the knee-exoskeleton attachment.
- Use the foam interface to increase friction and limit cuff migration.
- Avoid obstructing normal knee-exoskeleton motion or required hardware.
- Keep the IMU package accessible for installation, removal, and cable connection.
- Maintain a lightweight, printable, and serviceable mechanical design.

## Iteration record

### Shin cuff

- **Iteration 1:** first supplied foam-backed cuff assembly.
- **Iteration 2:** later supplied foam-backed cuff assembly and the cuff configuration used inside the zoomed-in visualization.

### Shank bar

- **Iteration 1:** earliest supplied bar geometry.
- **Iteration 2:** first refinement.
- **Iteration 3:** second refinement.
- **Iteration 4:** latest supplied bar geometry and the bar used in the zoomed-in visualization.

## Planned validation

- Fit the system to participants spanning the intended anthropometric range.
- Record achievable longitudinal and side-to-side adjustment ranges.
- Measure repeatability of relative IMU position after repeated fitting.
- Measure repeatability of the initial sensor-frame orientation.
- Inspect strap routing, pressure distribution, comfort, and donning time.
- Test for cuff migration and rotation during representative gait trials.
- Confirm that the foam increases grip without causing unacceptable compression or discomfort.
- Verify clearance throughout the knee exoskeleton's expected range of motion.
- Compare gait signals across repeated fittings and participants.
- Evaluate whether placement consistency improves model robustness or person-to-person transfer.

## CAD handling

Open the top-level files beginning with **OPEN -**. Supporting files retain their original SolidWorks filenames so references remain recognizable. After the GitHub-oriented reorganization, SolidWorks may request a one-time relink; select dependencies from the same entry folder or its packaged component archive only.
