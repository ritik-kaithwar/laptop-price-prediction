# Laptop Price Prediction — End-to-End Machine Learning Project  

## Project Highlights  
- Built a regression model to predict laptop prices from technical specs (CPU, GPU, RAM, storage, screen, weight, OS, brand).  
- Engineered structured features from raw text columns (CPU brand/series/speed, GPU brand/series, SSD vs HDD with sizes).  
- Compared multiple models: Linear Regression, Random Forest, Gradient Boosting, Decision Tree.  
- Best test performance: Gradient Boosting with **R² = 0.78**, RMSE ≈ 16,994, MAE ≈ 11,020.  
- 5-fold cross-validation (R² mean): Linear Regression 0.670, Random Forest 0.801, Gradient Boosting 0.832.  

---

## Overview  
The goal is to predict a laptop’s market price using its specifications. This project covers the full ML lifecycle: data cleaning, EDA, feature engineering, model training and evaluation, and a simple in-notebook prediction demo for new specs.  

---

## Dataset  
- **Source file**: `laptop.csv`  
- **Rows & Columns**: 1245 × 11 (after cleaning)  
- **Core Features**: Company, TypeName, Inches, ScreenResolution, Cpu, Ram, Memory, Gpu, OpSys, Weight  
- **Target Variable**: Price  

Data preprocessing included:  
- Dropping two unnamed columns and duplicates.  
- Handling missing values and inconsistent units.  
- Parsing CPU, GPU, and Memory into structured fields.  
- Encoding categorical features and scaling numeric features.  

---

## Feature Engineering  
- **CPU**: Extracted brand, series (i3/i5/i7, Ryzen, etc.), and speed (GHz).  
- **GPU**: Extracted brand and series.  
- **Memory**: Separated into SSD vs HDD with sizes.  
- **RAM & Weight**: Converted to numeric.  
- **Encoding**: One-hot encoding for categorical features.  
- **Scaling**: StandardScaler for numerical features (for linear models).  

---

## Exploratory Data Analysis (EDA)  
- Histograms, boxplots, and count plots for distributions and outliers.  
- Correlation heatmap showed strong relationships between price, RAM, CPU speed, and SSD storage.  
- Outlier filtering applied on numeric features.  

---

## Modeling Approach  
- **Train-test split**: 80:20  
- **Models Tested**:  
  - Linear Regression (with SelectKBest features)  
  - Random Forest  
  - Gradient Boosting  
  - Decision Tree  

### Model Evaluation  
- **Linear Regression**: R² = 0.74  
- **Random Forest**: R² = 0.72 | MAE ≈ 10,865 | RMSE ≈ 17,909  
- **Gradient Boosting**: R² = 0.78 | MAE ≈ 11,020 | RMSE ≈ 16,994  
- **Decision Tree**: R² = 0.58 | MAE ≈ 14,716 | RMSE ≈ 24,759  

### Cross-validation (5-fold, mean R²)  
- Linear Regression: 0.670  
- Random Forest: 0.801  
- Gradient Boosting: 0.832  

### Feature Importance (Tree Models)  
- RAM  
- SSD Size  
- CPU Speed & Series  
- GPU Brand/Series  
- Weight & TypeName  

---

## Key Insights  
- **RAM** capacity strongly influences price.  
- **SSD** configurations significantly increase price compared to HDD-only.  
- **CPU speed & series** are crucial in price prediction.  
- **GPU brand/series** matters in performance-based laptops.  
- **Weight & form factor** (Notebook, Gaming, Ultrabook) also drive segmentation.  

---

## How to Run  
1. Clone the repository.  
2. Install dependencies.
3. Open jupyter-notebook.ipynb and run all cells.  
4. The notebook includes a demo to test predictions for new laptop specs.  

---

## Recommendations

- Retrain the model periodically as new laptops are released.  
- Add additional features (release year, display type, refresh rate) to further improve accuracy.  
- Deploy as a simple Streamlit/Gradio app for interactive predictions.

---

## Author

**Ritik Kaithwar**
