# ITAI 1371 Final Machine Learning Project

## Project Title
**HR Analytics Job Change Prediction**

## Student
**Huong Thi Hue Nguyen**

## Course
**ITAI 1371: Introduction to Machine Learning**

## Project Type
**Classification Problem**

## Project Objective
This project builds a machine learning classification model to predict whether a candidate is likely to look for a job change. The dataset contains HR analytics information such as education level, experience, company size, company type, training hours, and related employment features.

The goal is to compare multiple classification models, evaluate them using required classification metrics, and identify the model that performs best for predicting the target variable.

## Dataset
The dataset used in this project is:

**HR Analytics: Job Change of Data Scientists**

Dataset source:
https://www.kaggle.com/datasets/arashnic/hr-analytics-job-change-of-data-scientists

The main dataset file is included in this repository:

```text
data/raw/aug_train.csv
```

A dataset URL reference is also included here:

```text
data/raw/url.txt
```

## Repository Structure

```text
ITAI-1371_Final_ML_Project_ML_19179_3/
│
├── data/
│   ├── raw/
│   │   ├── aug_train.csv
│   │   ├── HR Analytics Job - Change of Data Scientists.zip
│   │   └── url.txt
│   │
│   └── processed/
│       ├── hr_jobchange_train_raw_split.csv
│       ├── hr_jobchange_validation_raw_split.csv
│       ├── hr_jobchange_test_raw_split.csv
│       ├── hr_jobchange_train_processed.csv
│       ├── hr_jobchange_validation_processed.csv
│       └── hr_jobchange_test_processed.csv
│
├── notebooks/
│   └── final_ml_project_hr_job_change.ipynb
│
├── ouput/
│   ├── all_model_metrics.csv
│   ├── combined_model_metrics.csv
│   ├── ensemble_metrics.csv
│   ├── bayesian_ensemble_coefficients.csv
│   ├── classification_report.txt
│   ├── best_model_confusion_matrix.csv
│   ├── best_model_confusion_matrix.png
│   ├── feature_importance.png
│   ├── gradient_boosting_top_feature_importance.csv
│   ├── test_f1_by_model.png
│   ├── validation_roc_auc_by_model.png
│   └── project_summary.json
│
├── report/
│   ├── model_comparison_table.pdf
│   └── final_project_model_report.pdf
│
├── presentation/
│   └── Presentation deck will be added separately
│
└── README.md
```

Note: The project folder currently uses the folder name `ouput`. This folder contains the model outputs, charts, tables, and saved metrics.

## Final Exam Requirement Coverage

### 1. Data Preprocessing
The notebook performs preprocessing and prepares the dataset for model training. It also creates the required split:

- Training set: 70%
- Validation set: 15%
- Test set: 15%

The split files are saved under:

```text
data/processed/
```

### 2. Required Classification Models
The notebook trains and compares the required classification models:

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier
- K-Nearest Neighbors Classifier
- Support Vector Classifier

### 3. Validation and Test Metrics
Each model is evaluated using the required classification metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

The comparison table is saved here:

```text
ouput/combined_model_metrics.csv
report/model_comparison_table.pdf
```

### 4. Ensemble Models
The notebook includes ensemble modeling using:

- Average Ensemble using the top 3 models
- BayesianRidge Probability Ensemble using the top 3 model prediction probabilities

Both ensemble methods are evaluated on the validation and test sets and compared against the individual models.

### 5. Report Deliverables
The project includes the required PDF report files:

```text
report/model_comparison_table.pdf
report/final_project_model_report.pdf
```

The report discusses the modeling approach, model comparison, best model selection, and why the selected model performed well.

## Summary of Results

Based on validation ROC-AUC, **Gradient Boosting** was selected as the strongest individual model. It performed well because it can capture non-linear patterns and interactions between HR features better than simpler linear models.

The ensemble models were also compared. The BayesianRidge Probability Ensemble achieved a strong test ROC-AUC, while Random Forest showed strong recall and F1 performance. Because the target class is imbalanced, ROC-AUC, recall, and F1 score are more meaningful than accuracy alone.

## How to Run the Notebook

1. Open the notebook:

```text
notebooks/final_ml_project_hr_job_change.ipynb
```

2. Make sure the dataset exists at:

```text
data/raw/aug_train.csv
```

3. Run all notebook cells from top to bottom.

4. Review generated outputs in:

```text
ouput/
report/
```

## Required Python Libraries

The notebook uses common Python machine learning libraries:

```text
pandas
numpy
scikit-learn
matplotlib
seaborn
joblib
```

If needed, install them with:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib
```

## Important Output Files

| File | Purpose |
|---|---|
| `notebooks/final_ml_project_hr_job_change.ipynb` | Main project notebook |
| `data/raw/aug_train.csv` | Original dataset |
| `data/processed/` | Train, validation, and test split files |
| `ouput/combined_model_metrics.csv` | Validation and test metrics for all models |
| `ouput/ensemble_metrics.csv` | Ensemble model performance |
| `ouput/classification_report.txt` | Classification report for the selected model |
| `ouput/best_model_confusion_matrix.png` | Confusion matrix visualization |
| `ouput/feature_importance.png` | Feature importance chart |
| `report/model_comparison_table.pdf` | PDF comparison table |
| `report/final_project_model_report.pdf` | Final written report |

## Presentation Note
The PowerPoint presentation will be updated separately. The final exam instruction requires a short presentation deck of 3 to 4 slides and a 5-minute walkthrough of the code and results.

## Submission Note
Canvas does not allow direct file uploads for this final exam. All deliverables should be submitted through GitHub, and the GitHub repository URL should be submitted in Canvas.
