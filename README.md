# Repeatable IMU Placement and Distributed Electronics for a Hip-Knee Exoskeleton

**SolidWorks · Sensor placement · Mechanical design · Additive manufacturing · Mechatronics integration**

I designed an adjustable IMU mounting system and its supporting electronics packages for a hip-knee exoskeleton. The primary engineering goal is to place each IMU at a comparable position and initial sensor-frame orientation across people with different body geometries.

More repeatable placement should reduce setup-dependent variation in gait data, improve consistency in the data used to train control and estimation algorithms, and support better transfer of learned models from one participant to another. This is the design motivation; the magnitude of the algorithmic benefit remains an experimental question.

The supporting distributed-computing hardware places electronics closer to the sensing and actuation locations. Its practical system-level purpose is to reduce long cable runs and wiring-bundle complexity across the exoskeleton.

## Project at a glance

| | |
| --- | --- |
| **Primary objective** | Repeatable IMU position and initial orientation across participants |
| **Current mechanical focus** | Pelvis, thigh, and shin IMU mounts for a hip-knee exoskeleton |
| **Data objective** | Reduce placement-induced variation in gait measurements |
| **Algorithm objective** | Support more consistent training data and improved person-to-person model transfer |
| **Distributed-system objective** | Place computing near devices to reduce long cable runs and simplify routing |
| **Supporting hardware** | ICM-20948 IMU, Teensy, QT Py SAMD21, CAN Pal, and exoskeleton mounting hardware |
| **CAD tools** | SolidWorks assemblies and parts organized around one obvious entry assembly per design |
| **Status** | Two electronics packages are complete and fully validated; the final pelvis CAD iteration is complete; the adjustable thigh and shin subsystems remain in development |

## Why repeatable sensor placement matters

An IMU measures motion in its own coordinate frame. If that frame starts at a different orientation or at a substantially different relative position for each participant, the resulting gait signals can contain variation caused by setup rather than movement.

The adjustable mount is intended to:

- align the sensor at a comparable location using the exoskeleton and pelvis mounting structure as references;
- establish a repeatable initial sensor-frame orientation;
- keep the sensor rigidly fixed relative to the exoskeleton during gait;
- accommodate differences in participant geometry without improvising a new mounting location;
- make cross-participant datasets easier to compare.

The sensor does not remain globally pointed in one direction throughout gait—the exoskeleton moves. The design goal is a consistent starting alignment and a fixed relationship between the IMU and the structure carrying it.

## My contribution

- Developed adjustable pelvis, thigh, and shin mounting concepts, including a static pelvis reference and documented component-level design iterations.
- Added controlled translation along the pelvis mounting structure while maintaining sensor support and orientation.
- Preserved both static and adjustable configurations so the value of pelvis translation can be tested rather than assumed.
- Integrated the compact QT Py and IMU package into the adjustable-mount assemblies.
- Designed two lightweight electronics-packaging architectures for the distributed communication system.
- Addressed connector access, cable strain relief, status-light shielding for motion capture, printability, assembly, and service access.
- Reorganized the CAD so each design exposes one clearly labeled top-level assembly and keeps nested assemblies and parts in an adjacent component folder.

## System context

~~~mermaid
flowchart LR
    Fit["Participant-specific fitting"] --> Mount["Adjustable pelvis, thigh, and shin IMU mounts"]
    Mount --> Alignment["Comparable relative position and initial orientation"]
    Alignment --> Data["More consistent gait data"]
    Data --> Transfer["Improved cross-person model transfer — design goal"]

    IMU["IMU"] --> Local["Local controller / communication node"]
    Local --> Network["Distributed exoskeleton network"]
    Local --> Wiring["Shorter cable runs and simpler routing"]
    Package["Protective electronics package"] --> Local
~~~

## Primary project: pelvis IMU positioning

