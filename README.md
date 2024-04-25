# PCB Assembly Test Measurements

## Overview
This is a collection of Measurement Services for common PCBA Functional Test using NI Modular Instruments (DMM, FGEN, Scope, SMU).

## Key Features
- FGEN
    - Signal Voltage Generation
- SCOPE
    - Digital Measurement
    - Time Domain Measurement
    - Frequency Domain Measurement
- SMU
    - Constant Voltage Power Supply Measurement
- DMM
    - DC Voltage/Current RMS Measurement

## Getting Started

### Software Dependencies
- [InstrumentStudio 2024 Q1 or later](https://www.ni.com/r/lsadgm)
- [MeasurementLink 2024 Q1 or later](TBD)
- [LabVIEW 2024 Q1 or later](https://www.ni.com/r/p0pvmk)
- [TestStand 2023 Q4 or later](https://www.ni.com/r/o16yk2)
- [MeasurementLink Support for LabVIEW v2.0.0.1 or later](TBD) from VIPM
- NI Modular Instrument Drivers
  - [NI-SCOPE 2024 Q1 or later](TBD)
  - [NI-DMM 2023 Q4 or later](https://www.ni.com/r/ryflpz)
  - [NI-DCPower 2024 Q1 or later](TBD)
  - [NI-FGEN 2023 Q4 or later](https://www.ni.com/r/fsxbkw)

### Hardware Setup
Configure the hardware required by NI MAX before running measurements.
- For the hardware model, please refer to the individual readmes of the specific measurements.
- Simulated hardware devices are supported. To simulate a hardware device in NI MAX, please refer to [Create Simulated NI-DAQmx Devices in NI MAX](https://www.ni.com/r/2pwee1).

### Running Measurements
- For the MeasurementLink software to recognize avaliable measurements, the [Discovery Service](https://www.ni.com/r/ap6b6a) needs to be running and one of the following needs to be true:
  - The build outcome of measurements are saved in the 'C:\ProgramData\National Instruments\MeasurementLink\Services' directory to be detected automatically. It also can be realized by downloading the nipkg, which will install the measurements to the above 'Service' directory.
  - The measurements are manually running via the 'Run Service.vi' of the LabVIEW project (.lvproj).
- InstrumentStudio:
  - Open an existing project or create a new manual layout.
  - Available measurements should be populated and visible.
  - At least one measurement or instrument needs to be selected for the *Large Panel*.
  - Once open, the measurement will need a pinmap matching the instrument names created in NI MAX. For additional help on creating a new pin map, see [here](https://www.ni.com/r/mf8ss9).
  - Click `Run` to run the measurement.
- TestStand:
  - Create a TestStand sequence.
    - With MeasurementLink installed, there're custom measurement steps to register the pin map and configure the measurement.
    - For Teststand to create and own the management of the hardware sessions, additonal Setup steps to initialize and register sessions and Cleanup steps to unregister and close sessions are needed. See additional help from [here](https://www.ni.com/r/6nb5je) to use the driver sessions.
  - Run the sequence. The measurement runs as a step in the sequence.

### Testing
Functions of measurements are tested and validated. Testing materials are in the [test](/test) folder.
- The folder includes TestStand sequences and InstrumentStudio projects used for the manual testing.
- The pin map file for each measurement can be found in the corresponding subfolders within the [src](/src) directory.

### Build
See the [Releases](https://github.com/NI-MeasurementLink-Plug-Ins/pcba-fct/releases) page of this repo to download the latest nipkg of the entire collection of measurements. Installing the nipkg will install each measurement service into the 'C:\ProgramData\National Instruments\MeasurementLink\Services' directory so the measurements will be ready-to-use in both InstrumentStudio and TestStand.
- This package does not include any driver or software dependencies (e.g. LabVIEW). Those must be installed first separately.
- The [package](/package) folder of this repo includes the NI Package Builder (.pbs) solution that was used to build the nipkg locally.
- If rebuilding the nipkg, it is recommended to rebuild the exe build spec in each measurement's `.lvproj` with the destination directory set to an short, local path. Then, the .pbs solution can be updated to pull local build files from that path before rebuilding the nipkg. 

## Reference
- [Measurementlink LabVIEW Examples](https://github.com/ni/measurementlink-labview/tree/main/Source/Example%20Measurements)
- [Measurementlink Overview](https://www.ni.com/r/ro82un)
- [Measurement Development and Usage Best Practices](https://www.ni.com/r/abohlo)