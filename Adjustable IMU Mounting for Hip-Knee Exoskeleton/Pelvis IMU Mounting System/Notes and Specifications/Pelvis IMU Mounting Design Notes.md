# Pelvis IMU Mounting Design Notes

## Project purpose

The pelvis IMU mounting system was developed to make sensor placement more repeatable across users of a hip-knee exoskeleton. Participants have different body dimensions and require different exoskeleton adjustments, but the sensor should begin each trial at a comparable location and orientation relative to the pelvis mounting structure.

Reducing placement-induced variation is expected to make gait data more consistent and support models that transfer more effectively between participants. This is the engineering hypothesis motivating the adjustable mount; it is not presented as a completed algorithm-performance result.

## Mechanical reference and orientation

The mount should establish:

- a repeatable initial IMU coordinate-frame orientation;
- a comparable relative position referenced to the exoskeleton/back-plate structure;
- rigid attachment so the IMU does not shift relative to the structure during gait;
- controlled translation to accommodate participant geometry;
- a positive lock after adjustment.

The IMU naturally changes global orientation as the exoskeleton moves through gait. The objective is not to keep it globally pointed in a fixed direction; it is to standardize the initial alignment and preserve the sensor-to-structure relationship during motion.

## Adjustment-axis terminology

The source description raised whether adjustment occurs along a Y or Z axis. Those labels depend on the SolidWorks coordinate frame and should not be assumed without verifying the model datum.

In this repository, the degree of freedom is described as **translation along the pelvis mounting structure** or **vertical/longitudinal placement adjustment**. This wording captures the mechanical function without assigning an unsupported global-axis label.

## Design requirements

| Requirement | Engineering rationale |
| --- | --- |
| Comparable relative placement | Reduces participant-to-participant setup variation |
| Repeatable initial orientation | Makes IMU coordinate frames more consistent at the start of a trial |
| Rigid locking during gait | Prevents adjustment slip from contaminating measurements |
| Practical fit range | Accommodates participant and exoskeleton setup differences |
| Compact local electronics support | Keeps the IMU and controller close to the sensing location |
| Cable clearance and strain management | Avoids connector loading and interference during motion |
| Fast, understandable setup | Makes repeated participant fitting less operator-dependent |
| Self-contained CAD stages | Preserves each design iteration and its matching dependencies |

## Static and adjustable configurations

### Static Reference

The static back-plate mount is retained as the experimental baseline. It provides a simpler fixed attachment without translational adjustment.

### Adjustable Mount

The adjustable design adds controlled translation along the mounting structure. Iterations 2–4 record development of the slider, holder, locking hardware, and integrated electronics arrangement. **ASM #5 is labeled Final Adjustable Mount** and represents the final adjustable CAD iteration.

Both configurations remain in the repository because the pelvis-specific benefit of translation has not yet been established. The static version may be preferable if the adjustment does not materially improve repeatability.

## CAD design history

| Stage | Main assembly | Design role |
| --- | --- | --- |
| 01 Static Reference | OPEN - Static Pelvis IMU Mount.SLDASM | Fixed baseline for comparison |
| 02 Adjustable Mount – Iteration 2 | OPEN - Adjustable Pelvis IMU Mount - Iteration 2.SLDASM | First supplied slider-based assembly |
| 03 Adjustable Mount – Iteration 3 | OPEN - Adjustable Pelvis IMU Mount - Iteration 3.SLDASM | Refined holder and adjustment hardware |
| 04 Adjustable Mount – Iteration 4 | OPEN - Adjustable Pelvis IMU Mount - Iteration 4.SLDASM | Further mechanism and system integration |
| 05 Final Adjustable Mount | OPEN - Final Adjustable Pelvis IMU Mount.SLDASM | Final adjustable CAD baseline |
| 06 Full Exoskeleton Integration Context | OPEN - Full Exoskeleton Integration Context.SLDASM | Context for placement on the larger hip exoskeleton |

The adjustable stages include the compact QT Py electronics package as a smaller nested assembly. That nested assembly keeps its original filename and is stored with its supporting parts in Assembly Components.

## Planned comparison and validation

The final CAD iteration is complete, but the need for pelvis translation remains a testable design question. Planned evaluation should:

1. Define a repeatable mounting or anatomical reference used during participant fitting.
2. Fit the static and adjustable versions across a representative range of participants.
3. Measure variation in relative IMU position and initial sensor-frame alignment.
4. Verify that the adjustment remains locked during representative gait motion.
5. Confirm cable clearance, service access, and comfort throughout the fit range.
6. Compare setup time and operator repeatability.
7. Compare downstream gait features and cross-participant model performance with each mounting approach.
8. Retain the adjustable mechanism only if its measured benefit justifies the added complexity.

## Distributed-computing context

The local QT Py and IMU package is part of a distributed exoskeleton architecture. Placing computing and communication hardware near sensors and actuators reduces long cable runs and the complexity of routing a large centralized wiring bundle. The packaging work provides the physical mounting, protection, connector access, and strain management required to make that architecture practical.
