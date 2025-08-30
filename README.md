# Concrete Mix 7-Day Strength Prediction using Machine Learning

This project focuses on predicting the **7-day compressive strength of concrete** based on its mix design parameters.  
It uses a **real-world dataset of 2,286 concrete mix records** and applies a **leakage-safe Machine Learning pipeline** for accurate and reliable predictions.

---

## 📊 Dataset
- **Size:** 2,286 records, 20+ features  
- **Features include:**
  - Cement content (kg/m³)  
  - Water–Cement (W/C) ratio  
  - Water content  
  - Fine and coarse aggregates  
  - Admixture type & dosage  
  - Workability slump (mm)  
  - Hardened concrete density  
  - Aggregate gradation (% passing sieve)  
- **Target variable:**  
  - **7-day compressive strength (MPa)**  
- Note: 28-day strength was excluded due to ~1200 missing values.

---

## ⚙️ Methodology
1. **Data Preprocessing**
   - Handled missing values and cleaned admixture fields  
   - Encoded categorical variables (aggregate/admixture types)  
   - Scaled numerical features for uniformity  
   - Performed **train / validation / test split** (60/20/20) with input range checks  

2. **Modeling**
   - Evaluated multiple ML models:
     - Ridge Regression  
     - Gradient Boosting  
     - Random Forest  
   - Performed 5-fold Cross-Validation on training data  
   - Selected **Random Forest** as the best model  

3. **Deployment Utility**
   - Built a function `predict_csv()` that:
     - Accepts new concrete mix designs in CSV format  
     - Automatically preprocesses data  
     - Outputs 7-day strength predictions with residual diagnostics  

---

## 📈 Results
- **Model Comparison (Cross-Validation R²):**
  - Ridge: **0.25** (poor performance)  
  - Gradient Boosting: **0.64**  
  - Random Forest: **0.74 ± 0.06** (best)  

- **Final Random Forest Performance:**
  - Validation (20% split): **R² = 0.76**, MAE = 1.49, RMSE = 3.25  
  - Test (20% split): **R² = 0.918**, MAE = 0.89, RMSE = 1.72  

---

## 📊 Visual Insights
- Residual diagnostics show centered and normally distributed errors  
- Predictions vs. actual plots indicate strong alignment on validation and test sets  
- Random Forest consistently outperformed Ridge and Gradient Boosting across folds  

---

## 🚀 Features of This Project
- End-to-end leakage-safe ML pipeline  
- Deployment-ready prediction utility (`predict_csv`)  
- Handles raw input data and outputs predictions in CSV format  
- Includes residual diagnostics for model performance evaluation  
