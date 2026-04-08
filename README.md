📈 Stock Price Predictor
A Python-based machine learning and deep learning application that forecasts stock closing prices using Linear Regression and LSTM (Long Short-Term Memory) neural networks.

Authors: Harsh Singh (2416551) & Himanshu Joshi (2416557)
Institution: CGC College of Engineering, Landran, Mohali
Guide: Ms. Sapna Saini, Assistant Professor, Dept. of CSE


🧠 Overview
The Stock Price Predictor fetches real-time historical stock data, preprocesses it, trains two predictive models, evaluates their performance, and visualizes actual vs. predicted prices — all within a modular Python environment.

✨ Features

Fetches historical stock data via the yFinance API
Dual-model prediction: Linear Regression (ML) + LSTM (Deep Learning)
Lag-based feature engineering for ML models
60-day sequence generation for LSTM time-series learning
RMSE-based model evaluation
Next-day closing price forecast
Visualization of actual vs. predicted prices
Graceful error handling for invalid tickers, missing data, and non-trading days


🛠️ Tech Stack
ComponentTechnologyLanguagePython 3.xData FetchingyFinanceData ProcessingPandas, NumPyML Modelscikit-learn (Linear Regression)DL ModelTensorFlow / Keras (LSTM)VisualizationMatplotlibIDEGoogle Colab / Jupyter Notebook / VS Code

📦 Installation
bashpip install yfinance scikit-learn tensorflow matplotlib pandas numpy

🚀 Usage
Run the script and follow the prompts:
bashpython stock_predictor.py
Enter stock ticker (e.g., RELIANCE.NS, TCS.NS, AAPL): AAPL
Enter start date (YYYY-MM-DD) or press Enter for default 2020-01-01:
The system will automatically:

Fetch historical data up to the latest trading day
Train both ML and DL models
Print RMSE scores for each model
Display the predicted next-day closing price
Plot actual vs. predicted prices


📊 Model Architecture
Linear Regression (ML)

Uses 5 lag features (previous 5 days' closing prices)
80/20 train-test split
Evaluated using RMSE

LSTM Network (DL)
Input → LSTM(50, return_sequences=True) → Dropout(0.2)
      → LSTM(50, return_sequences=False) → Dropout(0.2)
      → Dense(1) → Predicted Price

Sequence length: 60 days
Optimizer: Adam | Loss: Mean Squared Error
Epochs: 20 | Batch size: 32


📁 Project Structure
stock-price-predictor/
├── stock_predictor.py       # Main application script
├── README.md                # Project documentation
└── requirements.txt         # Python dependencies

📈 Sample Results (AAPL)
ModelRMSELinear Regression3.0843LSTM6.9939

Predicted next day's closing price for AAPL: 277.95


🔮 Future Enhancements

GUI dashboard using Streamlit or Tkinter
Real-time data streaming via live APIs
Multi-stock and portfolio-level predictions
Additional models: GRU, Prophet, Transformers
Database integration for persistent storage
PDF/Excel export of prediction reports


🔗 Live Code
Full source code available on Google Colab:
Open in Colab

📚 References

Brownlee, J. — Deep Learning for Time Series Forecasting, Machine Learning Mastery, 2020
Chollet, F. — Deep Learning with Python, Manning Publications, 2021
Yahoo Finance API
scikit-learn Docs
TensorFlow Docs
Matplotlib Docs


⚠️ Disclaimer
This project is developed for educational purposes only and does not constitute financial advice. Predictions are based on historical data and should not be used for real trading decisions.
