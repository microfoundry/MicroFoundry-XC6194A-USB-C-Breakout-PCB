# MicroFoundry-XC6194A-USB-C-Breakout-PCB
Information about the XC6194A Breakout with USB-C connectors.

## XC6194 Description
The TOREX XC6194A series device is load switch with functions best suited for a momentary push button and features to enhance battery operated devices.

The built-in high side switch is turned on and latched by inputting LOW level signal from a momentary switch to the SW (Switch) pin. It is turned off by a HIGH level signal into the SHDN (Shutdown) pin from the MCU or the like. Optionally, power-off state can be achived with the XC6194A series by inputting a continous LOW level signal for the duration of TOFFD (Turn-Off Delay) to the SW pin.

When the SW and SHDN signals are wired to MCU IO, end-user developed code can cleanly close connections, stop processes and then output the required SHDN signal when appropriate. Additionaly, the Turn-Off Delay functionality offers a fail-safe option to power down.

## XC6194 Features

| Feature              | Description                     |
| -------------------- | ------------------------------- |
| Input Voltage Range  | 1.8V ~ 6.0V                     |
| Stand-by Current     | 0.001μA (TYP.) / Turn-Off state |
| Quiescent Current    | 0.13μA (TYP.) / Turn-On state   |
| Output Current       | 1000mA (VIN=2.0V, Ta=25℃)      |
| Turn-On Delay Time   | 0.2s, 1.0s, 3.0s or 5.0s        |
| Turn-Off Method      | <ul><li>By inputting “H” voltage to the SHDN pin.</li><li>By inputting “L” voltage for the duration of TOFFD to the SW pin.</li></ul>|
| Turn-Off Delay Time  | 3s, 5s, 10s or 15s |
| Added Functions      | <ul><li>Power Good function (The PG pin)</li><li>Shutdown function (the SHDN pin)</li></ul>|
| Protective Functions | <ul><li>Output capacitor inrush current limit soft-start</li><li>Output capacitor discharge function</li><li>Output short circuit protection</li><li>Thermal shutdown</li></ul>|
| Operating Ambient Temperature | -40℃ ~ 85℃ | 
| Package | USP-8B06 (2.0 x 2.0 x h0.33mm) |

## The Micro Foundry XC6194A Breakout
This is a practical application of the XC6194A IC with USB-C connectors for VIn/VOut/USB-C pass-through functionality, a JST SH style connector to provide IO access to the XC6194A functions, essential passive components required for basic operation and voltage-in/voltage-out LEDs. An additional 1.0mm pitch FFC connector offers expansion capabilities for optional breakout PCBs with features like voltage level signal translation and the ability to drive up to 3 LEDs for RGB momentarty switches such as those sold by Adafruit. The PCB is 26x26 mm with 4x 2.5mm mounting holes.

## Pinouts
### VIn/VOut
- USB-C connectors
- Data Pass-Through
- 5.1k resistors on VIn CC1 & CC2 for 5v power delivery negotiation
### IO
JST SH style connector, 1.0mm Pitch, 6 Position

| Pin | Function | Description | XC6194A IO |
| --- | -------- | ----------- | ---------- |
| 1 | VIn | XC6194A Voltage In | |
| 2 | GND | Ground | |
| 3 | VOut | XC6194A Switched Voltage Out | |
| 4 | SW | XC6194A Momentary Switch | Input (Active LOW) |
| 5 | PG | XC6194A Power Good | Output (Active HIGH) |
| 6 | SHDN | XC6194A Shutdown | Input (Active HIGH) |

**NOTE:** All IO/Expansion pins operate at VIn level. If the XC6194A IO are connected to an MCU, please verify voltage compatibility or utilize one of the optional Micro Foundry XC6194A expansion PCBs.

### Expansion
FFC ZIF connector with backlock, 1.0mm Pitch, 6 Position. Pinout is the same as the IO port above.

**NOTE:** The FFC connector is a bottom/top common contact design. I.e., there will be power and IO signals present regardless of which orientation the FFC jumper is inserted. Please exercise caution when connecting external devices and double check pin-to-pin mapping.

### Additional IO Pin Info
Basic XC6194A functionality can be achived utilizing the IO connector.
- SW Pin: When wired to a N.O. (normally open) momentary switch with the other switch leg connected to GND, pressing the switch will avtivate the XC6194A's internal mosfet and deliver power to VOut. Pressing the switch for the required Turn-Off Delay will turn off the XC6194A. The XC6194A Breakout has the required pull-up resistor on the SW circuit. 
- PG Pin: The Power Good Output is traditionally utilized to enable a downstream power supply with an Active High Enable input. Within the XC6194 functional logic, the PG pin state is controlled by the On/Off, Short Circuit Protection, Thermal Shut Down, and Soft Start logic blocks. The XC6194A Breakout has the required pull-up resistor on the VOut circuit.
- SHDN Pin: A HIGH signal on this input will trigger an immediate shut down, VOut will be disconnected and PG will be pulled low.
- VOut: The breakout circuit contains a 0 Ohm (Zero) series resistor allowing this Output to be utilized with a LED, such as a single color LED momentary switch. The resistor can be replaced with one of an appropriate value if current control is required.

## XC6194A Breakout PCB Variants
- [Micro Foundry XC6194A JST PH Style Breakout PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-PH-Breakout-PCB)
- [Micro Foundry XC6194A Micro USB Breakout PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-Micro-USB-Breakout-PCB)
- [Micro Foundry XC6194A USB-C Breakout PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-USB-C-Breakout-PCB)

## XC6194A Expansion PCBs
- [Micro Foundry XC6194A Discrete Logic RGB Expansion PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-Discrete-Expansion-PCB)
- [Micro Foundry XC6194A WS2811 RGB Expansion PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-WS2811-Expansion-PCB)
- [Micro Foundry XC6194A IS31FL3193 RGB Expansion PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-IS31FL3193-Expansion-PCB)
