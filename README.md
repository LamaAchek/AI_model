# Plant Watering Prediction AI Model

This project applies machine learning techniques to predict the amount of water a plant needs using environmental sensor data, including temperature, humidity, light intensity, and soil moisture. The project evaluates two models: a classification-based approach (Gaussian Naive Bayes) and a regression-based approach (Random Forest Regressor).

---

## 1. Dataset Overview

**Source:** `Data.xlsx`  
**Samples:** 1000 rows  
**Columns:**
- `year`, `month`, `day`, `hour`, `minute`, `second`
- `temp` (Temperature)
- `Humidity` (Humidity)
- `light` (Light intensity)
- `moisture` (Soil moisture)
- `water` (Water amount in mL)

**Features Used (X):**
- `temp`
- `Humidity`
- `light`
- `moisture`

**Target Variable (y):**
- `water`

---

## 2. Models Used

### Gaussian Naive Bayes (GNB)
- **Type:** Classification  
- **Train/Test Split:** `train_test_split` with `random_state=1`  
- **Training Accuracy:** 99.1%  
- **Testing Accuracy:** 91.6%  

### Random Forest Regressor

- **Type:** Regression  
- **Mean Squared Error (MSE):** 1.004  
- **Mean Absolute Error (MAE):** 0.184  
- **Observation:** Performs well overall but may produce unrealistic predictions under extreme moisture conditions.

---

### 3. Data Visualization

- **Pairplots:**  
  Show relationships between variables such as temperature, humidity, moisture, and water.

- **Linear Regression Plots:**  
  Plotted each feature against water using regression trendlines and correlation metrics.

- **Key Findings:**  
  - Strong negative correlation between moisture and water: -0.98  
  - Humidity negatively correlated with water: -0.82  
  - Temperature and light positively correlated with water

---

### 4. Evaluation Summary

| Metric                | GaussianNB (Classifier) | Random Forest (Regressor) |
|-----------------------|-------------------------|---------------------------|
| Accuracy (Test)       | 91.6%                   | N/A                       |
| Mean Squared Error    | 16.10                   | 1.00                      |
| Mean Absolute Error   | 0.58                    | 0.18                      |

- GaussianNB performs well for classification when moisture levels are within a normal range.  
- Random Forest offers more detailed predictions but struggles with extreme input values.

---

### 5. Setup Instructions

**Install Dependencies**  
```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
