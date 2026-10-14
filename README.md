# Machine Learning for Predicting Sediment Particle Size Distributions

## Project Overview

This project uses machine learning techniques to predict sediment particle-size characteristics from environmental and water-quality measurements. Sediment particle-size distributions are important for understanding sediment transport and aquatic environments.

The project follows a **Reproduce and Extend** approach. It compares the results of existing machine learning models with the results obtained in this project and evaluates an additional model.

The main target variables are:

- **d50:** Median sediment particle diameter.
- **σ²:** Variance of the sediment particle-size distribution, as defined in the dataset and reference study.

## Objectives

- To study the application of machine learning in sediment particle-size prediction.
- To implement and evaluate Random Forest and Support Vector Regression (SVR).
- To extend the comparison using XGBoost.
- To evaluate the models using the coefficient of determination (R²).
- To compare project results with the reference study and identify possible differences.

## Machine Learning Models

### 1. Random Forest (RF)
Random Forest combines multiple decision trees to make predictions. It can capture nonlinear relationships between input variables and target values.

### 2. Support Vector Regression (SVR)
SVR is a regression algorithm that attempts to predict continuous values by finding a suitable function within a defined error tolerance.

### 3. XGBoost
XGBoost is a gradient-boosting algorithm that builds decision trees sequentially to improve prediction performance. It is used as the additional model in this project.

## Dataset and Features

The project uses a reconstructed or closest-available dataset prepared for this mini-project. The original reference study describes 1,648 observations from South San Francisco Bay. The available project dataset should be verified before claiming that it exactly matches the original dataset.

The reference feature list includes:

| Feature | Description |
|---|---|
| S | Salinity |
| ub | Near-bed orbital velocity or the source-defined variable |
| np | Variable defined in the reference dataset |
| T | Temperature |
| a676/a650 | Ratio of optical measurements at 676 nm and 650 nm |
| chlorophyll-a | Chlorophyll-a concentration |
| a450/a676 | Ratio of optical measurements at 450 nm and 676 nm |
| u | Velocity variable defined in the source |

The reference workflow selected S, ub, np, and T as input features. Their definitions and units should be verified against the original paper and the dataset.

## Methodology

The project follows these steps:

1. Load the dataset.
2. Inspect the data structure and identify missing values.
3. Clean the data and handle missing values.
4. Select input features and target variables.
5. Divide the dataset into training and testing sets.
6. Train the Random Forest, SVR, and XGBoost models.
7. Evaluate the models using R².
8. Compare project results with the reference results.
9. Discuss the findings and limitations.

The exact preprocessing methods, train-test split, and model parameters should be taken from the final project notebook.

## Results and Comparison

The following are the recorded project results. Verify them against the final notebook before submission.

| Model | Reference R² (d50) | Reference R² (σ²) | Project R² (d50) | Project R² (σ²) |
|---|---:|---:|---:|---:|
| Random Forest | 0.81 | 0.75 | 0.900 | 0.764 |
| SVR | 0.76 | 0.76 | 0.885 | 0.747 |
| XGBoost | Not reported | Not reported | 0.899 | 0.762 |

XGBoost is included as the additional model for extending the reference study.

Differences between the reference and project results may arise from differences in datasets, preprocessing, feature selection, train-test splits, random seeds, and model parameters. These results should not be described as an exact reproduction unless the original dataset and experimental setup have been verified.

## Understanding R²

R², or the coefficient of determination, measures how well a regression model explains the variation in the target variable.

- An R² value closer to 1 generally indicates a better fit on the evaluated data.
- An R² value near 0 indicates that the model explains little of the target variation relative to a mean-based baseline.
- R² can be negative when the model performs worse than that baseline.

Model scores should be evaluated on the intended test data and compared using consistent evaluation procedures.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Jupyter Notebook
- Google Colab
- Matplotlib and Seaborn, if used for visualization
- Git and GitHub for version control

## Project Structure

A suggested repository structure is:

```text
sediment-particle-size-ml/
├── README.md
├── data/
│   └── sediment_dataset.csv
├── notebooks/
│   └── sediment_particle_size_ml.ipynb
├── src/
│   └── Python scripts (optional)
└── requirements.txt
```

Update the filenames and folders to match the actual repository.

## Installation and Execution

### Option 1: Google Colab

1. Upload the project notebook to Google Colab.
2. Upload the dataset or connect the storage location used by the notebook.
3. Verify the dataset path in the code.
4. Execute the notebook cells in order.
5. Review the evaluation metrics and comparison tables.

### Option 2: Run Locally

Clone the repository:

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
cd <YOUR-REPOSITORY-FOLDER>
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install the required libraries:

```bash
pip install pandas numpy scikit-learn xgboost jupyter matplotlib seaborn
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open the project notebook and run the cells in sequence.

If the repository contains a `requirements.txt` file, install dependencies using:

```bash
pip install -r requirements.txt
```

## Reproducibility Checklist

- Verify the dataset source and number of observations.
- Document missing-value handling and feature selection.
- Record the training and testing split.
- Record the model parameters and random seeds.
- Confirm that metrics are calculated on the intended evaluation data.
- Verify that the reported scores match the final notebook.
- Explain differences from the reference study.

## Limitations

- The available dataset may differ from the original research dataset.
- Model performance depends on the quality and representativeness of the data.
- Different preprocessing and evaluation procedures can produce different results.
- A high R² score on one test split does not guarantee good generalization to new environments.
- Feature definitions, units, and target-variable definitions must be verified against the source.

## Conclusion

This project demonstrates how machine learning can be used to predict sediment particle-size characteristics. Random Forest and SVR provide baseline comparisons, while XGBoost extends the evaluation with an additional model. Comparing results with the reference study helps assess model performance and highlights the importance of consistent datasets and experimental procedures.

## References

Add the complete citation and link for the reference research paper and the actual dataset source used in the project.

Do not claim that the reconstructed dataset is the original research dataset unless this has been verified.

## License

No license has been specified for this project. Add an appropriate license if the project authors decide to publish the code and data under one.
