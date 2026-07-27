# Professional Depression Classification

This project explores the **Professional Depression Dataset** and compares several
machine learning models for classifying depression-related outcomes. It includes
data inspection, exploratory data analysis, preprocessing, model evaluation, risk
stratification, and feature interpretation.

## Project Overview

The notebook:

- Downloads the dataset directly from Kaggle with `kagglehub`
- Checks missing values, duplicate records, feature types, and class distribution
- Explores relationships between depression and selected personal or professional factors
- Preprocesses numerical and categorical features with a scikit-learn pipeline
- Trains and compares three classification models
- Groups model probabilities into low, medium, and high risk categories
- Examines Logistic Regression coefficients for model interpretation

## Dataset

The project uses the
[Professional Depression Dataset](https://www.kaggle.com/datasets/aizahzeeshan/professional-depression-dataset)
published on Kaggle.

The dataset is downloaded at runtime, so it is not included in this repository.
Please review the dataset page for its description, provenance, and applicable
terms of use.

## Models

The following models are evaluated:

- Logistic Regression
- Random Forest
- Histogram-based Gradient Boosting

## Results

Performance on the notebook's stratified 20% test split:

| Model | Accuracy | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.988 | 1.000 | 0.878 | 0.935 |
| HistGradientBoosting | 0.971 | 0.968 | 0.732 | 0.833 |
| Random Forest | 0.949 | 1.000 | 0.488 | 0.656 |

Logistic Regression achieved the strongest overall F1 score and was selected for
the notebook's probability-based risk stratification. These values reflect one
train-test split with `random_state=42` and should not be interpreted as evidence
of clinical validity or generalization to other populations.

## Technologies

- Python
- pandas and NumPy
- scikit-learn
- Matplotlib and seaborn
- KaggleHub
- Jupyter Notebook / Google Colab

## Running the Project

1. Clone the repository:

   ```bash
   git clone https://github.com/aybikecan/professional-depression-classification.git
   cd professional-depression-classification
   ```

2. Install the required packages:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn "kagglehub[pandas-datasets]"
   ```

3. Open `Professional_Depression_Classification.ipynb` in Jupyter Notebook or
   Google Colab and run the cells in order.

Kaggle authentication may be required depending on the environment and Kaggle's
current access requirements.

## Repository Structure

```text
professional-depression-classification/
├── Professional_Depression_Classification.ipynb
└── README.md
```

## Limitations and Responsible Use

This project is for **educational and exploratory purposes only**. It is not a
medical diagnostic tool and must not be used for clinical decisions, screening,
treatment, or assessment of any individual.

The model is trained on a third-party dataset and may reflect sampling limitations,
biases, self-reported information, or other data-quality constraints. The reported
metrics are based on a single holdout split rather than external validation.

