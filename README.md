# 8×8×8 LED Cube

## Overview

This project is an 8×8×8 LED cube consisting of 512 LEDs controlled by an Arduino.  
The system uses SPI-driven shift registers for LED data and transistor-based layer switching to multiplex the cube. Multiple animations are implemented, with a push button used to cycle between display modes.

---

## Project Description

The LED cube is refreshed using rapid layer multiplexing. Each horizontal layer is enabled individually while column data is shifted in using SPI. By cycling through layers at a high refresh rate, the cube appears fully illuminated in three dimensions due to persistence of vision.

The project was designed with modular animation logic to allow new patterns to be added easily.

---

## Demonstration

### Images

Project images will be added in the following directory:

docs/images/

### Videos

Demonstration videos or GIFs will be added in:

docs/videos/

---

## Features

- 512 LEDs arranged in an 8×8×8 configuration
- Multiplexed layer scanning (8 layers)
- SPI communication for efficient data transfer
- Multiple built-in animations
- Push-button animation selection
- Expandable animation framework

---

## Hardware

### Components

- Arduino (exact model configurable)
- 8×8×8 LED cube
- Shift registers (e.g., 74HC595)
- Layer drivers (ULN2803 or discrete NPN BJTs)
- Current-limiting resistors
- Push button
- External power supply
- Wiring and connectors

### Schematic

The circuit schematic is located at:

docs/schematic/led-cube-schematic.png

---

## System Operation

1. A single layer is enabled using transistor drivers
2. LED data for that layer is shifted into the registers via SPI
3. The latch signal updates the outputs
4. The process repeats for all layers at a high refresh rate

This process creates the illusion of a fully lit three-dimensional display.

---

## Repository Structure

.
├── code/
│   ├── led_cube.ino
│   ├── animations/
│   └── drivers/
├── docs/
│   ├── images/
│   ├── videos/
│   └── schematic/
└── README.md

---

## Getting Started

### Uploading the Code

1. Open led_cube.ino in the Arduino IDE
2. Select the correct board and serial port
3. Upload the firmware

### Power Considerations

Because of the large number of LEDs, current draw can be significant. An external power supply is recommended. Ensure that the Arduino ground and external supply ground are connected.

---

## Controls

- Button press cycles through available animations

Additional control features can be implemented in software if desired.

---

## Animations

Examples of animations included in this project:

- Layer scanning
- Plane sweeps along X, Y, and Z axes
- Expanding and contracting cube patterns
- Random sparkle effects
- Wave propagation patterns

---

## Customization

### Adding New Animations

- Implement a new animation function
- Add it to the animation selection logic
- Recompile and upload the firmware

### Performance Tuning

- Adjust layer refresh timing to reduce flicker
- Optimize SPI speed for smoother animations
- Modify animation frame delays as needed

---

## Troubleshooting

- Flickering display: check refresh timing and grounding
- Dim LEDs: verify power supply capacity
- Incorrect patterns: inspect shift register wiring and latch timing
- Non-functional layer: test transistor drivers and connections

---

## Lessons Learned

This section documents design challenges, timing considerations, and improvements identified during development.

---

## Future Improvements

- Software-controlled brightness adjustment
- Wireless or serial animation control
- Sound-reactive animation modes
- Expanded animation library

---

## License

Specify a license for this project (e.g., MIT or GPLv3).  
Include a LICENSE file in the repository if applicable.

---

## Author

Developed by Your Name
