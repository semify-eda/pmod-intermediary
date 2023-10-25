# PMOD™ Intermediary - Monitoring and debugging PMOD™ peripherals


<img
  src="https://user-images.githubusercontent.com/52371300/232043387-a45369d5-aef3-471d-a96c-88b0fbe72440.jpg"
  alt="PMOD™ Intermediary"
  title="PMOD™ Intermediary"
  style="display: inline-block; margin: 0 auto; width: 200px"> 
  
  
  
<img
  src="https://user-images.githubusercontent.com/52371300/232043409-f9909ebf-54b3-4fa5-8729-e9a1d9fcb358.jpg"
  alt="PMOD™ Intermediary"
  title="PMOD™ Intermediary"
  style="display: inline-block; margin: 0 auto; width: 300px">


  
## Overview

Our PMOD™ intermediary board is designed for monitoring and debugging purposes, allowing users to monitor all signals of a 12-pin PMOD™ connector.
With this board, debugging connection problems with an existing PMOD™ extension board becomes an easy task.
A green LED, which is integrated into the board, provides a quick and easy way to check the presence of the supply voltage (VCC).

In addition, the board enables users to measure the actual current consumption.
This can be done by either adding an ampere meter in series or measuring the voltage drop across the integrated shunt resistors.

Each power and ground line of the 12-pin PMOD™ connector can be individually measured.

The size and pinout of our PMOD™ intermediary board follow the Digilent Pmod™ Interface Specification, ensuring compatibility with a wide range of devices. With this board, users can easily monitor and debug PMOD™ devices without the need for additional hardware or complex set-ups.

## Current measurement

Are you aware of the current consumption of your PMOD™ board?

It is crucial to know the current consumption of your PMOD™ peripheral board, especially if it approaches the limits of the host power supply. The PMOD™ Intermediary board offers two ways to measure the current consumption.

The PMOD™ intermediary provides four current consumption measurement points.

  | Pin  | Signal |
  | ---- | ------ |
  | 5    | GND  |
  | 6    | VCC  |
  | 11   | GND  |
  | 12   | VCC  |


### Average current using an ampere meter
To measure the average power consumption, simply remove the corresponding jumper and connect an ampere between pin 1 and pin 2. This allows for an accurate measurement of the current drawn by the PMOD™ device.

THe current can be measured in the VCC as well as in the GND path.

### Dynamic current using shunt resistor
To measure the dynamic power consumption of the PMOD™ device, insert the shunt resistor into the supply (VCC) or ground (GND) line. This can be achieved by shorting pin 2 and pin 3 of the corresponding header with a jumper. The current can then be calculated by measuring the voltage drop across the shunt resistor. This allows for an accurate measurement of the dynamic current drawn by the connected PMOD™ peripheral.

The shunf resistor has a value of 100mOhm.

$I = U / R $

A voltage drop of 100mV corresponds to a current of $I = 0.1 / 0.1 = 1A $.

To avoid any impact of the voltage drop across the shunt resistor during normal operation it is recommended to short the shunt resistor. This can be achieved by shorting pin 1 and pin 2 of the corresponding header with a jumper.

## External supply voltage

By removing the jumper and connecting an external power supply to the VCC header pin 1, the PMOD™ can be powered using an external power source.

**Caution** When using an external power supply, it is important to take precautions to avoid exceeding the allowed voltage ranges of the connected devices of the PMOD™ host and peripherals.

## Reference

  - [Schemtaic](https://github.com/semify-eda/pmod-intermediary/blob/main/pmod-intermediary.pdf)
  - [Digilent Pmod™ Interface Specification](https://digilent.com/reference/_media/reference/pmod/digilent-pmod-interface-specification.pdf)

