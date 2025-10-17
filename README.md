# Static Code Vulnerability Detection using Machine Learning

This project explores the effectiveness of various machine learning and deep learning models for detecting vulnerable code snippets using static analysis. We perform a comparative study across traditional models and transformer-based embeddings to evaluate which approaches are most effective at identifying vulnerable C/C++ functions.

## Overview

Static code analysis is a crucial step in identifying software vulnerabilities early in the development lifecycle. Traditional tools often suffer from limited accuracy and high false positives. In this project, we evaluate ML and DL models—ranging from classical classifiers like SVM and Logistic Regression to semantic-rich embeddings from CodeBERT—to improve vulnerability detection in source code.

## Models Evaluated

### Feature Type: TF-IDF
- **Support Vector Machine (SVM)**
- **Logistic Regression**
- **Random Forest**
- **Multi-Layer Perceptron (MLP)**

### Feature Type: CodeBERT Embeddings
- **Logistic Regression**
- **MLP**

## Key Results

| Model              | Samples | Accuracy | F1-score (vulnerable class) |
|-------------------|---------|----------|------------------------------|
| TF-IDF + SVM      | 100K    | 0.80     | 0.49                         |
| TF-IDF + LR       | 100K    | 0.78     | 0.38                         |
| TF-IDF + RF       | 100K    | 0.85     | 0.19                         |
| TF-IDF + MLP      | 50K     | 0.82     | 0.33                         |
| CodeBERT + LR     | 10K     | 0.73     | 0.36                         |
| CodeBERT + MLP    | 50K     | 0.75     | 0.40                         |


## Dataset
The link to the github repository from where the dataset can be downloaded in .json format:
diversevul - https://github.com/wagner-group/diversevul

You can also download the dataset from the below link:
https://drive.google.com/file/d/12IWKhmLhq7qn5B_iXgn5YerOQtkH-6RG/view?usp=sharing


## Repository Structure
.
├── data/
│   └── data.txt                                        # Metadata / notes about dataset usage
│
├── Final Report/
│   └── CSCI_667_Final_Project_Report_Ahlaad_Y.pdf      # Final project report (academic submission)
│
├── models/                                             # (Reserved for trained model checkpoints or future work)
│
├── notebooks/
│   ├── 01_diversevul_svm.ipynb                         # SVM trained on DiverseVul dataset
│   ├── 02_logistic_regression_svm_comparison.ipynb     # SVM vs Logistic Regression comparison
│   ├── 03_random_forest.ipynb                          # Random Forest classifier implementation
│   ├── 04_MLP_Dense_Neural.ipynb                       # MLP experiments (TF-IDF features)
│   ├── 05_CodeBERT_LR.ipynb                            # CodeBERT + Logistic Regression experiments
│   └── 06_CodeBERT_MLP.ipynb                           # CodeBERT + MLP experiments and visualizations
│
├── results/
│   ├── output.png                                      # Model comparison visualization
│   └── output1.png                                     # Additional result chart
│
├── utils/                                              # (Reserved for helper functions or scripts)
│
├── .gitignore                                          # Ignore rules (dataset, cache, envs, etc.)
└── README.md                                           # Project documentation (this file)


# How to Run
## Clone the Repository:
    git clone https://github.com/ahlaady/static-code-vuln-detection.git
    cd static-code-vuln-detection

## Set Up the Environment:
It’s recommended to use a virtual environment (e.g., venv or conda):

## Using venv:
    python -m venv venv
    source venv/bin/activate        # On Mac/Linux
    venv\Scripts\activate           # On Windows

## Install dependencies
pip install -r requirements.txt

## Add the Dataset
Download the DiverseVul dataset (JSON format) and place it in the data/ directory:
    data/
    ├── data.txt
    └── diversevul_20230702.json            # Added dataset

## Explore the Notebooks
    jupyter notebook
Then open files from the notebooks/ directory to explore model training, evaluation, and visualizations.

## View Final Report
The complete report is available in:
    Final Report/
    └── CSCI_667_Final_Project_Report_Ahlaad_Y.pdf


## Future Work
Future work includes, but isn't limited to: TF-IDF + Stacked LSTM, CodeBERT + LSTM, CodeBERT + SVM, CodeBERT + RF, adversarial robustness