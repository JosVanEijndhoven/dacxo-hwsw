# Analog output stage
## Introduction
This PCB provides a textbook style opamp-based analog output to accompany the digital PCB.
This PCB was designed to function as basic reference (starting point) for other
more high-end analog audio alternatives.

The main functionality of this board is:

- Implement the current-to-voltage conversion that is needed for the (current output of) the PCM1792a dac chips.
- Create stereo balanced output on a pair of XLR connectors.

## Analog opamp output circuitry
For analog signal handling, the board currently uses LME49720 type dual operational amplifiers.
These are low-noise, low distortion, and low offset error opamps, intended for audio applications.

The first stage of opamps (U202 and U204 in the schematic) are used for current-to-voltage conversion.
The second stage of opamps (U201 and U203) are used for differential amplification
of the positive and negative signal outputs of the DAC chips.
This differential amplification is used for both:

- Filtering out common-mode distortion and power-supply artefacts, resulting in clean audio output.
- Filtering out the DC offset that is part of the PCM1792A output current.

To achieve good common-mode and DC suppression, it is needed that both of these stages
are accurately balanced. For that purpose, this implementation uses 0.1% accurate resistors
to set the opamp gains. Furthermore, the PCB provides empty posistions to mount extra resistors in
parallel to the 'main' resistors: this allows optional fine-tuning of the balancing,
if the initially obtained balance would not be satisfactory.
For now, these extra resistor positions are not mounted.

For resistor type, the design uses cylindrical 'MMA 0204' professional grade Vishay Beyschlag resistors.
These resistors have a decent *current noise* specification in their datasheet.
I would recommend to not buy any alternative resistor types for high-end audio
that are not provided with a specification of their (current-) noise.
In other designs I have preferred their larger 'MMB 0207' versions,
as these have a significantly better noise specification.
Unfortunately, I could not easily buy those larger versions with a 0.1% accuracy specification.

## Attenuation relay



