# BayesianGLM_stability

Distributed Temperature Sensing offers an unprecendented view into the vertical structure of the boundary layer. 

## Data Preparation

All of the data used in this study come from the Large-eddy Observatory, Voitsumra Experiment 2019 (LOVE19). They are available through Zenodo (doi: 10.5281/zenodo.4312976). They are not included in the repository due to their size.

The data preparation notebooks contain all of the data munging for this mini-experiment, especially for creating homogeneous potential tempreature data for comparing across the entire LOVE19 column.

## stability

I take advantage of DTS's unique ability to describe the vertical gradient temperature. Stability ($\frac{dT}{d\ln{z}}$) is estimated for the first time using DTS (`bayesian-GLM_estimate-dTdz.ipynb`). When combined with a Bayesian Generalized Linear Model stability appears to be better described than when using point observations and/or traditional linear fitting methods.

After deriving stability it is evaluated (`evaluate_dTdlnz.ipynb`), the CSAT and DTS air temperature biases are investigated (`evaluate_dTdlnz.ipynb`), the factors that control stability are investigated using PCA (`investigate_dTdlnz.ipynb`), and the implication these novel estimates of stability on theory are investigated (`similarity-theory_dTdlnz.ipynb`).