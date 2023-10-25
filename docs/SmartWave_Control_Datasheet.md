# Datasheet
## Block diagram
## Electrical parameter
### IOs
  - IO Voltage range
  - Pull-up resistor value
  - Current Drive capability
  - Rise and fall time on a given load
  - Current drive capability
  - Maximal frequency

### Connector

#### PMOD™
The SmartWave - Control support two fully populated Digilent PMOD™ header with 12 pins each called PMOD-A and PMOD-B. 

The distance between the two PMOD™ connectors follows the standard 12-pin female host port placement descibed in the (Digilent Pmod™ Interface Specification)[https://digilent.com/reference/_media/reference/pmod/pmod-interface-specification-1_3_1.pdf].

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

#### USB Connector
  - Type
  -
### Current consumption 

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
