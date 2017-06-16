# SpinCorrelation

Program to calculate the diffuse neutron scattering spectra for a chain of
spins with interactions between the nearest and next-nearest neighbours.

This program is calculating the exact solution of the scattering function
(http://www.nrcresearchpress.com/doi/pdf/10.1139/P10-081). With experimental
data, it can be used to calculate the size and direction of the magnetic
moments carried by the atoms, and the interaction ratio J2/J1.

The result will obviously be as good as the density of the reciprocal grid
(i.e. the number of Q vector) on which the average is performed. As the 
scattering function has to be calculated for each Q vector and summer over
all atomes, the quantity of operations is quite large.

At the moment, the calculation is brute force and could not be further
optimized through standard NumPy functions. To drasticly cut the calculation
time, the code is parallelized, whith the Q-vectors splitted in half, four
or eight, depending on the amount of processors available. Additionnal
calculation technique will be explored in the future.

Physical input required:
- Atomic positions and lattice parameters (i.e. a CIF file)
- Magnetic form factors (www.ill.eu/sites/ccsl/ffacts/ffachtml.html)
- Neutron powder scattering spectra, if fitting is desired.

*** The code will be added as soon as the article for which it was written is published ***
