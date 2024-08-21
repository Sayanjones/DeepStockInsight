# StockFusion: Hybrid Model for Stock Price Prediction

### Project Overview:
StockFusion is a hybrid model developed for predicting stock prices by leveraging both numerical analysis of historical stock data and sentiment analysis of news headlines. The project aims to enhance the accuracy of stock price predictions by integrating traditional financial data with sentiment-driven insights from news articles.

### Features:
**Data Integration:** Combines historical stock prices from BSE SENSEX with sentiment analysis of news headlines from the Times of India.
<br/>
**Sentiment Analysis:** Uses the VADER sentiment analysis tool to extract sentiment scores (positive, neutral, negative, and compound) from news headlines.
<br/>
**Predictive Modeling:** Implements an LSTM-based RNN model to capture temporal dependencies in stock prices and sentiment data.
<br/>
**Performance Metrics:** Evaluates model performance using metrics like Root Mean Square Error (RMSE), Mean Absolute Error (MAE), and R2 Score.

### Dataset:
****Stock Data:-****
<br/>
**Source:** Yahoo Finance via yfinance library.
<br/>
**Timeframe:** 2001-01-02 to 2020-12-31.
<br/>
**Features:** Open, High, Low, Close, Adjusted Close, Volume.

****News Data:-****
<br/>
**Source:** Times of India News Headlines dataset.
<br/>
**Timeframe:** 2001-01-02 to 2020-12-31.
<br/>
**Features:** Publish Date, Headline Text.

### Preprocessing:
**Stock Data:**
Removed duplicates.
Converted dates to datetime format.
Filtered relevant columns: Date, Close, Open, High, Low, Volume.
<br/>
**News Data:**
Removed duplicates.
Converted publish date to datetime format.
Grouped headlines by date.
<br/>
**Data Integration:**
Merged stock data with sentiment scores from news headlines.
Generated sentiment scores for each headline using the VADER tool.
Dropped irrelevant columns and arranged the dataset for modeling.

### Modeling:
**Architecture:**
3 LSTM layers with 100 units each, followed by a Dropout layer to prevent overfitting.
Final Dense layer to output the predicted stock price.
<br/>
**Training:**
Used 80% of the data for training and 20% for testing.
Scaled the features using MinMaxScaler.
Trained the model over 10 epochs with a batch size of 8.

### Evaluation:
**Training Loss:** 0.2717,
**Test Loss:** 1.2888,
**RMSE:** 651.2819,
**R2 Score:** 0.9738

### Results:
The model successfully predicted stock prices with a high degree of accuracy, achieving an R2 score of 0.9738 and a RMSE of 651.2819. The integration of sentiment analysis provided additional context to the stock price movements, improving the prediction performance.

### Visualization:
The predicted stock prices are plotted against the actual test data to visualize the model's performance. The resulting plot is saved as **Stock Price Prediction.jpg**. 

### Installation:
1. Clone the repository:```git clone https://github.com/your-username/StockFusion.git```
   
2. Run the notebook or script to train the model and make predictions.

### Usage:
This project can be used as a reference for creating hybrid models that integrate financial data with sentiment analysis to predict stock prices. It can be extended to other datasets or modified for real-time predictions.

### Contributing:
Contributions are welcome! Please fork the repository and submit a pull request with your improvements.


