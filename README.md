# Quasinormal Mode Extraction
Extract_Ringdown.py extracts quasinormal (spheroidal) mode amplitudes from the ringdown of a black hole coalescence. The algorithm has been tested in the large mass-ratio limit, for gravitational radiation calculated through the time-domain Teukolsky's equation.

You are welcome to use the code in any way you like, though we ask that if you use any results from it in a paper that you cite the following papers:
 - Lim, Khanna, Apte and Hughes (2019, https://arxiv.org/abs/1901.05902)
 - Hughes, Apte, Khanna, and Lim (2019, https://arxiv.org/abs/1901.05900)

Please also refer to the above papers for definitions of variables, conventions, and procedures used in the code. All quantities are expressed in Boyer-Lindquist coordinates in units of central hole mass M and all mode amplitudes are scaled by $\mu / D$

## Format of Input Data
Extract_Ringdown.py expects both trajectory and waveform input data.

### Trajectory file format

- One worldline/trajectory file with 10 columns: (time, r, theta, dr/dt, dtheta/dt, dphi/dt, phi, E, lz, Q)

### Waveform file(s) format

- Must provide multiple sherical harmonic waveform modes hlm, where (l,m) are the spherical harmonic indices

- Each file should contain several columns for each hlm component corresponding to a single m value:

  - m = 0: time, h00+, h00x, h10+, h10x, h20+, h20x
  - m = 1: time, h11+, h11x, h21+, h21x, h31+, h31x
  - m = 2: time, h22+, h22x, h32+, h32x, h42+, h42x
  - m = 3: time, h33+, h33x, h43+, h43x, h53+, h53x
  - m = -1: time, h1-1+, h1-1x, h2-1+, h2-1x, h3-1+, h3-1x
  - ...

- Our current implementation is tailored to 0 < |m| < 4 with l - |m| < 3.
