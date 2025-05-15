Plant Watering Prediction AI Model
This project uses Machine Learning techniques to predict the amount of water a plant requires based on environmental sensor data like temperature, humidity, light, and soil moisture. Two ML models are evaluated: Gaussian Naive Bayes and Random Forest Regressor.

📁 Dataset
Source: Data.xlsx

Rows: 1000 samples

Columns:
year, month, day, hour, minute, second, temp, Humdity, light, moisture, water

Features Used (X):

temp (Temperature)

Humdity (Humidity)

light (Light intensity)

moisture (Soil moisture)

Target Variable (y):

water (Water amount in ml)

⚙️ Models Used
1. Gaussian Naive Bayes (GNB)
Purpose: Classification-based approach to estimate water need.

Train/Test Split: Used train_test_split with random_state=1

Accuracy:

Training Score: 0.991

Testing Score: 0.916

Prediction Examples:

python
Copy
Edit
Xnew = [[24,20,140,350]]
ynew = model.predict(Xnew)  # → [0]
2. Random Forest Regressor
Purpose: Regression-based prediction of water quantity.

Mean Squared Error (MSE): 1.004

Mean Absolute Error (MAE): 0.184

Note: Performs well but gives unrealistic predictions for extreme moisture values.

📊 Data Visualization
Pairplots: Displayed relationships between features like temp, humidity, moisture, and water.

Linear Regression Plots: Plotted each feature vs. water with trendlines and correlation metrics.

Findings:

Strong negative correlation between moisture and water (-0.98)

Humidity is negatively correlated with water (-0.82)

Temperature and light are positively correlated with water

🧮 Evaluation Metrics
Metric	GaussianNB	Random Forest
Accuracy (Test)	91.6%	N/A (regressor)
MSE	16.10	1.00
MAE	0.58	0.18

✅ GNB is more robust for classification when moisture values are within a normal range.
⚠️ Random Forest shows prediction issues with extreme moisture levels.

🔧 Setup Instructions
Install Dependencies

bash
Copy
Edit
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
Run the Code

Ensure Data.xlsx is in the same directory.

Execute the script in an environment like Jupyter Notebook or VS Code.

🚀 Future Improvements
Add moisture threshold normalization

Incorporate time-based trends

Hyperparameter tuning for Random Forest

Train with larger, more balanced dataset

📌 Note
This project is meant for educational and prototyping purposes. Predictions are model-based and should be validated against real-world experiments in smart agriculture settings.
