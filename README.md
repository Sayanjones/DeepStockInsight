# StockFusion: Hybrid Model for Stock Price Prediction

## Project Overview
**StockFusion** is a hybrid model designed to predict stock prices by integrating two powerful data sources: **historical stock prices** and **sentiment analysis of news headlines**. This project aims to enhance the accuracy of stock price predictions by leveraging traditional numerical analysis combined with sentiment-driven insights from news articles, creating a more robust forecasting model.

---

## Features
- **Data Integration:** Combines historical stock data from **BSE SENSEX** with sentiment scores derived from **Times of India** news headlines.
- **Sentiment Analysis:** Utilizes the **VADER sentiment analysis** tool to extract sentiment scores (positive, neutral, negative, and compound) from news headlines.
- **Predictive Modeling:** Employs an **LSTM-based RNN model** to capture temporal dependencies in stock prices and sentiment data.
- **Performance Metrics:** Evaluates the model's accuracy using **Root Mean Square Error (RMSE)**, **Mean Absolute Error (MAE)**, and **R2 Score**.

---

## Dataset

### Stock Data:
- **Source:** Yahoo Finance via the `yfinance` library
- **Timeframe:** January 2, 2001, to December 31, 2020
- **Features:** Open, High, Low, Close, Adjusted Close, Volume

### News Data:
- **Source:** Times of India News Headlines dataset
- **Timeframe:** January 2, 2001, to December 31, 2020
- **Features:** Publish Date, Headline Text

---

## Preprocessing
### Stock Data:
- Removed duplicates
- Converted dates to `datetime` format
- Filtered relevant columns: Date, Close, Open, High, Low, Volume

### News Data:
- Removed duplicates
- Converted publish date to `datetime` format
- Grouped headlines by date

### Data Integration:
- Merged stock data with sentiment scores from the news headlines
- Generated sentiment scores for each headline using the **VADER** tool
- Dropped irrelevant columns and arranged the dataset for modeling

---

## Modeling

### Architecture:
- **LSTM Layers:** 3 LSTM layers with 100 units each
- **Dropout Layer:** Prevented overfitting with a dropout layer
- **Dense Layer:** Final output layer predicting the stock price

### Training:
- 80% of the data used for training, 20% for testing
- Scaled features using **MinMaxScaler**
- Model trained over **10 epochs** with a batch size of 8

### Evaluation:
- **Training Loss:** 0.2717
- **Test Loss:** 1.2888
- **RMSE (Root Mean Square Error):** 651.2819
- **R2 Score:** 0.9738

---

## Results
The model successfully predicted stock prices with high accuracy, achieving an **R2 score of 0.9738** and an **RMSE of 651.2819**. The inclusion of sentiment analysis added valuable context to stock price movements, improving prediction performance. 

---

## Visualization
The predicted stock prices are plotted against the actual test data to visualize the model's performance. The resulting plot is saved as **Stock Price Prediction.jpg**.

---

## Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/StockFusion.git
   cd StockFusion
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

Run the project script or Jupyter notebook to train the model and make predictions. The code will:
1. Load and preprocess stock and news data.
2. Perform sentiment analysis on the news headlines.
3. Train the LSTM model for stock price prediction.
4. Evaluate and visualize the results.

---

## Contributing
Contributions to the project are welcome! Please feel free to fork the repository and submit pull requests for any improvements or bug fixes.

1. Fork the repository.
2. Create a new branch.
3. Implement your changes.
4. Submit a pull request with a description of the changes.

---

## License
This project is licensed under the [MIT License](LICENSE).  

---  

Happy coding! 😊
