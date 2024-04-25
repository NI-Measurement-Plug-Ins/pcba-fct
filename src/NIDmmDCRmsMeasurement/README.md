## NI-DMM DC RMS Measurement 

This measurement reads a DC/AC signal and analyzes its characteristics using NI DMM.

### Features

- Uses the NI-DMM LabVIEW API.
- Pin-aware, supporting one session and one pin.
  - Uses the same selected measurement function and range for all selected pin/site combinations.
  - An example pin map file is included for this measurement. However, you'll need to setup your own pin map file according to your own system.
- Includes InstrumentStudio project files.
- Includes a TestStand sequence showing how to configure the pin map, register instrument sessions with the session management service, and run a measurement.
  - For the sake of simplicity, the TestStand sequence handles pin map and session registration and unregistration in the `Setup` and `Cleanup` sections of the main sequence. For **Sequential** and **Batch** process model use cases, these steps should be moved to the `ProcessSetup` and `ProcessCleanup` callbacks, See [Using Driver Sessions in TestStand](https://www.ni.com/r/6nb5je) for more information.
- Uses the NI gRPC Device Server to allow sharing instrument sessions with other measurement services when running measurements from TestStand.

### Run a Measurement

In order to use a measurement, you will need to start the measurement service and open the measurement plugin in InstrumentStudio at first, refer to the main repo [Readme](https://github.com/NI-MeasurementLink-Plug-Ins/pcba-fct/blob/main/README.md) for more details.
- Select the expected Pin in your system.
- Setup the measurement function, range.
- Setup the measurement timing settings.
- Click the `Run` button. The measured value will be displayed in the measurement indicators and waveform.

### Required Software or Drivers 

- NI-DMM 2023 Q4 or later
- For more software dependencies, please refer to the main repo [Readme](https://github.com/NI-MeasurementLink-Plug-Ins/pcba-fct/blob/main/README.md) for more details.

### Required Hardware

This measurement requires an NI DMM that is supported by NI-DMM(e.g. PXIe-4081).