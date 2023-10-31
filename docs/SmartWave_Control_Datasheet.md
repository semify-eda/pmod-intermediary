# SmartWave-Control Datasheet

## Overview

SmartWave, by semify GmbH, is a cutting-edge hardware tool designed for professional testing. 
It facilitates communication with a multitude of devices, including ADC, DAC, and Sensors, through industry-standard interfaces like SPI, I2C, and UART.
The device boasts a robust design, combined with flexible configuration options. Notable features include a range of standard interfaces, configurable IO voltage between 1.8 or 5.0 Volts, and a display that provides pin assignments and status information. 

Additionally, SmartWave is Pmod™ compatible, allowing direct connection with DIGILENT Pmod™ based extension boards. Its advanced FPGA platform ensures unparalleled performance and adaptability, making it an essential companion to any oscilloscope.

## Block diagram

The following drawing shows the block diagram of the SmartWave-Control hardware. 

![SmartWave-Control Block Diagram](SmartWave_Blockdiagram.svg?raw=true "SmartWave-Control Block Diagram")


## Electrical parameter

### IOs

There are 16 bidirectinal pins with the following parameter.

| *Parameter*       | *Min Value* | *Max Value*         | *Unit*  |
| ---------         | -------:    | ----:               | ----|
| Voltage range     | -0.5        | 6.0                 | V   |
| High-level output current @VDDIO = 1.8 V |   |  -3    | mA|
| High-level output current @VDDIO = 2.5 V |   |  -5    | mA|
| High-level output current @VDDIO = 3.3 V |   |  -8    | mA|
| High-level output current @VDDIO = 5.0 V |   | -16    | mA|
| Low-level output current @VDDIO = 1.8 V  |   |   3    | mA|
| Low-level output current @VDDIO = 2.5 V  |   |   5    | mA|
| Low-level output current @VDDIO = 3.3 V  |   |   8    | mA|
| Low-level output current @VDDIO = 5.0 V  |   |  16    | mA|
| Pin capacitance                          |   |  15    | pF|


#### Frequency

The maximal frequency depends on the selected VDDIO voltage.

| *Parameter*       | *Min Value* | *Max Value*         | *Unit*  |
| ---------         | -------:    | ----:               | ----|
| VDDIO < 2.5V      |             | 30       | MHz |
| VDDIO >= 2.5V     |             | 40       | MHz |


#### Pull-up resistor

Each bidirectional pin has a pull-up resistor assignet. Each pull-up resistor can enabled or disabled indpendently.

| *Parameter*       | *Min Value* | *Max Value*         | *Unit*  |
| ---------         | -------:    | ----:               | ----|
| Pull-up resistor  |  2.2k-1%    | 2.2k+1%       | Ohm |


#### ESD Protection:
  - Transient Protection for High Speed Lines to:
    - IEC61000−4−2 (ESD) ±15 kV (air), ±8 kV (contact)
    - IEC61000−4−4 (EFT) 40 A
    - IEC61000−4−5 (Lightning) 12 A

### Current consumption 
The SmartWave-Control is supplied via the USB connector.

| *Parameter* | *Min Value*   | *Max Value*   | *Unit*  |
| --------- | -------:| ----:  | ----|
| I_supply| - | 800 | mA  |


### Connector

#### PMOD™
The SmartWave - Control support two fully populated Digilent PMOD™ header with 12 pins each called PMOD-A and PMOD-B. 

The distance between the two PMOD™ connectors follows the standard 12-pin female host port placement descibed in the [Digilent Pmod™ Interface Specification](https://digilent.com/reference/_media/reference/pmod/pmod-interface-specification-1_3_1.pdf).

General information about the digitlent PMOD™ header can bo found [here](https://digilent.com/reference/pmod/start).

The voltage level of the VDDIO can be configured between 1.8 - 5.0V (VBUS). PMOD-A and PMOD-B share the same VDDIO supply level.

| *Pin* | *Function*   |
| --------- | -------|
| 1         | A/B 1     |
| 2         | A/B 2     |
| 3         | A/B 3     |
| 4         | A/B 4     |
| 5         | GND    |
| 6         | VDDIO     |
| 7         | A/B 5     |
| 8         | A/B 6     |
| 9         | A/B 7    |
| 10        | A/B 8    |
| 11        | GND     |
| 12        | VDDIO     |

##### Pinout Diagram

The following drawing shows the pin out diagram for the PMOD™ conectors.

<img src=SmartWave_Blockdiagram_Pin.svg width=50% height=50% alt="SmartWave-Control Pinout Diagram" title="SmartWave-Control Pinout Diagram" style="horizontal-align:center">


#### USB Connector
For the communication with the host (eg PC) a Micro USB (USB-B) connector is used.

### Driver

The following interfaces are supported

#### GPIO

A GPIO allows to drive an output to either es opend drain or push-pull. It is also possible to read back the value.

Each PMOD™ interface pin can be used as GPIO.

#### SPI

The SPI driver operates in master mode. It can receive and transmit data in full duplex mode. Each PMOD™ pin can be assigned to any SPI driver pin.

General information about the SPI interface can bo found [here](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface).

The SPI driver supports the following configuration parameters:

| *Parameter* | *Description*   |
| --------- | -------|
| Bit Width | Number of transferred bits per SPI frame |
| Shift Direction | Defines if MSB or LSB is transferred first |
| Clock Polarity | Defines the polarity of th SPI clock |
| Clock Phase | Defines the phase of each data bit's transmission cycle relative to the SPI clock |
| Chipselect polarity | Defines the Polarity of the SPI chip select signal |
| Frequency  | SPI clock frequency |
  
SPI driver clock specification:

| *Parameter* | *Min Value*   | *Max Value*   | *Unit*  |
| --------- | -------:| ----:  | ----|
| SPI clock| 33 | 0.0005 | MHz  |

#### I2C

The I2C driver operates in controller mode. It can receive and transmit data in half duplex mode. Each PMOD™ pin can be assigned to any SPI driver pin.

General information about the I2C interface can bo found [here](https://www.nxp.com/docs/en/user-guide/UM10204.pdf).

The I2C driver supports the following configuration parameters:
| *Parameter* | *Description*   |
| --------- | -------|
| Frequency | Defines the I2C clock frequency |
| Device ID | Defines the 7-bit target address of the receiver |


| *Parameter* | *Min Value*   | *Max Value*   | *Unit*  |
| --------- | -------:| ----:  | ----|
| I2C clock| 1.83 | 0.0005 | MHz  |


### Display

SmartWave uses an IPS LCD Display to configuration and status information.

| *Parameter* | *Value*   | *Unit*  |
| --------- | -------:| ----  |
| Resolution| 240×320 | px  |
| Colors    | 262k    | -   |
| Diagonal  |  2      | inch|


### Housing
The housing is a robust anodized aluminum housing.

| *Parameter* | *Value*   | *Unit*  |
| --------- | -------:| ----  |
| Width     |      86 | mm    |
| Height    |      67 | mm    |
| Depth     |      32 | mm    |


### Operating Temperature

The operating temperature range is from 10 to 40°C.

