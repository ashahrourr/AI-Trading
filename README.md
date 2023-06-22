# AI Trading
AI Trading a project that combines artificial intelligence and algorithmic trading techniques to manage a portfolio of stocks. The system uses historical price data, machine learning models, and the Alpaca paper trading API to make buy and sell decisions for a specified stock.

## Table of Contents
- [Overview](#overview)
- [Usage](#usage)
- [Contributing](#contributing)

## Overview

The AI Portfolio Management System consists of several components:

1. `AlpacaPaperSocket`: This class extends the Alpaca Trade API's `REST` class and provides a connection to the Alpaca paper trading API using the provided API key and base URL.

2. `TradingSystem`: This abstract base class defines the structure for a trading system. It contains abstract methods for placing buy and sell orders, as well as a system loop method that needs to be implemented by subclasses.

3. `PMDevelopment`: This class represents an AI portfolio management model. It uses historical stock data to train a neural network model using Keras and TensorFlow. The trained model is then saved to JSON and HDF5 files for later use.

4. `PortfolioMgmtModel`: This class loads the saved AI model structure and weights from the JSON and HDF5 files. It provides methods to evaluate the model's predictions on new data.

5. `PortfolioMgmtSystem`: This class extends the `TradingSystem` class and implements the specific portfolio management logic. It connects to the Alpaca API, retrieves daily stock data, calculates delta values, and uses the AI model to make buy or sell decisions based on the predicted stock price movements.

## Usage
1. Set up your Alpaca API credentials:

Open the strategy.py file.
Update the key_id and secret_key values in the AlpacaPaperSocket initialization with your Alpaca paper trading API credentials.
Save the file.

2. Prepare your historical stock data:

Ensure that your historical stock data is in CSV format.
Replace the stock_data.csv file with your own CSV file, or modify the code to load your data from a different source.

3. Train the AI portfolio management model:

Uncomment the PMDevelopment() line in strategy.py.
Run the strategy.py file.
The model will be trained using the historical stock data, and the model structure and weights will be saved to model.json and result.h5, respectively.

4. Run the portfolio management system:

Uncomment the PortfolioMgmtSystem() line in strategy.py.
Run the strategy.py file.
The system will connect to the Alpaca API, retrieve daily stock data, and make buy or sell decisions based on the AI model's predictions.

## Contributing
Contributions to the AI Portfolio Management System project are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request.

When contributing to this repository, please first discuss the change you wish to make via issue or email with the project maintainer.
