# Astrophysical Simulation Analysis

## Overview
This repository contains Python code developed during a Summer Research Bursary internship at the University of Leeds, focused on analysing the dynamics of inertial waves in large-scale astrophysical simulations. The project investigated resonant interactions and instabilities in rotating fluid systems.

## Contributions
This code was developed collaboratively with my supervisor, Dr. Astoul:
- **A. Astoul** wrote the code to generate the frequency spectra, including the Hanning window and FFT computation
- **A. Gokarn** wrote the code to batch-process and filter simulations, identify resonances and dominant wave modes from the spectra, produce the time series plots, and implement the analytical growth rate prediction

## Note on data
This script runs directly from simulation data and cannot be executed without it. The data was produced as part of the research project and is not publicly available. The code is shared here to demonstrate coding and documentation practices.

## What the code does
The script performs two main analyses on each simulation:

### Frequency Spectra
- Applies a Hanning window to the simulation data to reduce spectral leakage, then computes FFTs for each wave mode
- Plots the frequency spectrum for all modes exceeding a minimum power threshold
- Identifies the three dominant basis frequencies: the two highest-power wave modes and the forcing frequency encoded in the simulation directory name
- Searches for spectral peaks that can be expressed as low-order integer linear combinations of these basis frequencies, identifying triadic resonances and other nonlinear wave interactions
- Labels identified resonances directly on the plot, and marks the forcing frequency and its subharmonic (indicative of parametric instability)

### Time Series
- Plots the log amplitude of the three most energetically dominant wave modes against rotation time
- For the (1,1) mode, fits a line of best fit to the linear growth phase to extract the numerical growth rate
- Compares this against the analytic prediction for the logarithmic growth rate in the linearised case: `(3√3/16) × mean_amplitude × forcing_frequency`
- For simulations exhibiting two distinct growth phases, both are fitted and plotted separately

## Dependencies
- Python 3
- NumPy
- SciPy
- Matplotlib
- SymPy
