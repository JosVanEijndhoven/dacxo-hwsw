# Audio DAC main digital PCB
## Introduction
This board implements the main DAC functionality and features:

- Input switching between 5 inputs:
  - Two optical sp/dif inputs
  - Two coax sp/dif inputs
  - One i2s input

- Two high-quality (very low phase noise) crystal oscillators, in this case the Crystek CCHD-957.
  Their quality is a crucial basis for a low-jitter DAC.
  Availability of two oscillator frequencies avoids complex (non-power-of-two) sample rate conversion,
  retaining more of the original music.
  - To handle 44.1kHz samplerate audio (from CD), one oscillator has a frequency of 1024*44.1 kHz = 45.1584 MHz
  - To handle 48kHz (from TV), 96kHz and 192 kHz (from high-resolution audio files),
    one oscillator has a frequency of 1024*48 kHz = 49.152 MHz.



  
  
