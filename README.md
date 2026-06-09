<div align="center">

# 🏠 House Price Prediction using Machine Learning

### Model Validation &nbsp;•&nbsp; Overfitting Control &nbsp;•&nbsp; Hyperparameter Tuning

<br>

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2ea44f?style=for-the-badge)

</div>

---

## 📌 Project Overview

This project focuses on predicting **California house prices** using Machine Learning regression models. The objective was not only to achieve good prediction accuracy but also to evaluate model reliability through **cross-validation**, detect **overfitting**, and optimize model performance using **hyperparameter tuning**.

> 🗂️ **Dataset Used:** California Housing Dataset from Scikit-Learn  
> 🎯 **Target Variable:** Median House Value

---

## 🎯 Objectives

- 📥 Load and preprocess housing data  
- ⚖️ Apply feature scaling using `StandardScaler`  
- 🤖 Train multiple regression models  
- 🔍 Detect overfitting using train vs test performance  
- 🔄 Validate model performance using Cross Validation  
- 🔧 Optimize Decision Tree using `GridSearchCV`  
- 📊 Compare models using RMSE and R² Score  
- 🏆 Select the best-performing model  

---

## 🛠️ Technologies Used

<div align="center">

| Technology | Purpose |
|:----------:|:-------:|
| 🐍 Python | Core Language |
| 📓 Jupyter Notebook | Development Environment |
| 🔢 NumPy | Numerical Computing |
| 🐼 Pandas | Data Manipulation |
| 📊 Matplotlib | Data Visualization |
| 🤖 Scikit-Learn | Machine Learning |

</div>

---

## 📊 Dataset

**Dataset:** California Housing Dataset &nbsp;&nbsp;|&nbsp;&nbsp; **Target Variable:** Median House Value

### 🔑 Feature Description

| Feature | Description |
|---------|-------------|
| `MedInc` | Median income in block group |
| `HouseAge` | Median house age in block group |
| `AveRooms` | Average number of rooms per household |
| `AveBedrms` | Average number of bedrooms per household |
| `Population` | Block group population |
| `AveOccup` | Average number of household members |
| `Latitude` | Block group latitude |
| `Longitude` | Block group longitude |

---

## ⚙️ Machine Learning Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   📥 Data Preprocessing                                        │
│      └── Feature Selection → StandardScaler → Train-Test Split  │
│                                                                 │
│   📈 Baseline Models                                           │
│      └── Linear Regression → Ridge Regression                   │
│                                                                 │
│   🔍 Overfitting Analysis                                      │
│      └── Decision Tree → Train RMSE vs Test RMSE                │
│                                                                 │
│   🔄 Cross Validation                                          │
│      └── 5-Fold Cross Validation → Reliable Evaluation          │
│                                                                 │
│   🔧 Hyperparameter Tuning                                     │
│      └── GridSearchCV → Best Decision Tree                      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 1️⃣ Data Preprocessing
- Feature selection from raw dataset
- Normalization using `StandardScaler`
- Train-Test Split with **80:20** ratio

### 2️⃣ Baseline Models
- **Linear Regression** — simple benchmark model
- **Ridge Regression** — adds L2 regularization to reduce variance

### 3️⃣ Overfitting Analysis
- **Decision Tree Regressor** trained without constraints
- Compared **Train RMSE** vs **Test RMSE** to detect overfitting

### 4️⃣ Cross Validation
- **5-Fold Cross Validation** for stable, unbiased evaluation
- Reduces sensitivity to train-test split randomness

### 5️⃣ Hyperparameter Tuning
- `GridSearchCV` to find the optimal Decision Tree parameters
- Balanced model complexity and generalization

---

## 🔍 Overfitting Detection

### ⚠️ Initial Decision Tree — Before Tuning

<div align="center">

| Metric | Value | Observation |
|:------:|:-----:|:-----------:|
| Train RMSE | `3.218e-16` | Nearly Zero → Memorized Training Data |
| Test RMSE | `0.7030` | High → Poor Generalization |

</div>

> ❗ **Conclusion:** The near-zero training RMSE alongside a significantly higher test RMSE confirms **severe overfitting** — the model memorized training data but failed to generalize to unseen samples.

---

