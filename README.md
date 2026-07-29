# Exoskeleton IMU and CAN Electronics Packaging

**SolidWorks · Mechanical design · Additive manufacturing · Mechatronics integration**

I designed and iterated a lightweight, 3D-printable electronics enclosure for an exoskeleton's distributed-control system. The package brings together an IMU, a Teensy microcontroller, and CAN communication hardware while addressing motion-capture interference, cable strain, service access, and multiple exoskeleton mounting interfaces.

## Project at a glance

| | |
| --- | --- |
| **My focus** | Mechanical packaging, CAD iteration, and design-for-printing |
| **Hardware** | Adafruit ICM-20948 IMU, Teensy microcontroller, and 5708 CAN Pal |
| **Key constraints** | Low mass, fast printing, IR light shielding, connector protection, and simple service access |
| **Mechanical interfaces** | V2 and V2.5 exoskeleton mounting patterns |
| **Status** | Complete and fully validated for its intended exoskeleton use |
| **Deliverables** | Five CAD generations, lid prototypes, final SolidWorks assembly, requirements, and completed validation record |

## My contribution

- Translated an advisor brief and electrical-system needs into mechanical packaging requirements.
- Developed the enclosure through multiple SolidWorks iterations rather than treating the first concept as a finished design.
- Designed around board support, connector access, cable routing, minimum wall thickness, and component clearances.
- Addressed how indicator LEDs could be hidden from infrared motion-capture cameras while remaining accessible during debugging.
- Addressed strain relief so cable-yank loads transfer into the housing instead of board-mounted connectors.
- Defined and completed the physical validation needed before releasing the enclosure for use on the exoskeleton.

The work was collaborative: another team member focused on inter-device communications for distributed computing, while my focus was the physical packaging and hardware integration around that system.

## System context

```mermaid
flowchart LR
    Motion["Limb motion"] --> IMU
    subgraph Package["3D-printed electronics package"]
        IMU["ICM-20948 IMU"] --> MCU["Teensy microcontroller"]
        MCU --> CAN["CAN interface"]
    end
    CAN --> Network["Distributed exoskeleton network"]
```

## Engineering challenge

| Requirement | Why it matters | Validated response |
| --- | --- | --- |
| Block status lights | Infrared cameras may detect exposed indicators during motion capture | Opaque enclosure with deliberate debug-light access |
| Protect connectors | A yanked cable can damage a board-mounted connector | Housing-level cable capture and strain-relief features |
| Preserve service access | Hardware must be connected and inspected without removing the full system | Accessible cable exits and serviceable lid concepts |
| Support two exoskeleton versions | V2 and V2.5 use different IMU mounting interfaces | Common enclosure with mounting variants or interchangeable plates |
| Print quickly at low mass | The package is worn on a moving exoskeleton | Thin but controlled walls, compact geometry, and support-conscious design |
| Constrain electronics safely | Boards cannot move, short, or carry enclosure loads through components | Standoffs, positive board capture, and component clearance checks |

## Design evolution

| Iteration | Focus |
| --- | --- |
| **Design 1** | Baseline housing, hinged-lid exploration, and electronics packaging assembly |
| **Design 2** | Revised housing geometry and updated assembly packaging |
| **Design 3** | Further cover and lid refinement |
| **Design 4** | CAN Pal integration and a more complete communication-hardware stack |
| **Final** | Consolidated cover, snapping lid, CAN interface, IMU, and microcontroller assembly |
| **Lid tests** | Focused snap-fit and service-access experiments |

This progression preserves the design history and shows how the enclosure developed as integration constraints became clearer.

## Completion and validation

**Status: complete and fully validated.** The final package passed the validation required for its intended exoskeleton configuration. Validation covered:

- V2 and V2.5 mounting compatibility;
- board, connector, cable, and service-access fit;
- cable handling and strain relief;
- component and lid clearances;
- status-light shielding for motion capture and deliberate debug access;
- printability and repeated-use durability.

The repository preserves the validated final design together with the earlier CAD iterations that led to it.

## Explore the work

- Start with the [`Final` CAD package](Original%20CAN%20Communication%20Setup/CAD/Final), which includes the original source ZIP and extracted SolidWorks files.
- Read the [`IMU Packaging Notes and Specifications`](Original%20CAN%20Communication%20Setup/Notes%20and%20Specifications/IMU%20Packaging%20Notes%20and%20Specifications.md) for historical requirements, dimensions, design decisions, and the completed validation checklist.
- Review the [`CAD design history`](Original%20CAN%20Communication%20Setup/CAD) to see the earlier iterations and lid tests.

<details>
<summary>Source-folder mapping</summary>

The original Drive folders used overlapping design numbers, so the repository folders are normalized chronologically while the SolidWorks filenames remain unchanged:

| Repository folder | Original Drive folder |
| --- | --- |
| Design 1 | Design 1 |
| Design 2 | Design 1, Part 2 |
| Design 3 | Design 2 |
| Design 4 | Design 3 |
| Final | FINAL DESIGN |
| Lid Tests | Lid Test 1 |

The initial archive is limited to material from the original IMU-packaging project folder and its child folders.

</details>
