# 🍷 Wine Quality Classification using Machine Learning

## 📌 Project Overview

This project is a complete **Machine Learning-based Wine Quality Classification application** designed to classify wine into two categories — **GOOD (1)** and **BAD (0)** — based on its physicochemical properties.

The project combines **Data Preprocessing, Exploratory Data Analysis, Feature Analysis, Machine Learning Model Comparison, Feature Scaling, Hyperparameter Tuning, Feature Importance Analysis, and an interactive CustomTkinter Graphical User Interface (GUI)** to provide a complete end-to-end Machine Learning solution.

The trained Machine Learning model takes multiple chemical properties of wine as input and predicts whether the wine belongs to the **GOOD** or **BAD** quality category.

---

## 🎯 Project Objective

The main objective of this project is to develop a Machine Learning classification model capable of identifying wine quality based on its chemical characteristics.

The project focuses on:

- Data loading and exploration
- Data preprocessing
- Exploratory Data Analysis (EDA)
- Missing-value analysis
- Correlation analysis
- Target variable transformation
- Train-test splitting
- Feature scaling
- Machine Learning model development
- Model evaluation
- Model comparison
- Hyperparameter tuning
- Feature importance analysis
- Confusion matrix analysis
- Real-time prediction
- CustomTkinter GUI development

---

## 📊 Dataset

The project uses the **Wine Quality Dataset**, which contains physicochemical properties of red wine samples along with their quality ratings.

The dataset contains **1,599 wine samples** and **11 input features**.

### 🧪 Wine Chemical Features

- Fixed Acidity
- Volatile Acidity
- Citric Acid
- Residual Sugar
- Chlorides
- Free Sulfur Dioxide
- Total Sulfur Dioxide
- Density
- pH
- Sulphates
- Alcohol

### 🎯 Target Variable

The original target variable is:

```text
quality
```

It was converted into a binary classification target:

```text
quality_label
```

### Target Transformation

```text
Quality >= 7
     ↓
GOOD (1)

Quality < 7
     ↓
BAD (0)
```

---

## 🔄 Machine Learning Pipeline

```text
Raw Dataset
      ↓
Data Loading
      ↓
Data Cleaning
      ↓
Exploratory Data Analysis
      ↓
Missing Value Analysis
      ↓
Correlation Analysis
      ↓
Target Transformation
      ↓
Feature & Target Separation
      ↓
Train-Test Split
      ↓
Logistic Regression
      ↓
Feature Scaling
      ↓
KNN
      ↓
Decision Tree
      ↓
Model Comparison
      ↓
GridSearchCV
      ↓
Final Decision Tree
      ↓
Feature Importance
      ↓
CustomTkinter GUI
      ↓
Real-Time Prediction
```

---

## 🔍 Exploratory Data Analysis

The following EDA techniques were performed:

- Dataset inspection
- Statistical analysis
- Missing-value analysis
- Target variable distribution
- Feature distribution
- Correlation analysis
- Feature importance analysis

### Important Correlations

| Feature | Correlation |
|:---|---:|
| Alcohol | 0.4762 |
| Sulphates | 0.2514 |
| Citric Acid | 0.2264 |
| Fixed Acidity | 0.1241 |
| Residual Sugar | 0.0137 |
| Free Sulfur Dioxide | -0.0507 |
| pH | -0.0577 |
| Chlorides | -0.1289 |
| Density | -0.1749 |
| Total Sulfur Dioxide | -0.1851 |
| Volatile Acidity | -0.3906 |

**Alcohol** showed the strongest positive correlation, while **Volatile Acidity** showed the strongest negative correlation with wine quality.

---

## ✂️ Train-Test Split

The dataset was divided into training and testing sets.

```text
Total Samples : 1599
Training Set  : 1279
Testing Set   : 320
```

---

# 🤖 Machine Learning Models

Three classification algorithms were implemented and compared:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree

Each model was evaluated using both scaled and unscaled data where applicable.

---

# 1️⃣ Logistic Regression

### Without Scaling

| Metric | Score |
|:---|---:|
| Accuracy | 89.38% |
| Precision | 73.68% |
| Recall | 32.56% |
| F1-Score | 45.16% |

