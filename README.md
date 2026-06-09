# AI-ML-Task3-Model-Validation
Machine Learning project using the California Housing Dataset. Implemented feature scaling, Linear Regression, Ridge Regression, Decision Tree Regression, Cross Validation, Overfitting Analysis, and Hyperparameter Tuning using GridSearchCV.

<p align="center">
# 🏠 House Price Prediction using Machine Learning
### Model Validation, Overfitting Control & Hyperparameter Tuning

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)
</p>

## 📌 Project Overview

This project focuses on predicting California house prices using Machine Learning regression models. The objective was not only to achieve good prediction accuracy but also to evaluate model reliability through cross-validation, detect overfitting, and optimize model performance using hyperparameter tuning.

The California Housing Dataset from Scikit-Learn was used for this project.

---

## 🎯 Objectives

- Load and preprocess housing data
- Apply feature scaling using StandardScaler
- Train multiple regression models
- Detect overfitting using train vs test performance
- Validate model performance using Cross Validation
- Optimize Decision Tree using GridSearchCV
- Compare models using RMSE and R² Score
- Select the best-performing model

---

## 🛠 Technologies Used

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Scikit-Learn

---

## 📊 Dataset

**Dataset:** California Housing Dataset

**Target Variable:** Median House Value

### Features

- MedInc
- HouseAge
- AveRooms
- AveBedrms
- Population
- AveOccup
- Latitude
- Longitude

---

## ⚙️ Machine Learning Workflow

### 1. Data Preprocessing

- Feature Selection
- StandardScaler Normalization
- Train-Test Split (80:20)

### 2. Baseline Models

- Linear Regression
- Ridge Regression

### 3. Overfitting Analysis

- Decision Tree Regressor
- Train RMSE vs Test RMSE Comparison

### 4. Cross Validation

- 5-Fold Cross Validation
- Reliable Model Evaluation

### 5. Hyperparameter Tuning

- GridSearchCV
- Decision Tree Optimization

---

## 🔍 Overfitting Detection

### Initial Decision Tree Performance

| Metric | Value |
|----------|----------|
| Train RMSE | 3.218e-16 |
| Test RMSE | 0.7030 |

### Observation

The training RMSE was nearly zero while the testing RMSE was significantly higher.

This indicates severe overfitting because the model memorized the training data but did not generalize well to unseen data.

---

## 📈 Cross Validation Results

5-Fold Cross Validation Scores:

```text
[-0.78796899
 -0.68527964
 -0.80721441
 -0.89315807
 -0.84548406]
```

### Conclusion

The scores were relatively consistent across folds, indicating stable model performance.

---

## 🔧 Hyperparameter Tuning

### Parameter Grid

```python
param_grid = {
    "max_depth": [3, 5, 7, 10],
    "min_samples_split": [2, 5, 10]
}
```

### Best Parameters

```python
{
    'max_depth': 10,
    'min_samples_split': 10
}
```

These parameters reduced overfitting and improved generalization.

---

## 📊 Model Performance Comparison

| Model | RMSE | R² Score |
|---------|---------|---------|
| Linear Regression | 0.745581 | 0.575788 |
| Ridge Regression | 0.745554 | 0.575819 |
| Tuned Decision Tree | **0.645430** | **0.682099** |

---

## 🏆 Best Model

### Tuned Decision Tree Regressor

**Performance**

- RMSE = 0.645430
- R² Score = 0.682099

### Why It Was Selected

✅ Lowest RMSE

✅ Highest R² Score

✅ Reduced Overfitting

✅ Better Generalization

✅ Stable Cross Validation Performance

---

## 📷 Results

### RMSE Comparison

Add your chart here:

```text
images/rmse_comparison.png
```

### Overfitting Analysis

Add screenshot:

```text
images/overfitting_analysis.png
```

### Cross Validation

Add screenshot:

```text
images/cross_validation_results.png
```

---

## 📂 Project Structure

```text
House-Price-Prediction-Model-Validation
│
├── AI_ML_Task3_Model_Validation_Tuning.ipynb
├── Task3_Report.pdf
├── README.md
├── requirements.txt
│
└── images
    ├── rmse_comparison.png
    ├── overfitting_analysis.png
    └── cross_validation_results.png
```

---

## 🚀 How to Run

```bash
git clone https://github.com/00-Abhishek/House-Price-Prediction-Model-Validation.git

cd House-Price-Prediction-Model-Validation

pip install -r requirements.txt

jupyter notebook
```

Open:

```text
AI_ML_Task3_Model_Validation_Tuning.ipynb
```

and run all cells.

---

## 📚 Learning Outcomes

- Understanding Overfitting and Underfitting
- Model Validation Techniques
- Cross Validation
- Hyperparameter Tuning
- GridSearchCV
- Regression Evaluation Metrics
- Model Selection Strategies

---

## 👨‍💻 Author
<p align"center">
**Ayush Kumar Singh**
B.Tech Artificial Intelligence  
Amity University Lucknow
[GitHub](https://github.com/Ayush-2703) [LinkedIn](https://www.linkedin.com/in/ayushsingh2703)
</p>
---

## ⭐ Acknowledgements

- Scikit-Learn Documentation
- California Housing Dataset
- Maincrafts Technology AI & ML Internship Program
