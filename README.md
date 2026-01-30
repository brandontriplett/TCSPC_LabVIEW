This is our LabVIEW program for controlling the hardware and data acquisition of our primary time-correlated single-photon counting experiemntal setup in the nanometa group at Purdue University. This setup is used for the majority of our groups room-temperature quantum experiments. The labVIEW code is largely based on the work of Professor Simeon Bogdanov, who was a postdoc in our group before I joined, but I have since taken it over including a total rebuild and creating many new features. 


# Nanometa TCSPC Control Software

**Primary Control Interface for Room-Temperature Quantum Experiments** *Nanometa Group, Purdue University*

## Overview
This LabVIEW project controls the hardware and data acquisition for the group's primary Time-Correlated Single-Photon Counting (TCSPC) experimental setup. It integrates control for laser scanning, sample positioning, and single-photon detection to automate data collection for quantum emitter characterization.

This software is the primary setup for the majority of the group's room-temperature quantum experiments, including:
* Lifetime and g2 measurements
* Confocal scanning and mapping
* Spectral analysis
* Coherent control of spin measurements (ODMR, etc.)

## History & Credits
The core architecture of this codebase was originally developed by **Prof. Simeon Bogdanov** (University of Illinois Urbana-Champaign) during his tenure as a Postdoctoral Researcher in the Nanometa group.

Since 2023, the codebase has been **completely rebuilt and maintained by Brandon Triplett**. This modernization effort included:
* A complete refactoring of the file structure and dependency management.
* Integration of Git version control.
* Restructuring of the data logging for .

## System Requirements
To run this software, the following must be installed on the control PC:

### Software Prerequisites
* **LabVIEW 2023 Q3** (or compatible newer version)
* **NI-DAQmx** (Driver for NI USB cards)
* **NI-VISA** (General instrument communication)

### Hardware Drivers (Critical)
* **Thorlabs Kinesis/APT Software:** For motor controls.
* **Becker & Hickl SPC Drivers:** For the TCSPC card.
* **PI E-712 Piezo Stage Drivers:** For the scanning stage.

> **Note:** Vendor-specific driver VIs are included in the `Source/Drivers/` directory of this repository to ensure version stability.

## Project Structure
* `TCSPC_Control.lvproj` - The entry point for the software.
* `Source/` - Contains all source code and subVIs.
    * `Main.vi` - Top-level user interface.
    * `subVIs/` - Analysis logic, functional blocks, and helper VIs.
    * `Drivers/` - Local copies of third-party instrument drivers (Thorlabs, BH, etc.).
* `Docs/` - Hardware manuals, wiring diagrams, and SOPs.

## Contact
**Maintainer:** Brandon Triplett  
**Email:** brandont2010@gmail.com  
**Group:** Purdue Nanometa Group
