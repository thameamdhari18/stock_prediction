# stock_prediction
Imports:
The code imports necessary libraries including pandas for data manipulation, MinMaxScaler for data scaling, matplotlib for plotting, Sequential, LSTM, and Dense from Keras for building the LSTM model, and r2_score from sklearn.metrics for evaluating the model.
Loading the Data:
The code reads the data from the CSV file ('AAPL.csv') into a pandas DataFrame, parsing the 'Date' column as dates and setting it as the index.
Data Preprocessing:
The 'Close' column of the DataFrame is selected and scaled using MinMaxScaler. This ensures that all values are scaled to the range [0, 1], which is beneficial for neural network training.
Reshape Data for LSTM Model:
The create_dataset function is defined to reshape the scaled data into input-output pairs suitable for the LSTM model. It creates sequences of length time_steps from the data, where each sequence is used to predict the next value.
Splitting the Data:
The data is split into training and testing sets. 80% of the data is used for training and the remaining 20% for testing.
Building the LSTM Model:
A Sequential model is initialized, to which an LSTM layer with 50 units is added as the input layer. Dropout regularization with a dropout rate of 0.2 is applied to prevent overfitting. Finally, a Dense output layer with one unit is added.
Compiling the Model:
The model is compiled with the Adam optimizer and Mean Squared Error (MSE) loss function.
Training the Model:
The model is trained using the training data for 100 epochs with a batch size of 32. A validation split of 10% is used to monitor the model's performance on a validation set.
Predicting Closing Prices:
The model is used to predict closing prices for the test data. Predictions are scaled back to the original range using MinMaxScaler's inverse_transform method.
Plotting:
The actual and predicted closing prices are plotted against the dates using matplotlib.
Evaluating the Model:
The R-squared score is calculated to evaluate the performance of the model. R-squared measures the proportion of the variance in the dependent variable that is predictable from the independent variable(s).
Overall, this code demonstrates how to build, train, and evaluate an LSTM model for predicting stock prices using historical data. It also illustrates best practices for data preprocessing and model evaluation.
