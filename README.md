# README: Data for "When Bigger Isn't Better: Non‑monotonic Effects of Depth and Width on Neural Approximation and Generalization"

## Repository description blurb
Ten one‑dimensional datasets, 500 points each, used to study non‑monotonic effects of depth and width in neural networks for the Christakis–Fung–Drikakis Neurocomputing submission.

## Overview
This repository contains 10 CSV datasets used in the paper "When Bigger Isn't Better: Non‑monotonic Effects of Depth and Width on Neural Approximation and Generalization" by Nicholas Christakis, Daryl Fung, and Dimitris Drikakis. The manuscript is being submitted to Neurocomputing in 2025.

Each CSV provides a one‑dimensional regression target with 500 samples. Inputs and outputs are scalar. These data are noise free and deterministic. In the study, the same samples are used for training and evaluation to isolate approximation and optimizer stability effects.

Common format across files:
- Rows per file: 500
- Encoding: UTF‑8
- Delimiter: comma
- Header: present
- Line endings: LF
- Missing values: none

Continuous targets use a uniform grid over the stated interval with endpoints included. Discrete sequences 1-3 use integer indices 1 to 500.

## File list and schemas
Files are placed under data/. If you prefer different names or paths, update this section and your scripts accordingly.

1) hofstadter.csv
- Description: Hofstadter‑type recursive sequence
- Domain: n = 1 to 500
- Columns:
  - n: int
  - y: float

2) shifted_additive_recursion.csv
- Description: Shifted additive recursive sequence
- Domain: n = 1 to 500
- Columns:
  - n: int
  - y: float

3) nested_subtractive_recursion.csv
- Description: Nested subtractive recursion
- Domain: n = 1 to 500
- Columns:
  - n: int
  - y: float

4) sinusoidal.csv
- Description: Smooth oscillatory function
- Interval: x ∈ [0, 5]
- Columns:
  - x: float
  - y: float

5) explainable_ai.csv
- Description: Smooth function combining oscillatory and rational terms
- Interval: x ∈ [−10, 10]
- Columns:
  - x: float
  - y: float

6) brain_machine_interfaces.csv
- Description: Oscillatory function with Gaussian‑like decay
- Interval: x ∈ [−15, 15]
- Columns:
  - x: float
  - y: float

7) personalized_medicine.csv
- Description: Multi‑modal Gaussian‑like response surface
- Interval: x ∈ [−6, 6]
- Columns:
  - x: float
  - y: float

8) quantum_fragile_systems.csv
- Description: Fragile target based on sin(1/x) with a defined value at the origin
- Interval: x ∈ [−1, 1], includes x = 0
- Columns:
  - x: float
  - y: float
- Note: This target is highly sensitive near 0. The dataset sets y = 0 at x = 0 to avoid undefined values.

9)pseudo_huber.csv
- Description: Pseudo‑Huber loss with delta fixed to 1
- Interval: x ∈ [−5, 5]
- Columns:
  - x: float
  - y: float

10) smoothed_abs.csv
- Description: Smoothed absolute value with smoothing parameter mu = 10
- Interval: x ∈ [−5, 5]
- Columns:
  - x: float
  - y: float

## How the data are used in the paper
- Task: One‑dimensional regression with scalar input and output.
- Models: Leaky‑ReLU multilayer perceptrons with depths 1, 5, 10 and widths 20, 50, 100.
- Optimizer and training: Adam, learning rate 1e‑3, L2 weight decay 1e‑5, 1,000 epochs. Global hyperparameters are fixed within each target family.
- Protocol: Train and evaluate on the same 500 points per dataset to study approximation and optimizer stability without a hold‑out split.
- Metric: Symmetric Mean Absolute Percentage Error, SMAPE, as reported in the paper.

## License
Creative Commons Attribution 4.0 International, CC BY 4.0.

## How to cite
If you use these datasets, please cite the paper:

Christakis N, Fung D, Drikakis D. When Bigger Isn't Better: Non‑monotonic Effects of Depth and Width on Neural Approximation and Generalization. Submitted to Neurocomputing, 2025.

## Contact
Nicholas Christakis, 
Institute for Advanced Modelling and Simulation, University of Nicosia
