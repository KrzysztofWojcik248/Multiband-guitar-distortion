# Multiband-guitar-distortion

This is my design of multiband guitar distortion suitable for bass. I designed it because I wanted to have bass distortion where sub is clean and everything is adjustable.

## Table of Contents
- [Project Goals](#project-goals)
- [My Design Features](#design-features)
- [How It Works](#how-it-works)
- [Circuit Schematic](#circuit-schematic)

## Project Goals:
The goal of this project is to design and build a distortion pedal suitable for guitar and bass. I want it to provide solid and clean bass fundamentals with sharp mids and highs. My motivation is very limited choice of products on the market, in which you can adjust processing of different bands independently creating different sounds.

## My Design Features:

- Three independent bands: Sub, low-mid and high-mids with highs
- Adjustable gain before clipping and volume for each band
- transistor based clipping in low-mid
- Choice between soft (led) and hard (si) clipping diodes in high band clipping

## How It Works:

As shown on the block schematic below:
<img width="1750" height="1080" alt="schemat" src="https://github.com/user-attachments/assets/59ac8ee4-b57c-42ae-a54a-88667e11b8af" />


Audio signal is provided by audio jack to the circuit, then the signal amplitude is adjusted and signal is placed on 4.5V (half of the power supply) so gain and filters are able to work on proper range. Then signal is processed by Sallen-Key active filters. There are gaps between the bands ranges, but second order filters provides only 12 Db/oct slopes so these gaps provides better transistion between bands without cumulating amplitudes of different bands. After filtration there are three indepentent bands. The sub-bass band (<120Hz) has only a volume knob to adjust volume of lows in the mix. It doesn't have any other processing because clipping fundamental harmonics at most casses destroys the sound. The second band is low-mids (140Hz-850Hz) after filtration there is a gain based on non-inverting op-amp like volume in sub band. The difference is, that in this case after gain there are two NPN clipping transistors, so the gain knob determines how strong the clipping is. Bias in this section is not 4.5V but 5.7V which provides asymetrical clipping and there are two transistors instead of one, because clipping signal two times can provide warmer feel then one stronger distortion. The gain knob on minimal position can provide clear signal and maximal position can provide strong clipping. Volume knob lets suit the signal to the rest of the mix. High band (>950Hz) works very similar to low-mids, but instead of transistor there are clipping diodes. One diode is red led, and the second one is selected between harder si diode and softer yellow diode. This variety lets you choose between soft warm highs and sharp, distorted ones. Every band after processing comes through a resistor to summing op-amp which provides output signal to audio jack. In the end there is led limiter which limits signal when it is too close to 2V.

## Circuit Schematic
Image below shows my attempt to realizee this idea:
<img width="3507" height="2480" alt="MultiBandDistortionSchematics" src="https://github.com/user-attachments/assets/7529868a-a74a-42e4-9fb7-2263521626f4" />
This schematic features some additional comments. Most of them shows gain of amp or voltage divider, because voltage levels are very important for safety and mixing bands.

