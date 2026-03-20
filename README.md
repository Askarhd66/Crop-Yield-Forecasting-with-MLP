<h1>🌾 Time‑Based Crop Yield Forecasting with a Multilayer Perceptron</h1>

<h2>🎯 Project Overview</h2>
This project builds a time‑aware forecasting model to predict next‑year crop yield (kg/ha) using environmental, geographic, and crop‑specific features.  
A Multilayer Perceptron (MLP) is trained on historical data (2010–2019), validated on 2020, and tested on 2021 to forecast 2022 yield.

The pipeline includes:
<ul>
  <li>Environmental feature aggregation (rainfall, soil moisture, temperature, evapotranspiration, land cover)</li>
  <li>Geospatial alignment using K‑Nearest Neighbours</li>
  <li>One‑hot encoding of country and crop type</li>
  <li>Standardisation of all numerical features</li>
  <li>Time‑based train/validation/test split</li>
  <li>MLP training with early stopping</li>
</ul>

<h2>🛠 Tools & Libraries</h2>

- Python  
- Pandas, NumPy  
- Scikit‑learn  
- TensorFlow / Keras  
- Matplotlib  

<h2>📊 Dataset Summary</h2>
Final merged dataset: <b>57,447 rows</b> and <b>297 input features</b>, including:
<ul>
  <li>Annualised environmental variables</li>
  <li>Land cover percentages</li>
  <li>Latitude & longitude</li>
  <li>268 one‑hot encoded categorical features</li>
</ul>

The target variable is <b>yield_kg_per_ha</b>.

<h2>🧠 Model Architecture</h2>
A feedforward MLP with:
<ul>
  <li>Hidden Layer 1: 128 units, ReLU</li>
  <li>Hidden Layer 2: 64 units, ReLU</li>
  <li>Output Layer: 1 unit, linear activation</li>
</ul>

Training details:
<ul>
  <li>Optimizer: Adam (lr = 0.0005)</li>
  <li>Loss: Mean Squared Error (MSE)</li>
  <li>Batch size: 32</li>
  <li>Early stopping at epoch 171</li>
</ul>

<h2>📈 Performance (Test Set: Predicting 2022)</h2>
<table>
<tr><th>Metric</th><th>Value</th></tr>
<tr><td>RMSE</td><td>4455.12 kg/ha</td></tr>
<tr><td>MAE</td><td>1597.33 kg/ha</td></tr>
<tr><td>R²</td><td>0.91</td></tr>
</table>

The model explains <b>91% of yield variance</b>, with strong alignment between predicted and actual values.

<h2>📌 Key Strengths</h2>
<ul>
  <li>Strict time‑based splitting prevents data leakage</li>
  <li>Robust feature engineering across multiple datasets</li>
  <li>MLP captures non‑linear relationships between climate and yield</li>
  <li>High generalisation performance on unseen future data</li>
</ul>