### With Scaling

| Metric | Score |
|:---|---:|
| Accuracy | 89.38% |
| Precision | 69.57% |
| Recall | 37.21% |
| F1-Score | 48.48% |

---

# 2️⃣ K-Nearest Neighbors (KNN)

### Without Scaling

| Metric | Score |
|:---|---:|
| Accuracy | 85.94% |
| Precision | 45.45% |
| Recall | 23.26% |
| F1-Score | 30.77% |

### With Scaling

| Metric | Score |
|:---|---:|
| Accuracy | 89.38% |
| Precision | 66.67% |
| Recall | 41.86% |
| F1-Score | 51.43% |

---

# 3️⃣ Decision Tree

### Without Scaling

| Metric | Score |
|:---|---:|
| Accuracy | 90.00% |
| Precision | 61.70% |
| Recall | 67.44% |
| F1-Score | 64.44% |

### With Scaling

| Metric | Score |
|:---|---:|
| Accuracy | 90.62% |
| Precision | 63.83% |
| Recall | 69.77% |
| F1-Score | 66.67% |

---

# 📈 Complete Model Comparison

| Model | Scaling | Accuracy | Precision | Recall | F1-Score |
|:---|:---|---:|---:|---:|---:|
| Logistic Regression | Without Scaling | 89.38% | 73.68% | 32.56% | 45.16% |
| Logistic Regression | With Scaling | 89.38% | 69.57% | 37.21% | 48.48% |
| KNN | Without Scaling | 85.94% | 45.45% | 23.26% | 30.77% |
| KNN | With Scaling | 89.38% | 66.67% | 41.86% | 51.43% |
| Decision Tree | Without Scaling | 90.00% | 61.70% | 67.44% | 64.44% |
| **Decision Tree** | **With Scaling** | **90.62%** | **63.83%** | **69.77%** | **66.67%** |

---

# 🏆 Hyperparameter Tuning using GridSearchCV

After comparing the initial models, **Decision Tree** was selected for hyperparameter tuning.

### Best Parameters

```text
Criterion          : entropy
Max Depth          : None
Min Samples Leaf   : 1
Min Samples Split  : 2
```

### Best Cross-Validation F1-Score

```text
0.5255
```

---

# 📊 Final Model Performance

The tuned Decision Tree achieved:

| Metric | Score |
|:---|---:|
| **Accuracy** | **92.50%** |
| **Precision** | **73.17%** |
| **Recall** | **69.77%** |
| **F1-Score** | **71.43%** |

### Before vs After Tuning

| Metric | Original Decision Tree | Tuned Decision Tree |
|:---|---:|---:|
| Accuracy | 90.62% | **92.50%** |
| Precision | 63.83% | **73.17%** |
| Recall | 69.77% | **69.77%** |
| F1-Score | 66.67% | **71.43%** |

---

# 🔬 Feature Importance Analysis

Feature importance was calculated using the final tuned Decision Tree.

| Rank | Feature | Importance |
|---:|:---|---:|
| 1 | **Alcohol** | **0.2859** |
| 2 | Sulphates | 0.1017 |
| 3 | Volatile Acidity | 0.0973 |
| 4 | pH | 0.0866 |
| 5 | Total Sulfur Dioxide | 0.0789 |
| 6 | Chlorides | 0.0717 |
| 7 | Residual Sugar | 0.0714 |
| 8 | Citric Acid | 0.0614 |
| 9 | Free Sulfur Dioxide | 0.0581 |
| 10 | Density | 0.0533 |
| 11 | Fixed Acidity | 0.0338 |

**Alcohol** was the most important feature in the final model.

---

# 🖥️ CustomTkinter GUI

A modern desktop GUI was developed using **CustomTkinter**.

The GUI allows users to enter the chemical properties of wine and receive a real-time prediction.

### GUI Features

- 🍷 Modern Wine Quality Classification interface
- 🧪 11 wine feature input fields
- 🔍 Predict Wine Quality
- ✅ GOOD WINE classification
- ❌ BAD WINE classification
- ↻ Clear All functionality
- ⚠️ Input validation
- 🚨 Error handling
- 🎨 Modern CustomTkinter interface
- 📊 Prediction result display
- 🧠 Direct integration with the trained Decision Tree model

