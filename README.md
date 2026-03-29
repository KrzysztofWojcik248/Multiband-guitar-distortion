# Multiband-guitar-distortion

This is my design of multiband guitar distoriton suitable for bass. I designed it becuase I wanted to have bass distortion where sub is clean and everything is adjustable.

# My design features:

- Three independent bands: Sub, low-mid and high-mids with highs
- Adjustable gain for clipping and volume in out of every band
- transistor based clipping in low-mid
- Choice between soft (led) and hard (si) clipping diodes in high band clipping

# How it works:

As shown on the block schematics below:
<img width="1750" height="1080" alt="MultiBandDistortionBlockSchematics" src="https://github.com/user-attachments/assets/7e349bcf-4c51-4ef7-8614-bed55bec5f10" />

Audio signal is provided by audio jack to the circut, then the signal amplitude is adjsuted and signal is placed on 4.5V (half of the power supply) so gain and filters aree able to work on proper range. Then signal is processed by Sallen-Key active filters. Theree are gaps between the bands ranges, but second order filters provides only 12 Db/oct slopes so these gaps provides better transistion between bands without cumulating amplitudes of different bands.