The pelvis subsystem retains a fixed reference design and a sequence of adjustable designs. The direction of translation is described as **along the pelvis mounting structure** because the final SolidWorks coordinate-frame convention has not been verified well enough to call it a global Y or Z axis.

| CAD stage | Purpose | Status |
| --- | --- | --- |
| **Static Version** | Fixed back-plate alternative to the adjustable final design | Alternative final configuration |
| **Iteration 1** | Introduces the sliding mount concept | Design iteration |
| **Iteration 2** | Refines the holder and adjustment hardware | Design iteration |
| **Iteration 3** | Further integrates the adjustment mechanism and system hardware | Design iteration |
| **Final Version** | Final adjustable pelvis-mount CAD | Final adjustable configuration |
| **Full Assembly** | Shows the pelvis package in the larger hip exoskeleton | System-level assembly |

Both the static and adjustable versions are intentionally preserved. Testing will determine whether translation at the pelvis materially improves placement repeatability enough to justify the added adjustment mechanism.

[Explore the pelvis IMU mounting system](Adjustable%20IMU%20Mounting%20for%20Hip-Knee%20Exoskeleton/Pelvis%20IMU%20Mounting%20System)

## Thigh IMU positioning — work in progress

The thigh subsystem uses a movable strap-routing attachment captured within an opening in the thigh cuff. The attachment can move up/down and side-to-side for fitting. The retention strap threads through it and then wraps around the thigh/cuff, while bolts entering from the opposite side bound vertical travel so the attachment cannot migrate beyond the intended adjustment region.

The mechanism is intended to combine participant-specific adjustment with a repeatable, mechanically bounded strap path. Retention, comfort, slip resistance, placement repeatability, and the resulting data benefit still require experimental validation.

[Explore the thigh IMU mounting system](Adjustable%20IMU%20Mounting%20for%20Hip-Knee%20Exoskeleton/Thigh%20IMU%20Mounting%20System)

## Shin IMU positioning — work in progress

The shin subsystem extends the same repeatable-placement strategy to the knee exoskeleton. Its current concept supports adjustment up or down along the shin and side-to-side around the mounting region, while the cuff, strap path, foam interface, and shank bar work together to resist movement during gait.

The large cylinder in the close-up CAD is a simplified human shin. The cuff is intended to be secured by a strap routed through the knee-exoskeleton attachment, and the foam is intended to increase friction and reduce slipping.

| CAD area | Purpose | Status |
| --- | --- | --- |
| **Zoomed-In Shin IMU Assembly** | Inspect the current sensor, cuff, foam, representative shin, and shank-bar interface | Work in progress |
| **Full Knee Exoskeleton Assembly** | Review integration in complete knee-exoskeleton context | Work in progress |
| **Shin Cuff Iterations 1–2** | Track development of the wearable cuff and foam-backed IMU package | Design iterations |
| **Shank Bar Iterations 1–4** | Track development of the supporting knee-exoskeleton bar | Design iterations |

[Explore the shin IMU mounting system](Adjustable%20IMU%20Mounting%20for%20Hip-Knee%20Exoskeleton/Shin%20IMU%20Mounting%20System)

## Supporting distributed-electronics packaging

The distributed architecture supports the sensor-placement work by locating controller and communication hardware near the devices it serves. The mechanical packages make those local nodes wearable, serviceable, and compatible with motion-capture testing.

| Package | Architecture | Status | Start here |
| --- | --- | --- | --- |
| **Original CAN communication package** | Teensy, IMU, and CAN interface | Complete and fully validated | [Final/OPEN THIS FIRST](Original%20CAN%20Communication%20Setup/CAD/Final/OPEN%20THIS%20FIRST%20-%20Final%20Validated%20Design) |
| **Compact CAN communication package** | Exactly 1 QT Py and 1 IMU | Complete and fully validated | [Final Version/OPEN THIS FIRST](Final%20CAN%20Communications%20Packaging/CAD/Final%20Version/OPEN%20THIS%20FIRST%20-%20Compact%20QT%20Py%20Package%20-%20Final) |

