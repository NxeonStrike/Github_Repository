# Astrophysical Simulation Analysis

## Overview
This repository contains Python code developed during a Summer Research Bursary internship at the University of Leeds, focused on analysing the dynamics of inertial waves in large-scale astrophysical simulations. The project investigated resonant interactions and instabilities in rotating fluid systems.

## Contributions
This code was developed collaboratively with my supervisor, Dr Astoul. Dr Astoul wrote the code to generate the frequency spectra, including the Hanning window and FFT computation. I wrote the code to batch-process and filter simulations, identify resonances and dominant wave modes from the spectra, produce the time series plots, and implement the analytical growth rate prediction.

## Note on data
This script runs directly from simulation data and cannot be executed without it. The data was produced as part of the research project and is not publicly available. The code is shared here to demonstrate coding and documentation practices.

## What the code does
The script performs two main analyses on each simulation.

For the frequency spectra, the script applies a Hanning window to reduce spectral leakage before computing FFTs for each wave mode, and plots the spectrum for all modes exceeding a minimum power threshold. It identifies three dominant basis frequencies (the two highest-power wave modes and the forcing frequency encoded in the simulation directory name) and searches for spectral peaks expressible as low-order integer linear combinations of these, identifying triadic resonances and other nonlinear wave interactions. Identified resonances are labelled directly on the plot, along with the forcing frequency and its subharmonic, which is indicative of parametric instability.

For the time series, the script plots the log amplitude of the three most energetically dominant wave modes against rotation time. For the (1,1) mode, a line of best fit is fitted to the linear growth phase to extract the numerical growth rate, which is then compared against the analytic prediction for the logarithmic growth rate in the linearised case: `(3√3/16) × mean_amplitude × forcing_frequency`. For simulations exhibiting two distinct growth phases, both are fitted and plotted separately.

## Dependencies
Python 3, NumPy, SciPy, Matplotlib, SymPy
