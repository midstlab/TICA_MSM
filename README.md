
In this code, a trajectory of a 1000-nanosecond molecular dynamics simulation of ferric binding protein (FBP) is analyzed, focusing on its conformational transition from the apo to holo state.

TICA-MSM

This code enables the investigation of the slow conformational dynamics of proteins by applying Time-Independent Component Analysis (tICA) and constructing a Markov State Model (MSM) from molecular dynamics trajectories. Additionally, the notebook performs an overlap analysis to assess the ability of the tICA space to capture the system’s slowest kinetic modes. This integrative approach helps in identifying metastable states and transition kinetics in complex biomolecular systems.

Parameters to Adjust in the Notebook

If you are using this notebook for the first time, you may want to modify the following key parameters based on your own simulation or analysis goals:

lagtime: Number of frames used as lag time in tICA and MSM.

n: Number of time-independent components (tICs) retained in tICA.

n_clusters: Number of microstates used for clustering tICA data.

Code works as follows:

A DCD trajectory file and corresponding PSF topology file should be provided.

Backbone dihedral angles (φ and ψ) are computed using MDTraj.

These angles are concatenated to build a feature matrix.

The feature matrix is projected into a lower-dimensional space using tICA.

The tICA data is clustered into microstates using MiniBatchKMeans.

A Markov State Model (MSM) is constructed using the clustered data with the deeptime library.

Model validation is performed by:

Visualizing microstate transitions over time

Plotting implied timescales across lag times

Calculates overlap between tICA components and MSM eigenvectors.

Shows how well tICA captures the slowest kinetic processes.

Results are shown as a bar plot.

Output files and visualizations include:

predicted_conformation.pdb: Representative structure from the most populated MSM state

tica_projection.png: 2D scatter plot of the first two tICs

implied_timescales.png: Lag time vs implied timescale plot

overlap_plot.png: Bar plot of tICA–MSM overlaps
