# Original CAN Communication Setup

This directory documents the hardware-packaging work that supports the exoskeleton's distributed inter-device communication setup. Placing controller and communication hardware near the devices it serves reduces long cable runs and simplifies wiring across the exoskeleton.

The electronics enclosure work has two related goals:

1. Package the IMU, microcontroller, and CAN communication hardware in a lightweight, serviceable enclosure.
2. Provide a bolt-on motor-controller housing if the final motor architecture benefits from a separate processor enclosure.

See [`Notes and Specifications/IMU Packaging Notes and Specifications.md`](Notes%20and%20Specifications/IMU%20Packaging%20Notes%20and%20Specifications.md) for the source requirements, engineering rationale, and completed validation criteria behind the final design.

For CAD review, start with the [CAD design-history guide](CAD). Every design exposes one clearly labeled top-level assembly inside an **OPEN THIS FIRST** folder.
