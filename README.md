# Machine Learning for CO₂ Emission Optimization in Delivery Logistics

## Overview

This project explores how machine learning can help identify delivery configurations with lower predicted CO₂ emissions.

Using a dataset of around 100,000 delivery records, we analyze the factors associated with emissions, train regression models, and use their predictions to compare possible delivery configurations under a travel-time constraint.

The project also examines the limitations of the dataset and how they affect the optimization results.

## Project Workflow

1. **Data preprocessing:** Check data quality, handle missing values and duplicates, and prepare features for modeling.
2. **Exploratory data analysis:** Explore the main variables, visualize their distributions, and investigate relationships between delivery characteristics and emissions.
3. **Machine learning:** Train and compare regression models using standard evaluation metrics.
4. **Optimization:** Search for delivery configurations with lower predicted emissions while respecting a travel-time limit.
5. **Evaluation:** Compare the proposed configurations with the original ones and examine how the results change under different constraints.

## Dataset

The project uses `logistics_co2_dataset.csv`, which contains approximately 100,000 records and 19 columns.

The dataset includes delivery distance, average speed, traffic, cargo weight, vehicle type, road type, weather conditions, travel time, and CO₂ emissions.

Some details, including the units of measurement and the meanings of certain category codes, are not provided. The analysis therefore takes these limitations into account when interpreting the results.

## Project Structure

```text
.
├── logistics_co2_dataset.csv
├── logistics_co2_optimization.ipynb
├── requirements.txt
└── README.md
```

## Getting Started

Clone the repository and install the required packages:

```bash
git clone <repository-url>
cd <repository-name>
pip install -r requirements.txt
```

Place `logistics_co2_dataset.csv` in the project folder, open the notebook in Jupyter or Google Colab, and run the cells in order.

## Tools

- Python
- Pandas and NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Limitations

The dataset does not provide alternative routes for the same delivery, detailed vehicle specifications, or emission units. Some variables also appear to follow simplified patterns, which raises questions about how closely the data represent real delivery operations.

For this reason, the optimization results are treated as model-based estimates rather than evidence of actual emission reductions.

## Objective

The goal is to study how predictive models can be used in a constrained optimization problem and to understand what the available data can, and cannot, tell us about lower-emission delivery decisions.