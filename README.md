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
The core of this codebase was originally developed by **Prof. Simeon Bogdanov** (University of Illinois Urbana-Champaign) during his tenure as a Postdoctoral Researcher in the Nanometa group.

**Since 2023, the system has been completely re-architected and maintained by Brandon Triplett.**
This effort transformed the legacy codebase into a reliable, 64-bit automated platform. Major contributions include:

### System Architecture & Core Logic
* **Total Codebase Rebuild:** Refactored the entire file structure and dependency management system for modularity and stability.
* **64-bit Migration:** Ported all legacy code and drivers to 64-bit architecture to leverage modern memory addressing and processing power.
* **Version Control:** Integrated Git/GitHub for full history tracking and branching.
* **DAQ Optimization:** Rewrote the data acquisition logic to improve timing precision and throughput.

### Experimental Capabilities
* **Automation:** Implemented fully automated measurement sequences and standardized, metadata-rich file saving protocols.
* **Coherent Control:** Added suites for coherent spin control measurements (e.g., ODMR, Rabi oscillations).
* **Hardware Integration:** Developed drivers and control logic for a wide array of new instrumentation, including:
    * Motorized mirrors and optical shutters
    * Large-area scanning stages
    * Multiple new laser sources and optimized delay lines
    * Programmable attenuators

### Infrastructure & Documentation
* **Hardware Overhaul:** Mapped and completely redid the physical wiring and cable management of the setup to match the new software architecture.
* **Documentation:** Created comprehensive wiring diagrams and user manuals to ensure reproducibility and ease of training for new lab members.

## System Requirements
To run this software, the following must be installed on the control PC:

### Software Prerequisites
* **LabVIEW 2023 Q3** (or newer version)
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
