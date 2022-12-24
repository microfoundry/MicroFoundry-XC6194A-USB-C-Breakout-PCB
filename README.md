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
- VIn or VOut
- GND
- USB-C Functionality Pass-Through
- 5.1k resistors for 5v power delivery negotiation
### IO
1. VIn  - Voltage In 
2. GND  - Ground
3. VOut - Voltage Out
4. SW   - Momentary Switch Input (Active LOW)
5. PG   - Power Good Output (Active HIGH)
6. SHDN - Shutdown Input (Active HIGH)
### Expansion
1. VIn  - Voltage In 
2. GND  - Ground
3. VOut - Voltage Out
4. SW   - Momentary Switch Input (Active LOW)
5. PG   - Power Good Output (Active HIGH)
6. SHDN - Shutdown Input (Active HIGH)

**NOTE:** All IO/Expansion pins operate at VIn level. If the XC6194A IO are connected to an MCU, please verify voltage compatability or utilize one of the optional Micro Foundry XC6194A expansion PCBs.

## XC6194A Breakout PCB Variants
- [Micro Foundry XC6194A JST PH Style Breakout PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-PH-Breakout-PCB)
- [Micro Foundry XC6194A Micro USB Breakout PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-Micro-USB-Breakout-PCB)
- [Micro Foundry XC6194A USB-C Breakout PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-USB-C-Breakout-PCB)

## XC6194A Expansion PCBs
- [Micro Foundry XC6194A Discrete Logic RGB Expansion PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-Discrete-Expansion-PCB)
- [Micro Foundry XC6194A WS2811 RGB Expansion PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-WS2811-Expansion-PCB)
- [Micro Foundry XC6194A IS31FL3193 RGB Expansion PCB](https://github.com/microfoundry/MicroFoundry-XC6194A-IS31FL3193-Expansion-PCB)
