# Nanometa TCSPC Control Software

![LabVIEW Version](https://img.shields.io/badge/LabVIEW-2023_Q3+-002D62.svg)
![MATLAB](https://img.shields.io/badge/MATLAB-R2023b+-ED8B00.svg?style=flat&logo=mathworks&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-64--bit-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

📄 **[Read the Full 50-Page System Description/User Manual](./Docs/TCSPC_Manual.pdf)**

## Overview
This LabVIEW project manages the hardware and data acquisition for the group's primary **Time-Correlated Single-Photon Counting (TCSPC)** and confocal microscopy setup. The system coordinates sub-micron positioning (PI Piezo), high-speed laser scanning, timing electronics (Becker & Hickl), and single-photon detection to automate quantum emitter characterization. 

All data is saved in metadata-rich formats designed to interface directly with the **[TCSPC_analysis](https://github.com/brandontriplett/TCSPC_analysis)** module for automated plotting and reporting.

### Core Capabilities
* **Timing:** Lifetime ($\tau$) and $g^{(2)}$ photon correlation measurements.
* **Mapping:** High-speed confocal scanning and spatial mapping.
* **Spectroscopy:** Visible and near-IR spectral analysis.
* **Spin Dynamics:** Coherent control protocols, including **ODMR**, $T_1$, $T_2$, and Rabi oscillations.
* **All of the above, highly-automated.**

### Short explanation of my contribution to this project — Brandon Triplett
During the early years of my PhD, this setup was largely sitting idle. The students who had started the project had graduated, and because it lacked documentation, much of the custom code and hardware had become difficult for the group to use effectively. In 2024, while other group members began to build new setup on another table, I decided to ownership of this setup to revitalize and expand its capabilities.

I rebuilt most of the LabVIEW codebase from the ground up, upgraded legacy hardware, migrated everything from 32-bit to 64-bit (future-proofing), restructured the optical path, and most of all made it very user-friendly and highly automated. I documented a lot of this in my manual (which is linked above). My goal was maximizing data collection efficiency through automation, and now, almost every type of measurement can be taken, saved (with all necessary metadata needed for processing), and analyzed with a few mouse clicks. The setup is now the primary workhorse for the group.

<div align="center">
  <img src="https://github.com/user-attachments/assets/21c0a00f-1d0a-440d-8261-b892cc2381be" width="500">
  <br>
  <p align="center">
    <em>A student printed some of the interesting results of an overnight autoscan report and used it to re-locate and further analyze the exact same emitters the next day</em>
  </p>
</div>

## Repository Structure
* **`TCSPC_Control.lvproj`**: Main LabVIEW project environment.
* **`Source/`**: SubVIs.
* **`Docs/`**: Documents. Most everything needed is included in the 50-page technical manual.

## Requirements & Environment
* **Software:** LabVIEW 2023 Q3 (64-bit), MATLAB, Python 3.9+.
* **Drivers:** NI-DAQmx, NI-VISA, B&H SPC, PI GCS, Thorlabs Kinesis, Ocean Optics OmniDriver.

## Credits
Built on an initial foundation by **Prof. Simeon Bogdanov** and **Dr. Mikhail Shalaginov**. 

**Current Maintainer:** Brandon Triplett (Purdue University)
