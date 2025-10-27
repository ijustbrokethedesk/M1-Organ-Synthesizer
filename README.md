# Analog Synthesis of the M1 Organ 2 Preset

An analog implementation of the Korg M1 Organ 2 preset.

I love this sound which was popularized by 90's House music, and I wanted to recreate it from scratch.

## Prototype
Instead of trying to design an entire synthesizer at once, this project is split up into multiple components which will be designed and tested separately.
I will need to develop a dual waveform voltage controlled oscillator (VCO), exponential converter, voltage controlled amplifier (VCA), envelope generator, filter, and class AB amplifier.

-  [x] Dual Waveform VCO
-  [ ] Exponential Converter
-  [ ] Envelope Generator
-  [ ] Voltage Controlled Amplifier
-  [ ] Lowpass Filter
-  [ ] Class AB Amplifier

### Sound Design
The M1 Organ 2 preset can be recreated through mixing a series of triangle and / or square waves. I have researched and outlined two methods I am interested in testing.

$OSC_{X}^N\qquad$ X : Type of Waveform, N : Number of semitones above base note

Method 1: $OSC_{tri} + OSC_{sqr}^7$

Method 2: $OSC_{tri} + OSC_{tri}^7 + OSC_{tri}^{-12} + OSC_{tri}^{-5}$

### Oscillator Core

Design uses an op amp bistable integrator VCO which produces both triangle and square wave output.
The pitch controlled by voltage, compatible with exponential converter

## Exponential Converter (WIP)
While musical scales are linear, humans perceive audible frequencies (or pitch) on an exponential scale. 

Take the note A for example: A1 = 110Hz, A2 = 220Hz, A3 = 440Hz... As you increase in octave linearly, the frequency doubles each time

An exponential converter translates the linear input voltages to exponential output voltages for VCO
