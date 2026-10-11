# Machine Learning for Sustainable Delivery Logistics

A machine learning project that predicts CO₂ emissions from delivery operations and explores how delivery decisions can be optimized to reduce predicted emissions while respecting travel-time constraints.

## Overview

Delivery operations involve several decisions, including vehicle selection, road type, departure time, and driving speed. These choices can affect both travel time and fuel-related emissions.

This project uses machine learning to estimate delivery CO₂ emissions and investigate how different operational decisions may reduce them without significantly increasing travel time.

The project combines predictive modeling, exploratory data analysis, and constrained optimization.

## Objectives

- Analyze the factors associated with delivery CO₂ emissions.
- Train and compare regression models to predict emissions.
- Identify the most influential input features.
- Optimize delivery configurations while respecting a travel-time constraint.
- Evaluate how sensitive the proposed decisions are to changes in traffic, distance, cargo, and available time.

## Methodology

### 1. Data exploration and preparation

The dataset is examined for missing values, duplicates, unusual values, and relationships between variables. Additional features are created where useful, including cyclic representations of departure time and interaction features.

### 2. Machine learning

Several regression models are compared using a training, validation, and test split:

- Dummy Regressor as a baseline
- Ridge Regression
- Ridge Regression with interaction features
- Random Forest Regressor
- HistGradientBoosting Regressor

Models are evaluated using **MAE**, **RMSE**, and **R²**. The validation set is used for model selection, while the test set is reserved for final evaluation.

### 3. Feature analysis

Feature relationships and model behavior are examined using correlation analysis, visualizations, model diagnostics, and permutation importance.

The analysis also investigates potential data leakage and whether the dataset's emission values follow a simple mathematical relationship.

### 4. Constrained optimization

The project explores two optimization approaches.

**Delivery configuration optimization**

Candidate vehicle types, road types, departure hours, and driving speeds are evaluated to find configurations with lower predicted emissions, subject to a limit on travel-time increases.

**Traffic and route scenarios**

Hypothetical traffic reductions and route detours are evaluated to investigate when a longer route might be worthwhile under the selected emission and travel-time objectives.

The proposed decisions are also checked for sensitivity to different constraints and evaluated using an alternative predictive model.

## Dataset

The project uses `logistics_co2_dataset.csv`, containing approximately 100,000 delivery records.

The dataset includes variables related to delivery distance, vehicle and road types, traffic, departure time, cargo, travel time, and CO₂ emissions.

Some dataset details require caution: the emission units and cargo-weight units are not specified, and the meanings of certain categorical codes are unclear. The data also appears to contain generated relationships between variables, which are investigated during the analysis.

## Repository Structure

```text
green-logistics-co2-predictor/
├── data/
│   └── logistics_co2_dataset.csv
├── notebook/
│   └── green-logistics-co2-predictor.ipynb
├── README.md
└── requirements.txt
```

## Getting Started

### Requirements

- Python 3.10 or later
- Jupyter Notebook or JupyterLab

### Installation

Clone the repository:

```bash
git clone https://github.com/noursouabni/green-logistics-co2-predictor.git
cd green-logistics-co2-predictor
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Launch JupyterLab:

```bash
jupyter lab
```

Open the notebook in the `notebook/` directory and run the cells in order.

Make sure the dataset path in the notebook points to:

```python
DATA_PATH = Path("data/logistics_co2_dataset.csv")
```

This path assumes the notebook is launched from the repository root. If you run it from another directory, adjust the path accordingly.

## Limitations

- The dataset is synthetic
- Optimization results are model predictions! not measured emission reductions
- A model-based optimizer can exploit prediction errors, so proposed configurations should be validated before practical use. (ofc)

The goal is therefore to explore how machine learning can support delivery optimization (not real-world savings)
## Technologies

Python · pandas · NumPy · scikit-learn · Matplotlib · Jupyter Notebook

## Author

Nour Souabni

Master's student in Artificial Intelligence, Data & Agentic Systems at Paris Dauphine-PSL.
