## NI-SCOPE Digital Measurement 

This example performs measurement for digital signals using NI SCOPE.


### Features

- Uses the NI-SCOPE LabVIEW API.
- Pin-aware, supporting one session and one pin.
  - Uses the same selected measurement function and range for all selected pin/site combinations.
- Includes InstrumentStudio project files.
- Includes a TestStand sequence showing how to configure the pin map, register instrument sessions with the session management service, and run a measurement.
  - For the sake of simplicity, the TestStand sequence handles pin map and session registration and unregistration in the `Setup` and `Cleanup` sections of the main sequence. For **Sequential** and **Batch** process model use cases, these steps should be moved to the `ProcessSetup` and `ProcessCleanup` callbacks.
- Uses the NI gRPC Device Server to allow sharing instrument sessions with other measurement services when running measurements from TestStand.

### Required Driver Software

- NI-SCOPE 2024 Q1 or later

### Required Software

- InstrumentStudio 2024 Q1 or later
- MeasurementLink 2024 Q1 or later
- LabVIEW 2024 Q1 or later
- TestStand 2023 Q4 or later

### Required Hardware

This example requires an NI SCOPE that is supported by NI-SCOPE (e.g. PXIe-5122).