---

# 🧾 GUI Input Features

The application accepts:

```text
Fixed Acidity
Volatile Acidity
Citric Acid
Residual Sugar
Chlorides
Free Sulfur Dioxide
Total Sulfur Dioxide
Density
pH
Sulphates
Alcohol
```

---

# 🔮 Prediction Workflow

```text
User Input
     ↓
11 Wine Chemical Features
     ↓
DataFrame Creation
     ↓
Feature Alignment
     ↓
Tuned Decision Tree
     ↓
Prediction
     ↓
GOOD WINE / BAD WINE
```

Since the final model is a **Decision Tree**, the GUI directly uses the original feature values without applying StandardScaler.

---

# 🛠️ Technologies Used

| Technology | Purpose |
|:---|:---|
| Python | Programming Language |
| Pandas | Data Manipulation |
| NumPy | Numerical Computing |
| Matplotlib | Data Visualization |
| Seaborn | Statistical Visualization |
| Scikit-learn | Machine Learning |
| StandardScaler | Feature Scaling |
| GridSearchCV | Hyperparameter Tuning |
| Decision Tree | Final Classification Model |
| CustomTkinter | Modern GUI Development |
| Tkinter | Desktop GUI Framework |
| Jupyter Notebook | Development Environment |

---

# ⚙️ Installation

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn customtkinter joblib
```

---

# ▶️ How to Run

### Jupyter Notebook

1. Download or clone the repository.
2. Open the project folder.
3. Launch Jupyter Notebook.
4. Open `Wine_Quality_Classification.ipynb`.
5. Run the notebook cells from top to bottom.
6. Perform EDA and preprocessing.
7. Train the Machine Learning models.
8. Compare the models.
9. Perform GridSearchCV.
10. Run the CustomTkinter GUI.
11. Enter the wine feature values.
12. Click **Predict Wine Quality**.

### GUI

If the GUI is saved separately:

```bash
python wine_quality_gui.py
```

---

# 📚 Key Learning Outcomes

This project demonstrates practical implementation of:

- Data Cleaning
- Exploratory Data Analysis
- Statistical Analysis
- Correlation Analysis
- Feature Engineering
- Binary Classification
- Train-Test Split
- Logistic Regression
- KNN
- Decision Tree
- Feature Scaling
- Model Comparison
- Hyperparameter Tuning
- GridSearchCV
- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-Score
- Feature Importance
- Machine Learning Model Integration
- CustomTkinter GUI Development
- Real-Time Prediction

---

# 🔮 Future Improvements

Possible improvements include:

- Prediction probability/confidence score
- Prediction history
- Export results to CSV/Excel
- Dark/Light theme switch
- Advanced input validation
- Interactive charts
- Model performance dashboard
- Additional Machine Learning algorithms
- Cross-validation comparison
- Class imbalance handling
- Web deployment
- REST API integration

---

# 🏁 Final Conclusion

This project demonstrates a complete **end-to-end Machine Learning workflow** for Wine Quality Classification.

Multiple Machine Learning algorithms were trained and compared using Accuracy, Precision, Recall, and F1-Score. The **Decision Tree** achieved the best initial performance and was selected for hyperparameter tuning using **GridSearchCV**.

The final tuned Decision Tree achieved:

```text
Accuracy  : 92.50%
Precision : 73.17%
Recall    : 69.77%
F1-Score  : 71.43%
```

Feature importance analysis identified **Alcohol** as the most influential feature in the final model.

The trained model was then integrated with a modern **CustomTkinter GUI**, allowing users to enter wine chemical properties and receive real-time **GOOD WINE / BAD WINE** predictions.

---

# 👨‍💻 Developed By

## **Arjun Pal**


**Data Science & Machine Learning**

**Project:** Wine Quality Classification  
**Domain:** Data Science | Machine Learning | Predictive Analytics  
**Model:** Tuned Decision Tree Classifier  
**Interface:** CustomTkinter GUI  
**Development Environment:** Jupyter Notebook

---

⭐ **If you find this project useful, consider giving this repository a star!**
