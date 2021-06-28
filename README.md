# BayesianGLM_stability

Distributed Temperature Sensing offers an unprecendented view into the vertical structure of the boundary layer. Some initial investigations into this are presented in this repository. If you have trouble viewing the notebook through github's interface, you can use the [nbviewer portal](https://nbviewer.jupyter.org/) to render the notebook.

## Data Preparation

All of the data used in this study come from the Large-eddy Observatory, Voitsumra Experiment 2019 (LOVE19). They are available through Zenodo (doi: 10.5281/zenodo.4312976). They are not included in the repository due to their size.

The data preparation notebooks contain all of the data munging for this mini-experiment, especially for creating homogeneous potential tempreature data for comparing across the entire LOVE19 column.

[data-prep/data-prep_homogenizing-potential-temp_data.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/data-prep/data-prep_homogenizing-potential-temp_data.ipynb): Converts all surface temperature observations to potential temperature, including conversions from CSAT sonic temperature to potential temperature.

[data-prep/data-prep_sodar.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/data-prep/data-prep_sodar.ipynb): Data preparation for converting the SODAR sonic temperature to potential temperature. The various assumptions for deriving this thermodynamic quantitiy are explored. The entire LOVE19 "column" of observations is also evaluated.

## stability

In these scripts I demonstrate some of the powerful advantages of DTS's unique ability to describe the vertical gradient temperature in detail.

### Bayesian modeling of stability

[stability/bayesian-GLM_estimate-dTdz.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/stability/bayesian-GLM_estimate-dTdz.ipynb): Stability is estimated for the first time using DTS following a Bayesian Generalized Linear Modeling Approach. Various prior assumptions are explored before concluding that assuming the errors in DTS temperature are distributed following a Student's t-distribution and modeling the stability for the entire LOVE19 campaign using this Bayes GLM approach.

[stability/evaluate_dTdlnz.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/stability/evaluate_dTdlnz.ipynb): After deriving stability, it is evaluated. When combined with a Bayesian Generalized Linear Model, stability appears to be better described than when using point observations and/or traditional linear fitting methods. Intriguingly, the largest disagreements occur during very stable conditions.

[stability/similarity-theory_dTdlnz.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/stability/similarity-theory_dTdlnz.ipynb): The implication of these novel estimates of stability on theory are investigated by comparing Similarity Theory theoretical values derived from the CSATs to the actual values derived from the DTS profile and Bayesian modeling. A further proof-of-concept is completed showing how it may be possible to directly model Similarity Theory using DTS profiles.

### PCA/dimension reduction

[stability/evaluate_DTS-CSAT-tair.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/stability/evaluate_DTS-CSAT-tair.ipynb): The CSAT and DTS air temperature biases are investigated using a PCA/clustering approach.

[stability/investigate_dTdlnz.ipynb](https://nbviewer.jupyter.org/github/klapo/BayesianGLM_stability/blob/main/notebooks/stability/investigate_dTdlnz.ipynb): T factors that control stability are investigated using a PCA/clustering approach.
