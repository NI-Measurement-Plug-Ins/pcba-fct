The pcba-measurements.pbs is the NI Package Builder solution file used to build the nipkg found in the [Releases](https://github.com/NI-MeasurementLink-Plug-Ins/pcba-fct/releases) of this repo.

# Getting Started
To rebuild the nipkg using this .pbs:
1. Right click the exe build spec in each measurement .lvproj to open its Properties, and set the destination directory in each measurement's exe build spec to a folder with the measurement's name at short, local path.
2. Rebuild the exe for each measurement.
3. Open the .pbs solution and under the `Inputs` section, select `Add Folder` and add the measurement folder with the built files that should've appeared in the path set in step 1.
4. Repeat for each measurement.
5. Click and drag each measurement folder from the `Inputs` section onto the `Services` folder in the Destination Directory section of the .pbs.
6. Change any of the package properties as desired.
7. The fourth button under the Packages section in the .pbs or `ctrl+F6` is used to build the package.


