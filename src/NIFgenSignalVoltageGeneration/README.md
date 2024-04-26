## NI-FGEN Signal Voltage Generation Measurement

This measurement generates a Standard Function waveform that is either sine or square at a set 50% duty cycle using NI-FGEN.

### Features

- Uses the NI-FGEN LabVIEW API.
- Pin-aware, supporting one session and one pin.
  - Uses the same inputs for all selected pin/site combinations.
- An example pin map is saved under the measurement source for reference.
- Includes a TestStand sequence found under the test directory showing how to configure the pin map, register instrument sessions with the session management service, and run a measurement.
  - For the sake of simplicity, the TestStand sequence handles pin map and session registration and unregistration in the `Setup` and `Cleanup` sections of the main sequence. For batch process model use cases, these steps should be moved to the `ProcessSetup` and `ProcessCleanup` callbacks. See [Using Driver Sessions in TestStand](https://www.ni.com/r/6nb5je) for more information.
- Uses the NI gRPC Device Server to allow sharing instrument sessions with other measurement services when running measurements from TestStand.

### Run a Measurement

1. Create a pin map if not yet already done so.
2. Select the appropriate pin from the Pin Name drop down.
3. Provide the desired input values.
4. Run the measurement.
5. The measurement will display the standard function generated on the graph. A more comprehensive view of the generated waveform can also be seen using an NI SCOPE device to read back the generated waveform.

### Required Software or Drivers 

- NI-FGEN 2023 Q4 or later
- For more software dependencies, please refer to the main repo [Readme](../../README.md) for more details.

### Required Hardware

This example requires an NI Waveform Generator that is supported by NI-FGEN (e.g. PXIe-5441).