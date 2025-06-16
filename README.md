# DataMining-Daily-Stock-Index-2
# DataMining-Daily-Stock-Index
Daily stock index return for the Canadian, UK, and US

S&P/TSX Composite Index Price Prediction
This project aims to predict the S&P/TSX Composite Index prices using historical data and an LSTM (Long Short-Term Memory) model. It includes data preparation, feature engineering with technical indicators, model training, and performance evaluation, providing insights into stock price forecasting.
Dataset
The dataset comprises historical daily data of the S&P/TSX Composite Index, sourced from two CSV files (S&P_TSX Composite Historical Data-2.csv and S&P_TSX Composite Historical Data.csv), merged into Merged_S&P_TSX_normalization.csv. It includes:

Columns: Date, Price, Open, High, Low, Change %, SMA_10 (10-day Simple Moving Average), EMA_10 (10-day Exponential Moving Average), RSI_14 (14-day Relative Strength Index), MACD, MACD Signal, and MACD Difference.
Time Range: From January 2, 1990, to recent years (up to 2016 in the sample provided).
Preprocessing: Data is cleaned, normalized using StandardScaler, and enriched with technical indicators for enhanced predictive power.

Methods

Data Preparation:

Merged and sorted historical data by date (Canada.ipynb).
Added technical indicators: SMA_10, EMA_10, RSI_14, and MACD (Additional_signal.ipynb).
Normalized numerical features for model input (Additional_signal.ipynb).


Model Training:

Utilized an LSTM model with 60-day sequence length for time-series prediction (Canada_Predict.ipynb).
Architecture: Two LSTM layers (100 and 80 units) with dropout (0.3), followed by dense layers (25 and 1 units).
Trained on 70% of the data, with 30% reserved for testing, using Mean Squared Error (MSE) loss and Adam optimizer.


Evaluation:

Metrics: Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), R², and Adjusted R².
Visualizations: Real vs. predicted prices, error distribution, model loss, and scatter plots.



Results

Training Set Performance:

MAE: 0.0341
MSE: 0.0016
RMSE: 0.0406
R²: 0.9977
Adjusted R²: 0.9977


Test Set Performance:

MAE: 0.0373
MSE: 0.0027
RMSE: 0.0517
R²: 0.9860
Adjusted R²: 0.9860




![Predicted-1](https://github.com/user-attachments/assets/8deef54e-4240-4510-bbc5-f6d6e922fefc)

![Predicted-2](https://github.com/user-attachments/assets/26922118-7cf0-4790-b0bc-a6f8f401eae0)


The model demonstrates high accuracy, with R² scores indicating strong predictive capability on both training and test sets. Visualizations confirm alignment between real and predicted values.
Installation and Usage
To run this project locally, follow these steps:

Clone the Repository:
git clone https://github.com/yourusername/sp-tsx-prediction.git
cd sp-tsx-prediction


Install Dependencies:Install required Python packages:
pip install -r requirements.txt

Required libraries include: numpy, pandas, matplotlib, seaborn, sklearn, tensorflow.

Prepare the Data:

Ensure Merged_S&P_TSX_normalization.csv is in the project directory.
Alternatively, run Canada.ipynb and Additional_signal.ipynb to preprocess raw data.


Run the Prediction Model:Execute the LSTM prediction script:
jupyter notebook Canada_Predict.ipynb

Follow the notebook cells to train the model and visualize results.


Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes and commit (git commit -m "Add feature").
Push to your branch (git push origin feature-branch).
Open a pull request or submit an issue for discussion.



