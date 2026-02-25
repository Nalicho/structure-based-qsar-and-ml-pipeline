# QSAR and Machine Learning Workflow

## Overview

This repository provides a structured and reproducible computational pipeline for quantitative structure–activity relationship (QSAR) modelling. The workflow integrates:

- Bioactivity data curation  
- Molecular descriptor and fingerprint generation (PaDEL-Descriptor via `padelpy`)  
- Feature preprocessing and hybrid selection  
- Random Forest model development and hyperparameter optimisation  
- Internal and external validation  
- Y-randomisation testing  
- Applicability Domain (Williams plot) assessment  
- External library prediction and activity classification  

The notebooks are modular and executed sequentially to ensure transparency and reproducibility.

---

## Repository Structure


qsar-and-ml-workflow/
│
├── README.md
├── requirements.txt
│
├── data/
│ ├── raw/
│ └── processed/
│
├── config/ # PaDEL fingerprint XML files
├── figures/ # Exported validation plots
│
└── notebooks/
├── 01_Analogue_Library_Preparation.ipynb
├── 02_Bioactivity_Data_Curation.ipynb
├── 03_Descriptor_Generation.ipynb
└── 04_QSAR_Model_Development.ipynb


---

## Validation Strategy

Model performance is evaluated using:

- R² (training and test sets)  
- RMSE  
- Q²CV (10-fold cross-validation)  
- Q²Test and Q²Ext (predictive coefficients)  
- Y-randomisation testing  
- Applicability Domain analysis  

All preprocessing is fitted exclusively on training data to prevent data leakage.

---

## Installation

Python ≥ 3.9 recommended.

```bash
pip install -r requirements.txt

Note: Java (JRE 8 or later) is required for PaDEL-Descriptor.

Usage

Run notebooks in order:

Analogue library preparation

Bioactivity curation

Descriptor generation

QSAR modelling and validation

Outputs (models, figures, predictions) are saved in data/processed/ and figures/.

Acknowledgement

Parts of the descriptor workflow adapt the open-source PaDEL integration by Data Professor (MIT License), with modifications for structured QSAR modelling.

This repository represents a complete, reproducible QSAR modelling framework suitable for academic and research applications.
