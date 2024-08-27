# VNA Control 5 SDK Example Programs

There are three interfaces for programmatically controlling and retrieving data from the LA Techniques VNA instrument:

1. API
2. SCPI
3. Binary data broadcasts (data retrieve only)

This repository contains example programs and links to documentation for each interface. The examples are made available under the MIT License (see LICENSE.txt for terms).

## Requirements and obtaining the SDK

The VNA Control 5 SDK requires a LA Techniques VNA instrument that is compatible with the VNA Control 5 software. To check if your instrument is compatible, download and run the VNA Control 5 software. You will have the opportunity to upgrade your instrument using the VNA Control 5 software if it is not currently compatible. If your LA Techniques VNA instrument is not compatible with the VNA Control 5 software, you can use the SDK in demonstration mode for evaluation purposes.

To remote control the instrument via SCPI, the VNA Control 5 software must be installed.

> [!IMPORTANT]  
> [CLICK HERE](https://www.aairobotics.com//la_builds/current/app.zip) to download the VNA Control 5 software (required to control the instrument via SCPI).

To use the API, installing the VNA Control 5 software is optional. An SDK is available that allows the instrument to be programmatically controlled without the VNA Control 5 software being installed.

> [!IMPORTANT]  
> [CLICK HERE](https://www.aairobotics.com/la_builds/current/sdk.zip) to download the SDK (language bindings, headers, libraries, driver-only installer, etc.).

Further requirements specific to programming languages can be found within the programming guides for those languages.




## API

The API allows the LA Techniques VNA instrument to be controlled directly, without running the VNA Control 5 software. It is the most programmer-friendly way of controlling the LA Techniques VNA instrument, with useful abstractions and clean syntax. The API is appropriate for system integrators who wish to distribute their own systems that encapsulate the LA Techniques VNA instrument, without needing to also deploy the VNA Control 5 software. Using the LA Techniques VNA instrument via the API will maximise performance and minimise energy use on the host controller, so is also the most appropriate option for use in embedded systems. It is not possible to control the instrument via the API and the VNA Control 5 software simultaneously.

### Documentation

[C++ Programmer's Guide](https://aairobotics.com//la_builds/current/docs/VNA_Control_5_Programming_Guide_Cpp.pdf)

[Python Programmer's Guide](https://aairobotics.com//la_builds/current/docs/VNA_Control_5_Programming_Guide_Python.pdf)

### Examples

1. Simple frequency sweep using factory calibration and retrieve data |  [C++](/api/cpp/01_simple_frequency_sweep) | [Python](/api/python/01_simple_frequency_sweep) |
2. Load user calibration and perform frequency sweep | [C++](/api/cpp/02_load_user_cal_and_print_logmagarg_data) | [Python](/api/python/02_load_user_cal_and_print_logmagarg_data) |
3. Time domain transform | [C++](/api/cpp/03_time_domain_transform) | [Python](/api/python/03_time_domain_transform) |
4. Perform a logarithmic frequency sweep | [C++](/api/cpp/04_log_frequency_sweep) | [Python](/api/python/04_log_frequency_sweep) |
5. Measure after trigger event | [C++](/api/cpp/05_trigger) | [Python](/api/python/05_trigger) |


## SCPI

SCPI allows the LA Techniques VNA instrument to be controlled via the VNA Control 5 software. The VNA Control 5 software must be running in order to control the LA Techniques VNA instrument via SCPI. SCPI control is most useful in applications where the instrument is being controlled together by both the VNA Control 5 software and by an external user application. The syntax used for SCPI control will be familiar to users of other test and measurement equipment. SCPI control supports some more complex features of the VNA Control 5 software that would not be appropriate in the API: for example, importing touchstone data to memory channels. The most simple example of an application where SCPI control is appropriate is: VNA Control 5 can be used to load a calibration and conﬁgure the measurement, and then the external user application can perform the measurement and retrieve data. SCPI commands can also be typed by the user directly into a console, in order to control the application via interactive scripting.

### Documentation

[SCPI Programmer's Guide](https://aairobotics.com//la_builds/current/docs/VNA_Control_5_Programming_Guide_SCPI.pdf)

### Examples

1. Perform a simple frequency sweep using factory calibration and retrieve all sweep data | [Python](/scpi/python/01_simple_frequency_sweep) | [MATLAB](/scpi/matlab/01_simple_frequency_sweep) | [LabVIEW](/scpi/LabVIEW/01_simple_frequency_sweep) |
2. Load user calibration, perform sweep and export all sweep data to a Touchstone file | [Python](/scpi/python/02_load_cal_and_export_touchstone) | [MATLAB](/scpi/matlab/02_load_cal_and_export_touchstone)  | [LabVIEW](/scpi/LabVIEW/02_load_cal_and_export_touchstone) |


## Binary Data Broadcasts

Binary data broadcasts provide a simple way for other applications to extract data from the VNA Control 5 software in real-time. No programming is required to conﬁgure these; data is broadcast using a binary protocol when a measurement is started via the VNA Control 5 software. These are read-only, and they do not provide a programmatic way to conﬁgure measurements (which must be done either via the user interface of the VNA Control 5 software or via SCPI). Refer to the VNA Control 5 User Manual for details on how to retrieve data using the binary data broadcasts.
