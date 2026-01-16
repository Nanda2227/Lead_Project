# Lead Scoring & Prediction Pipeline

## Overview
This project builds an end-to-end **machine learning pipeline for lead scoring and categorization**. Using historical customer lead data, the model predicts the likelihood of conversion and assigns each lead a **score from 0–100**, which is then mapped into actionable business categories such as **Hot, Warm, and Cold** leads.

The project focuses not only on prediction accuracy, but also on **practical business usefulness**, including threshold optimization to ensure high conversion rates among prioritized leads.

---

## Project Objectives
- Clean and prepare real-world lead data with missing and inconsistent values
- Perform exploratory data analysis (EDA) and data quality checks
- Train and evaluate a classification model for lead conversion
- Generate interpretable **lead scores** and **lead categories**
- Optimize decision thresholds to improve business outcomes

---

## Dataset
- **Source**: `Leads.csv`
- **Target Variable**: `Converted` (binary: 0 = not converted, 1 = converted)
- **Features**: Mix of categorical and numerical customer attributes

### Data Challenges Addressed
- Missing values in both categorical and numerical features
- Placeholder values such as `'Select'` in categorical columns
- Duplicate records

---

## Workflow

### 1. Data Loading & Exploration
- Dataset inspection (shape, data types, sample rows)
- Missing value analysis and visualization

### 2. Data Cleaning & Preprocessing
- Replacement of invalid categorical values (`'Select' → NaN`)
- Duplicate removal
- Missing value imputation:
  - Categorical features → mode
  - Numerical features → median
- Encoding of categorical variables
- Feature scaling

### 3. Model Training
- Model type: **Logistic Regression**
- Train-test split applied
- Model trained to predict lead conversion probability

### 4. Model Evaluation
- Accuracy score
- Classification report (precision, recall, F1-score)
- ROC-AUC evaluation

### 5. Lead Scoring & Categorization
- Predicted probabilities converted to **Lead Scores (0–100)**
- Initial categorization:
  - **Hot**: score ≥ 80
  - **Warm**: score 50–79
  - **Cold**: score < 50

### 6. Threshold Optimization
- Optimized score threshold to achieve ~80% conversion rate among **Hot leads**
- Updated lead categories based on optimized threshold

---

## Results & Insights
- The model successfully differentiates high-intent leads from low-intent ones
- **Hot leads** show significantly higher actual conversion rates
- Threshold tuning improves business relevance beyond raw model accuracy

This approach enables sales teams to:
- Prioritize high-value leads
- Reduce time spent on low-probability prospects
- Align ML outputs with real-world conversion goals

---

## Visualizations
The notebook includes:
- Missing value heatmaps
- Lead score distribution plots
- Category-wise conversion analysis

---

## Installation
Install required dependencies:

```bash
pip install numpy pandas matplotlib seaborn missingno scikit-learn
```

> Note: The notebook uses `google.colab` utilities for file upload when run in Google Colab.

---

## Usage
1. Upload or place `Leads.csv` in the working directory
2. Open `Lead_Project.ipynb`
3. Run cells sequentially
4. Review generated lead scores and categories

---

## Future Improvements
- Try tree-based models (Random Forest, XGBoost)
- Hyperparameter tuning
- Feature importance analysis
- Deploy as a web application or API
- Automate data ingestion and scoring

---

## Author
**[Your Name]**

If you have feedback or suggestions, feel free to open an issue or submit a pull request.

