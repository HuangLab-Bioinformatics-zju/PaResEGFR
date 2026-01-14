# Mapping EGFR Variants of Pathogenicity and Drug Resistance in NSCLC via a Dual Function Perturbation-Informed Protein Language Model

[![Project Website](https://img.shields.io/badge/Project-Website-blue)](https://github.com/HuangLab-Bioinformatics-zju/PaResEGFR)


## Introduction
PaResEGFR: a lightweight, EGFR-specific dual model that simultaneously scores variant pathogenicity and predicts afatinib/osimertinib resistance across the exon 18-24 saturation landscape in NSCLC, validated in cells and patients.
<p align="center">
<img src="./figures/model framework.png" alt="The framework" style="width:20cm; height:auto;"/>
</p>
<details open><summary><b>Table of contents</b></summary>

- [PaResEGFR-Model](#PaResEGFR-Model)
  - [Data](#data)
  - [Model Weights and Usage](#Usage)
  - [Example](#Example)
- [Citations](#citations)
- [License](#license)
</details>


## PaResEGFR-Model <a name="PaResEGFR-Model"></a>
### Data <a name="data"></a>

This repository contains the data and model for predicting the pathogenicity and drug resistance score of PaResEGFR variants using a our gene-specific protein language model, PaResEGFR.
The datasets used for training and evaluating the model are provided"[datas/train_dataset](datas/train_dataset.csv)".
We have conducted saturation mutagenesis on the EGFR sequence using the fine-tuned PaResEGFR. The results of this analysis are included in this repository"[.datas/EGFR_mutagenesis_predictions](datas/EGFR_mutagenesis_predictions.csv)".

### Model Weights and Usage <a name="Usage"></a>
To utilize the PaResEGFR model for predicting the pathogenicity and drug resistance score of EGFR variants, you will first need to obtain the model weights and follow the steps below to run the model.
<pre>
#Clone the Repository
git clone https://github.com/HuangLab-Bioinformatics-zju/PaResEGFR.git

# Create the PaResEGFR environment
conda create --name PaResEGFR python=3.11

# Activate the environment
conda activate PaResEGFR

# Install the pip packages
pip install -r requirements.txt    
# You can add the other pip packages from the dyna.yml file one by one if needed
python score.py --checkpoint_path "./PaResEGFR" --input_path './datas/example_pre_data.csv' --output_path './datas/example_outcome.csv'
#You may substitute the prediction data with your own CSV file

</pre>
