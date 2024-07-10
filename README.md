# Price-Prediction-using-ARIMA-and-LSTM-on-Indian-Stocks
This code fetches stock data from Yahoo Finance, trains an LSTM model on the data to make predictions, uses an ARIMA model to correct the errors in the LSTM predictions, and plots various aspects of the process.
It fetches stock data and transforms it for various plots that go into the ngrok dashboard.

To run this script:

Make sure you have all the required libraries installed.
Set up a .env file with necessary environment variables (like OUTPUT_ADDRESS, LAG, EPOCHS, etc.).
Run the script and enter the stock ticker symbol when prompted.
The script will fetch the stock data, train the models, make predictions, and save the results and plots to the specified output directory.

Using AIC to fit ARIMA models, we find the ideal parameters, the model is fitted.
the LSTM model is trained using:
The data_allocation(data) function splits the data into two parts: training data and testing data. The training data is used to train the model, and the testing data is used to evaluate the model's performance.

1) The apply_transform(data, n) function prepares the data for the LSTM model. It creates sequences of data points (lagged sequences) that the LSTM will use to learn patterns.
LSTM Model Training:

2) The LSTM(train, n, number_nodes, learning_rate, epochs, batch_size) function trains an LSTM model using the training data. It configures the model with layers, trains it, and returns the trained model along with predictions.
Model Accuracy Calculation:

3) The calculate_accuracy(true_values, predictions) function calculates how well the model performed by computing metrics like Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE).
Error Evaluation:

4) The Error_Evaluation(train_data, predict_train_data, n) function calculates the difference between the actual and predicted values from the LSTM model to understand where and how much the model is making errors.
