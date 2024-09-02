# Cryptocurrency Exchange Rate Data Ingestion

## Overview

This Python script fetches cryptocurrency exchange rate data from the Alpha Vantage API and stores it in an AWS Kinesis data stream. Here's a breakdown of its functionality:
 
### Importing Necessary Modules and Setting Environment Variables

The script starts by importing necessary modules and setting up environment variables. These variables include the API key required to access the Alpha Vantage API and the name of the Kinesis data stream.

### Data Transformation Functions

The script defines functions to handle data transformation tasks. These functions are responsible for tasks such as renaming dictionary keys and converting values to float type.

### `get_crypto_data` Function

The `get_crypto_data` function utilizes the Alpha Vantage API to retrieve exchange rate data for a specified currency pair. It then applies data cleanup operations, including renaming dictionary keys and converting specific values to floats.

### `handle_intraday_request` Function

The `handle_intraday_request` function takes charge of processing the request. It calls the `get_crypto_data` function to retrieve exchange rate data, creates a partition key based on the timestamp, and puts the data into the Kinesis data stream using the boto3 library.

### `handler` Function

The `handler` function serves as the entry point for the script. It accepts an event and context as input, verifies the presence of required keys in the event, extracts the currency pair, and calls `handle_intraday_request` to store the data in the Kinesis data stream. The response from the `put_record` operation is then returned.

In summary, this script simplifies the process of fetching cryptocurrency exchange rate data, performs necessary data transformations, and efficiently stores the data in an AWS Kinesis data stream. This data can be further analyzed or processed as needed.