## Recruiter-friendly CAD navigation

Most design folders follow the same convention:

~~~text
Design or version/
├── README.md
└── OPEN THIS FIRST - Clear Design Name/
    ├── OPEN - Clear Top-Level Assembly Name.SLDASM
    └── Assembly Components/
        ├── supporting parts
        └── nested assemblies, when present
~~~

Open the assembly beginning with **OPEN -**. Supporting part filenames and nested-assembly filenames are left unchanged to protect their identity across design iterations. Because the files were reorganized for GitHub review, SolidWorks may request a one-time reference relink; select the matching file inside that design's own **Assembly Components** folder.

The full knee-exoskeleton shin view is the deliberate exception requested for that large context assembly: its main assembly remains visible and its other source files are consolidated into **Assembly Components.zip**. Original source archives are otherwise not duplicated. Each supplied archive is integrity-checked and extracted or repackaged into its corresponding self-contained CAD stage.

## Validation status

### Completed electronics packages

The original Teensy-based package and compact QT Py package are complete and fully validated for their intended exoskeleton configurations. Their checks covered:

- board and connector fit;
- cable routing and strain relief;
- component and lid clearances;
- status-light shielding for infrared motion capture;
- deliberate debug access;
- printability, assembly, service access, and repeated use.

### Pelvis positioning subsystem

The final adjustable CAD iteration is complete. Comparative testing remains for the pelvis-specific adjustment question:

- measure placement repeatability for the static and adjustable mounts across participants;
- compare initial sensor-frame alignment;
- verify that the selected adjustment does not slip during gait;
- determine whether the added translation meaningfully reduces setup variation;
- evaluate whether the resulting data improves cross-participant algorithm transfer.

### Thigh and shin positioning subsystems

The current thigh and shin CAD concepts remain in development. Planned checks include:

- verify usable adjustment ranges across the intended participant population;
- measure repeated-fit position and initial-orientation consistency;
- test strap retention, bounded travel, and resistance to slip during gait;
- confirm participant comfort and exoskeleton clearance;
- evaluate whether improved placement consistency reduces setup-driven signal variation.

## Repository map

- [Adjustable IMU Mounting for Hip-Knee Exoskeleton](Adjustable%20IMU%20Mounting%20for%20Hip-Knee%20Exoskeleton) — primary sensor-placement project and pelvis CAD history.
- [Thigh IMU Mounting System](Adjustable%20IMU%20Mounting%20for%20Hip-Knee%20Exoskeleton/Thigh%20IMU%20Mounting%20System) — in-progress strap-adjustable thigh-cuff IMU positioning with bounded travel.
- [Shin IMU Mounting System](Adjustable%20IMU%20Mounting%20for%20Hip-Knee%20Exoskeleton/Shin%20IMU%20Mounting%20System) — in-progress adjustable shin sensor placement, full knee-exoskeleton context, and component iterations.
- [Final CAN Communications Packaging](Final%20CAN%20Communications%20Packaging) — compact, fully validated one-QT-Py/one-IMU package.
- [Original CAN Communication Setup](Original%20CAN%20Communication%20Setup) — original, fully validated Teensy-based package and its design history.

<details>
<summary>Original source-folder mapping</summary>

The original Teensy-package Drive folders used overlapping design numbers, so the repository folders are normalized chronologically while supporting SolidWorks filenames remain unchanged:

| Repository folder | Original Drive folder |
| --- | --- |
| Design 1 | Design 1 |
| Design 2 | Design 1, Part 2 |
| Design 3 | Design 2 |
| Design 4 | Design 3 |
| Final | FINAL DESIGN |
| Experimental – Lid Tests | Lid Test 1 |

The pelvis source archives map to Static Version, Iterations 1–3, Final Version (source ASM #5), and Full Assembly.

</details>
