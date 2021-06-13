# Peltor-interface
Interface for the Peltor MT72H61B P930472 headset.

The Peltor MT72H61B is a Military headset with microphone, and push to talk button. It has a special highly rugged connector.


![Headset overview](https://raw.githubusercontent.com/gbThreepwood/Peltor-interface/master/images/headset_overview.jpg "Headset overview")

This project attempts to document the interface, in order for the headset to be used for applications outside of what was probably originally intended by the manufacturer. E.g. to connect it to a PC for use in online meetings.

## Internal wiring

The speaker measures 118 Ohm, while the microphone is a dynamic type, and measures 235.6 Ohm.


The cable between the switch box and the headset has 4 wires, which are connected according to the following table:

| Color         | Device        |
| ------------- |:-------------:|
| Black         | Mic           |
| Yellow        | Mic           |
| White         | Speaker       |
| Red           | Speaker       |
 
The switch is a 4PDT type 7413 from K&R. This is a special device with varying operation for each of the 4 switches. The datasheet is available here: https://no.mouser.com/datasheet/2/60/7000toggle-1841888.pdf





## Pre amplifier circuit

In order to use dynamic microphones with normal PC sound cards, a pre-amplifier
is usually required.

This can be as simple as a single transistor, common emitter amplifier. For low
noise however a slightly more elaborate design is required.

## Stereo to mono conversion

A typical PC sound card has stereo output. In order to ensure that no parts of
the audio is lost, both channels should be merged in the mono input to the
headset.
