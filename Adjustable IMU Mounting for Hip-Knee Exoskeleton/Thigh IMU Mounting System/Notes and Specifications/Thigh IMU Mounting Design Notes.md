# Thigh IMU Mounting Design Notes and Specifications

## Project status

This thigh subsystem is **still in development**. The CAD documents the current strap-adjustable mounting concept; it should not be presented as a fully validated final design.

## Functional objective

Provide an adjustable thigh-cuff attachment that supports repeatable IMU placement across participants with different thigh geometries. Adjustment is described relative to the cuff rather than assigned to a global SolidWorks axis:

1. **Vertical adjustment:** move the strap-routing attachment up or down within the thigh-cuff opening.
2. **Side-to-side adjustment:** reposition the attachment laterally within the available opening.
3. **Bounded travel:** use the opposite-side cuff bolts to keep vertical movement within the intended region.
4. **Wearable retention:** route the strap through the movable attachment and around the thigh/cuff to secure the system.

The target outcome is reduced setup-dependent variation in gait signals. More consistent sensor placement may support more comparable cross-participant data and better model transfer, but that effect still requires testing.

## Mechanism sequence

| Step | Mechanical role |
| --- | --- |
| Position | Slide the strap-routing attachment vertically and side-to-side within the cuff opening. |
| Bound | The bolts entering the cuff from the opposite side define the permitted vertical travel and prevent the attachment from migrating beyond that range. |
| Thread | Pass the retention strap through the movable attachment. |
| Wrap | Route the strap around the participant's thigh and the cuff. |
| Tension | Tighten the strap to secure the cuff and IMU relative to the wearer. |

## Design requirements

- Provide controlled vertical and side-to-side IMU positioning.
- Preserve a consistent initial IMU orientation after fitting.
- Keep the movable attachment captured within the cuff opening.
- Bound vertical travel with the cuff-bolt geometry.
- Maintain a clear, practical strap path through the attachment and around the thigh/cuff.
- Resist sliding, rotation, and loosening during representative gait.
- Avoid interference between the strap, bolts, cuff, IMU, and exoskeleton motion.
- Support repeatable donning, adjustment, tightening, and removal.
- Remain lightweight, printable, and serviceable.

## Planned validation

- Measure the usable vertical and side-to-side adjustment ranges.
- Fit participants spanning the intended thigh-size range.
- Confirm that the bolts consistently stop vertical over-travel.
- Apply strap pull loads and verify that the attachment remains captured.
- Test for vertical slip, lateral shift, and rotation during gait.
- Check comfort, pressure distribution, and strap routing during prolonged wear.
- Measure repeatability of relative IMU position and initial orientation after repeated fitting.
- Verify clearance through the hip-knee exoskeleton's expected range of motion.
- Compare gait signals across repeated fittings and participants.

## CAD source and handling

The supplied archive contains six files: one top-level assembly and five parts. The assembly was renamed to **OPEN - Strap-Adjustable Thigh IMU Cuff.SLDASM** for recruiter navigation; its bytes are otherwise unchanged. Supporting filenames remain unchanged in **Assembly Components**.

If SolidWorks requests a reference relink, select only the matching parts from this design's own **Assembly Components** folder.
