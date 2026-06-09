<h1 align="center">Metro Interstate Traffic Prediction</h1>

<p align="center">
  Machine Learning project for traffic volume forecasting and congestion classification using weather, temporal, and historical traffic data.
</p>

<h2>Project Overview</h2>

<p>
This project analyzes the <b>Metro Interstate Traffic Volume Dataset</b> and builds machine learning models to:
</p>

<ul>
  <li>Predict future traffic volume (Regression)</li>
  <li>Classify traffic congestion levels (Classification)</li>
  <li>Identify the most influential factors affecting traffic flow</li>
  <li>Compare multiple machine learning approaches</li>
</ul>

<p>
The project follows a complete machine learning pipeline including
data cleaning, exploratory data analysis (EDA), feature engineering,
model training, evaluation, and interpretation.
</p>

<h2>Dataset</h2>

<p>
Dataset: Metro Interstate Traffic Volume Dataset
</p>

<ul>
  <li>48,204 traffic observations</li>
  <li>Weather conditions</li>
  <li>Temperature, rain, snow, cloud coverage</li>
  <li>Date and time information</li>
  <li>Traffic volume measurements</li>
</ul>


<h2>Exploratory Data Analysis</h2>

<p>
Several insights were discovered during EDA:
</p>

<ul>
  <li>Traffic volume strongly depends on hour of the day</li>
  <li>Weekdays experience significantly more traffic than weekends</li>
  <li>Peak traffic occurs during commuting hours</li>
  <li>Friday shows the highest average traffic volume</li>
  <li>Temperature has a weak positive relationship with traffic volume</li>
  <li>Weather conditions have limited influence compared to temporal features</li>
</ul>

<h2>Feature Engineering</h2>

<p>
To improve predictive performance, several engineered features were created:
</p>

<ul>
  <li>Hour of day</li>
  <li>Day of week</li>
  <li>Month and year</li>
  <li>Weekend indicator</li>
  <li>1-hour traffic lag</li>
  <li>6-hour traffic lag</li>
  <li>24-hour traffic lag</li>
  <li>24-hour rolling mean</li>
  <li>24-hour rolling standard deviation</li>
  <li>Cyclical hour encoding (sin/cos)</li>
  <li>Weather one-hot encoding</li>
</ul>

<hr>

<h2>Regression Models</h2>

<p>
Objective: Predict exact traffic volume.
</p>

<table>
  <tr>
    <th>Model</th>
    <th>MAE</th>
    <th>RMSE</th>
    <th>R² Score</th>
  </tr>
  <tr>
    <td>Mean Predictor</td>
    <td>1723</td>
    <td>1968</td>
    <td>0.00</td>
  </tr>
  <tr>
    <td>Linear Regression</td>
    <td>434</td>
    <td>608</td>
    <td>0.905</td>
  </tr>
  <tr>
    <td>Random Forest Regressor</td>
    <td>150.6</td>
    <td>235.1</td>
    <td>0.9857</td>
  </tr>
  <tr>
    <td>XGBoost Regressor</td>
    <td>151.1</td>
    <td>232.3</td>
    <td>0.9861</td>
  </tr>
</table>

<p>
Best Regression Model: <b>XGBoost Regressor</b>
</p>

<hr>

<h2>Traffic Congestion Classification</h2>

<p>
Traffic volume was converted into four congestion categories using quartile-based segmentation:
</p>

<ul>
  <li>Low</li>
  <li>Medium</li>
  <li>High</li>
  <li>Critical</li>
</ul>

<p>
Random Forest Classifier achieved:
</p>

<ul>
  <li><b>Accuracy:</b> 93%</li>
  <li><b>Macro F1 Score:</b> 0.93</li>
  <li><b>Weighted F1 Score:</b> 0.93</li>
</ul>

<p>
The confusion matrix revealed that most errors occurred between adjacent congestion levels, while severe misclassifications were extremely rare.
</p>

<hr>

<h2>Key Findings</h2>

<ul>
  <li>Historical traffic volume is the strongest predictor of future traffic.</li>
  <li>1-hour lag traffic contributed nearly 73% of total feature importance.</li>
  <li>Time-related features outperform weather-related features.</li>
  <li>Feature engineering contributed more to performance gains than model complexity.</li>
  <li>Traffic forecasting can be performed with high accuracy using engineered temporal features.</li>
</ul>

<h2>Tech Stack</h2>

<p align="left">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge">
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white">
  <img src="https://img.shields.io/badge/XGBoost-AA4A44?style=for-the-badge">
</p>