## 📈 Cross Validation Results

**5-Fold Cross Validation Scores:**

```
Fold 1:  -0.78796899
Fold 2:  -0.68527964
Fold 3:  -0.80721441
Fold 4:  -0.89315807
Fold 5:  -0.84548406
```

> ✅ **Conclusion:** Scores are relatively consistent across all folds, indicating **stable and reliable model performance**.

---

## 🔧 Hyperparameter Tuning

### Parameter Grid Used

```python
param_grid = {
    "max_depth":        [3, 5, 7, 10],
    "min_samples_split": [2, 5, 10]
}
```

### ✅ Best Parameters Found

```python
{
    "max_depth":         10,
    "min_samples_split": 10
}
```

> These parameters **reduced overfitting** and significantly improved generalization on unseen data.

---

## 📊 Model Performance Comparison

<div align="center">

| Model | RMSE | R² Score | Verdict |
|:-----:|:----:|:--------:|:-------:|
| Linear Regression | 0.745581 | 0.575788 | Baseline |
| Ridge Regression | 0.745554 | 0.575819 | Marginal Improvement |
| ⭐ Tuned Decision Tree | **0.645430** | **0.682099** | **Best Model** |

</div>

---

## 🏆 Best Model — Tuned Decision Tree Regressor

<div align="center">

| Metric | Value |
|:------:|:-----:|
| 📉 RMSE | **0.645430** |
| 📈 R² Score | **0.682099** |

</div>

### Why It Was Selected

| ✅ Criterion | Detail |
|-------------|--------|
| 📉 Lowest RMSE | Outperformed all other models |
| 📈 Highest R² Score | Explains ~68% of target variance |
| 🛡️ Reduced Overfitting | Controlled via `max_depth` and `min_samples_split` |
| 🌐 Better Generalization | Strong performance on unseen test data |
| 🔄 Stable Cross Validation | Consistent scores across all 5 folds |

---

## 📷 Results & Visualizations

### 📉 RMSE Comparison
![RMSE Comparison](images/rmse_comparison.png)

### 🔍 Overfitting Analysis
![Overfitting Analysis](images/overfitting_analysis.png)

### 🔄 Cross Validation Results
![Cross Validation](images/cross_validation_results.png)

---

## 📂 Project Structure

```
House-Price-Prediction-Model-Validation/
│
├── 📓 AI_ML_Task3_Model_Validation_Tuning.ipynb   ← Main Notebook
├── 📄 Task3_Report.pdf                            ← Project Report
├── 📝 README.md                                   ← Documentation
├── 📦 requirements.txt                            ← Dependencies
│
└── 📁 images/
    ├── 📊 rmse_comparison.png
    ├── 🔍 overfitting_analysis.png
    └── 🔄 cross_validation_results.png
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/00-Abhishek/House-Price-Prediction-Model-Validation.git

# 2. Navigate into the project directory
cd House-Price-Prediction-Model-Validation

# 3. Install required dependencies
pip install -r requirements.txt

# 4. Launch Jupyter Notebook
jupyter notebook
```

Then open **`AI_ML_Task3_Model_Validation_Tuning.ipynb`** and run all cells.

---

## 📚 Learning Outcomes

| Concept | What Was Learned |
|---------|-----------------|
| 🔍 Overfitting & Underfitting | Identifying model behavior via train/test gap |
| 🔄 Cross Validation | Reliable evaluation beyond a single split |
| 🔧 Hyperparameter Tuning | Systematic search using `GridSearchCV` |
| 📊 Evaluation Metrics | RMSE and R² for regression tasks |
| 🤖 Model Selection | Choosing the best model based on evidence |

---

## 👨‍💻 Author

<div align="center">

### Ayush Kumar Singh

**B.Tech — Artificial Intelligence**  
Amity University, Lucknow

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ayush-2703)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ayushsingh2703)

</div>

---

## ⭐ Acknowledgements

- 📘 [Scikit-Learn Documentation](https://scikit-learn.org/)
- 🗂️ California Housing Dataset
- 🏢 **Maincrafts Technology** — AI & ML Internship Program

---

<div align="center">

*If you found this project helpful, consider giving it a ⭐ on GitHub!*

</div>
