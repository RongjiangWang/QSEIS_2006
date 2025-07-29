FORTRAN code for calculating synthetic seismograms based on a layered viscoelastic half-space earth model.

Last update by Rongjiang Wang: Berlin, 29. July 2025

Highlights:

(1) orthonormal propagator algorithm for numerical stability (more efficient than the reflectivity method)

(2) complex frequency technique for supressing the time-domain aliasing problem

(3) wave-number-domain differential filter technique for suppressing numerical phases

(4) various partial solution options

(5) different shallow structures at source and receiver site

(6) earth flattening transformation

Related codes

MSEIS – for marine seismic application

QSEIS2D - for quasi 2D structure model (only teleseismic applications)

For Windows user, the executable file is provided under folder "WindowsEXE". Linux user may compile the source codes with "gfortran" via a single command like, e.g.,

~>cd .../SourceCode

~>gfortran -o qseis2006 *.f -O3

to get the excutable code qseis2006.

After start the executable code, the program ask for an input file in the ASCII format. An example input file is provided under folder "InputFile". You may change the input data included in this file for your own applications.

Notes to the co-ordinate convention used in QSEIS:

(1) Define a local Cartesian co-ordinate system using Aki's convention, that is, x = northward, y = eastward and z = downward. The corresponding local cylindrical co-ordinate system has the same x axis and the azimuth (theta) increasing from north to east as commonly used in seismology.

(2) Decompose your moment tensor or single force to their components in the local Cartesian co-ordinate system.

(3) All Green's functions as outputs of QSEIS are given by their ZRT components in the cylindrical co-ordinate system for a unit source. To consider the effect of radiation pattern, you need to multiply each Green's function output with an azimuth factor, which is given in the documentation of example input file.

(4) The final results for your application are then obtained by convoluting your source components with the corresponding Green's functions.

References

Wang, R., (1999), A simple orthonormalization method for stable and efficient computation of Green's functions, Bulletin of the Seismological Society of America, 89(3), 733-741.

Wang, R., and H. Wang (2007), A fast converging and anti-aliasing algorithm for Green’s functions in terms of spherical or cylindrical harmonics, Geophysical Journal International, doi: 10.1111/j.1365-246X.2007.03385.x.
