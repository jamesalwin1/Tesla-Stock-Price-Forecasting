# Tesla Stock Price Forecasting Using LSTM

## Project Overview

This project aims to forecast Tesla's stock opening prices using a Long Short-Term Memory (LSTM) neural network. Stock price prediction is a time-series forecasting problem where historical stock data is used to predict future prices.

The model learns patterns from Tesla's historical stock prices and predicts the next day's opening price using the previous 60 days of stock market data.

---

## Dataset Source

Dataset: Tesla Historical Stock Price Dataset

File Used: `Tesla.csv`

Features Available:

- Date
- Open
- High
- Low
- Close
- Volume
- Adj Close

Target Variable:

- Open Price

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the Tesla stock dataset using Pandas.
2. Set the Date column as the index.
3. Performed exploratory data analysis using summary statistics and visualizations.
4. Checked for missing values.
5. Selected the Open price column for prediction.
6. Normalized the data using MinMaxScaler with a range of 0 to 1.
7. Split the dataset into:
   - Training Data: 75%
   - Testing Data: 25%
8. Created sequences of 60 previous days to predict the next day's stock price.
9. Reshaped the data into a format suitable for LSTM input.

---

## LSTM Model Architecture

The forecasting model was built using TensorFlow/Keras.

### Model Architecture

```text
Input Layer (60 Time Steps, 1 Feature)
                │
                ▼
LSTM Layer (50 Units, Return Sequences=True)
                │
                ▼
LSTM Layer (64 Units)
                │
                ▼
Dense Layer (32 Units)
                │
                ▼
Dense Layer (16 Units)
                │
                ▼
Output Layer (1 Unit)
```

### Model Configuration

- Optimizer: Adam
- Loss Function: Mean Squared Error (MSE)
- Callback: Early Stopping
- Epochs: 100
- Batch Size: 32

---

## Model Implementation

The following steps were performed:

1. Imported required libraries.
2. Loaded Tesla stock market data.
3. Visualized stock price trends and feature correlations.
4. Normalized stock prices using MinMaxScaler.
5. Created 60-day input sequences.
6. Built and compiled the LSTM model.
7. Trained the model on historical stock prices.
8. Generated predictions on test data.
9. Converted predictions back to original scale.
10. Evaluated model performance using error metrics.
11. Visualized actual and predicted stock prices.

---

## Results and Insights

### Performance Metrics

| Metric | Value |
|----------|----------|
| Mean Squared Error (MSE) | 35.25 |
| Root Mean Squared Error (RMSE) | 5.94 |
| Mean Absolute Error (MAE) | 4.35 |

### Visualizations

The project includes the following visualizations:

- Correlation Heatmap
- Tesla Open Stock Price History
- Training Loss Curve
- Actual vs Predicted Stock Prices

### Key Observations

- The LSTM model successfully captured the overall trend of Tesla stock prices.
- Predicted values closely followed actual stock prices during the testing period.
- The average prediction error was relatively low, demonstrating effective forecasting performance.
- The training loss steadily decreased, indicating successful model learning.
- Slight deviations occurred during periods of high market volatility, which is expected in stock market prediction tasks.

### Future Improvements

- Include additional features such as High, Low, Close, and Volume prices.
- Use Bidirectional LSTM or GRU architectures.
- Perform hyperparameter tuning.
- Add technical indicators such as RSI, MACD, and Moving Averages.
- Experiment with different sequence lengths and forecasting horizons.

---

## Project Structure

```text
Tesla-Stock-Price-Forecasting/
│
├── Tesla_Stock_Price_Forecasting_using_LSTM.ipynb
├── Tesla.csv
├── README.md
├── requirements.txt
│
├── images/
│   ├── correlation_heatmap.png
│   ├── stock_price_history.png
│   ├── loss_curve.png
│   └── prediction_vs_actual.png
│
└── .gitignore
```

---

## How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Tesla-Stock-Price-Forecasting.git
```

### 2. Navigate to the Project Directory

```bash
cd Tesla-Stock-Price-Forecasting
```

### 3. Install Required Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the Notebook

Open:

```text
Tesla_Stock_Price_Forecasting_using_LSTM.ipynb
```

### 6. Run All Cells

Execute all notebook cells sequentially to:

- Preprocess the data
- Train the LSTM model
- Generate predictions
- Evaluate model performance
- Visualize results

---

## Output Screenshots

### Correlation Heatmap
![Correlation Heatmap](images/correlation_heatmap.png)

### Tesla Stock Price History
![Stock Price History](images/stock_price_history.png)

### Training Loss Curve
![Loss Curve](images/loss_curve.png)

### Actual vs Predicted Prices
![Prediction vs Actual](images/prediction_vs_actual.png)

---

## Conclusion

This project demonstrates the application of Long Short-Term Memory (LSTM) networks for stock price forecasting. Using Tesla's historical stock data, the model effectively learns temporal patterns and predicts future stock prices with reasonable accuracy. The results indicate that LSTM networks are well-suited for time-series forecasting problems in financial markets.
