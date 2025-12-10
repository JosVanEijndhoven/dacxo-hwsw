# Audio DAC and digital pre-amp with low jitter

## Introduction

This repository provides all HW and SW sources of my DIY audio DAC design.
The 'audio Digital-to-Analog Conversion' is the heart and main aim of the design.
However, more audio device functionality was built around that:

- Functionality for a digital pre-amp is provided, with input selection
  and volume control. Inputs are optical and coax SP/DIF, HDMI-arc, and a network DLNA player.
- The control UI (user interface) is created with `esphome`.
  Besides the front panel control knob, this also provides remote control from a mobile phone
  and/or integration in *home assistant* automation environments.
- The core DAC design aims for high-end audio, with a focus on low jitter, not
  trying to reach low component cost.

The intention is to show some solutions across a wide range of design choices,
potentially of interest to other DIY audio enthousiasts. Supporting purely cloning the full hw/sw design is not the intention, as some design files might be outdated for the various and components tools that were used: the design start was around 2015. (But its development still continous in 2026...)
This DAC design builds on previous experience: it is my 5th design.

## Contents

This repository contains all hardware and software design aspects:

- [The front control and remote UI software](./esphome-ui/)
  based on a commercial *esp32-s3* board with display.
- The digital signal processing board, schematics and PCB design,
  in the `dacxo-hw/PCBs/PCB-dacxo/` folder.
- The logic configuration of the FPGA on that board,
  in the `dacxo-hw/FPGA-content/` folder.
- The analog output board, schematics and PCB design,
  in the `dacxo-hw/PCBs/PCB-opampout` folder.
- The use of this DAC board as audio output in a Raspberry Pi
  DLNA renderer, including Linux kernel drivers,
  in the `dacxo-sw/RPi-audiodevice` folder.

## License
All source and configuration files provided in this repository are provided without any warrenty,
and under copyright and license:

Copyright 2025 Jos van Eijndhoven

[GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0.nl.html)

