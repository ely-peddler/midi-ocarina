# midi-ocarina
Code, notes and other stuff related to building a midi controller that plays like an ocarina.

## Overview
An ocarina is a small wind instrument about the size and shape of a sweet potato. It's produces a sound similar to a flute. It's appears in the Zelda series of games. 

The project is to create a midi controller with the same form factor which can be played in the same way, blowing into a mouthpiece and covering holes / pressing buttons.

The controller can then be used to play a synthesizer via midi.

## Approach

The proposed interface is relatively simple. Buttons will replace the finger holes and an [air pressure sensor](https://www.homemade-circuits.com/hx710b-air-pressure-sensor-datasheet-how-to-connect/) will be used to measure the players blowing. 

Air pressure sensor - 

The button compination and pressure will be read by an Arduino which will convert them into midi information using the [Arduino Midi library](https://reference.arduino.cc/reference/en/libraries/midi-library/)

