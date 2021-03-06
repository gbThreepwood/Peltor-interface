# Peltor-interface
Interface for the Peltor MT72H61B P930472 headset.

The Peltor MT72H61B is a Military headset with microphone, and push to talk button. It has a special highly rugged connector.


![Headset overview](https://raw.githubusercontent.com/gbThreepwood/Peltor-interface/master/images/headset_overview.jpg "Headset overview")




![Connector](https://raw.githubusercontent.com/gbThreepwood/Peltor-interface/master/images/connector.jpg "Connector")

This project attempts to document the interface, in order for the headset to be used for applications outside of what was probably originally intended by the manufacturer. E.g. to connect it to a PC for use in online meetings.

## Internal wiring


![Connection box](https://raw.githubusercontent.com/gbThreepwood/Peltor-interface/master/images/connection_box.jpg "Connection box")

The speaker measures 118 Ohm, while the microphone is a dynamic type, and measures 235.6 Ohm. The speakers for right and left ear are connected in parallel, i.e. the individual speaker impedance is probably twice of what is measured.


The cable between the switch box and the headset has 4 wires, which are connected according to the following table:

| Color         | Device        |
| ------------- |:-------------:|
| Black         | Mic           |
| Yellow        | Mic           |
| White         | Speaker       |
| Red           | Speaker       |
 
The switch is a 4PDT type 7413 from K&R. This is a special device with varying operation for each of the 4 switches. The datasheet is available here: https://no.mouser.com/datasheet/2/60/7000toggle-1841888.pdf

The cable from the switch box, to the connector has six wires, connected
according to the follwoing table:

| Color         | Device        | Comment                                                |
| ------------- |:-------------:|:-------------:                                         |
| Black         | Mic           | Mic + connected through switch, disconnect in pos 1    |
| Yellow        | Mic           | Mic -                                                  |
| White         | Speaker       | Speaker +                                              |
| Red           | Speaker       | Speaker -                                              |
| Brown         | Switch        | Switch connects to red wire in pos 1                   |
| Green         | PTT           | Momentary switch connects to red wire in pos 3         |
 

## Pre amplifier circuit

In order to use dynamic microphones with normal PC sound cards, a pre-amplifier
is usually required. The inputs are typically only designed for electret
microphones.

If used with the microphone input, this can be as simple as a single transistor, common emitter amplifier. For low
noise however a slightly more elaborate design is required.

## Stereo to mono conversion

A typical PC sound card has stereo output. In order to ensure that no parts of
the audio is lost, both channels should be merged in the mono input to the
headset.

This is solvable in software, but a hardware solution will ensure that the
headset will operate immediately when switching to a new PC.


## Telephone interfacing circuit

The headset is supported by the RA2000 army field telephone. If such a phone is
availabe, it is thus an option to interface the phone with the PC, instead of directly interfacing the headset.

