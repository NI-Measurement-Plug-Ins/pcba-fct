## NI-DMM DC RMS Measurement 

This example performs DC RMS measurement using NI DMM.


Select the waveform function and range.
Specify the sample rate and number of samples to acquire.
  The measured value will be displayed in the DC Value and RMS Value indicators.
  The Boolean indicator will indicate if the measured value is out of range.
  The measured waveform will display on the Voltage Waveform graph.


### Features

- Uses the NI-DMM LabVIEW API.
- Pin-aware, supporting one session and one pin.
  - Uses the same selected measurement function and range for all selected pin/site combinations.
- Includes InstrumentStudio project files.
- Includes a TestStand sequence showing how to configure the pin map, register.
  instrument sessions with the session management service, and run a measurement.
  - For the sake of simplicity, the TestStand sequence handles pin map and session registration and unregistration in the `Setup` and `Cleanup` sections of the main sequence. For **Test UUTs** and batch process model use cases, these steps should be moved to the `ProcessSetup` and `ProcessCleanup` callbacks.
- Uses the NI gRPC Device Server to allow sharing instrument sessions with other measurement services when running measurements from TestStand.

### Required Driver Software

- NI-DMM 2023 Q1 or later

### Required Software

- InstrumentStudio 2024 Q1 or later
- MeasurementLink 2024 Q1 or later
- LabVIEW 2024 Q1 or later
- TestStand 2023 Q4 or later

### Required Hardware

This example requires an NI DMM that is supported by NI-DMM (e.g. PXIe-4081).