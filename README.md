# Multiband-guitar-distortion

This is my design of multiband guitar distortion suitable for bass. I designed it because I wanted to have bass distortion where sub is clean and everything is adjustable.

# Project goals:
Goal of this project is to design and build a distortion pedal suitable for guitar and bass providing solid and clean bass fundamentals with sharp mids and highs. My motivation is very limited choice of products on the market, in which you can adjust processing of different bands independently creating different sounds.

# My design features:

- Three independent bands: Sub, low-mid and high-mids with highs
- Adjustable gain for clipping and volume in out of every band
- transistor based clipping in low-mid
- Choice between soft (led) and hard (si) clipping diodes in high band clipping

# How it works:

As shown on the block schematics below:
<img width="1750" height="1080" alt="MultiBandDistortionBlockSchematics" src="https://github.com/user-attachments/assets/7e349bcf-4c51-4ef7-8614-bed55bec5f10" />

Audio signal is provided by audio jack to the circuit, then the signal amplitude is adjusted and signal is placed on 4.5V (half of the power supply) so gain and filters are able to work on proper range. Then signal is processed by Sallen-Key active filters. There are gaps between the bands ranges, but second order filters provides only 12 Db/oct slopes so these gaps provides better transistion between bands without cumulating amplitudes of different bands.
