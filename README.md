# midi-ocarina
Code, notes and other stuff related to building a midi controller that plays like an ocarina.

## Overview
An ocarina is a small wind instrument about the size and shape of a sweet potato. It's produces a sound similar to a flute. It appears in the Zelda series of games. 

This project is to create a midi controller with the same form factor which can be played in the same way, blowing into a mouthpiece and covering holes / pressing buttons.

The controller can then be used to play a synthesizer via midi.

## Approach

The proposed interface is relatively simple. Buttons will replace the finger holes and an [HX710B air pressure sensor](https://www.homemade-circuits.com/hx710b-air-pressure-sensor-datasheet-how-to-connect/) will be used to measure the player blowing.

The button combination and pressure will be read by a USB Compatible Arduino which will convert them into note and velocity information to be sent via MIDI using the [Arduino Midi library](https://reference.arduino.cc/reference/en/libraries/midi-library/).

## Note information

On an acoustic ocarina different notes are created by covering different combinations of holes. Covering a specific hole alters the frequency by a specific amount. The difference in frequency between notes increases as the notes get higher. Covering a combination of holes alters the frequency of by the sum of the holes covered. Only some of these combinations create notes on a scale.

In midi notes are defined numerically, 42, 43, 44 etc. these will be calculated by mapping the combination of buttons to a specific note value. This could be achieved with a table of combinations, which leads the to the issue of dealing with invalid combinations. Alternatively, each button could be mapped to a frequency change and summed together for each combination then mapped to the closest note, with possibly a associated pitch bend.

# Mouthpiece pressure

The volume of the note produced by an acoustic ocarina is controlled by the pressure of the air blown into the mouthpiece. This should translate into a velocity value in midi.

