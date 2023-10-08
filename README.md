# Incremental ETL Pipeline with AWS CDK
Cryptocurrency, represented by digital or virtual currencies utilizing cryptographic techniques for secure transactions and asset verification, operates on decentralized blockchain technology. Bitcoin, introduced in 2009 as the pioneering decentralized cryptocurrency and the largest by market capitalization, paved the way for numerous alternative cryptocurrencies or "altcoins."

In the domain of Data Engineeri ng within AWS, cryptocurrency data analytics involves systematic examination and interpretation of cryptocurrency and market data. This plays a pivotal role in understanding market trends, making informed decisions, and discovering opportunities within the cryptocurrency landscape. Key aspects encompass *market data analysis*, *blockchain analysis*, *sentiment analysis*, *trading strategies*, *predictive modeling*, and *risk assessment*. Employing data analytics in AWS enables data-driven decision-making, facilitating effective navigation of the dynamic cryptocurrency domain and risk management.  


## Table of Contents

- [Description](#description)
- [Architecture](#architecture)
- [Modular_Code_Overview](#modular_code_overview)
- [Installation](#installation)
- [Usage](#usage) 
- [Contribution](#contribution)
- [Contact](#contact)

## Description

The primary objective of this project is to develop an incremental Extract, Transform, Load (ETL) solution using AWS CDK for the analysis of cryptocurrency data. This process involves the construction of a serverless pipeline, in which Lambda functions are employed for data extraction from an API and subsequent streaming into Kinesis streams. Additionally, a standalone Lambda function will be created to consume data from the Kinesis stream, apply essential transformations, and store them in DynamoDB.

To conduct real-time data analytics within the Kinesis streams, we will utilize Apache Flink and Apache Zeppelin. These tools will empower us to extract insights and derive valuable information from the data. AWS serverless technologies, including Amazon Lambda and Amazon Glue, will be leveraged for efficient processing and transformation of data from three distinct data sources.

Furthermore, Amazon Athena, a query service, will be used to analyze the transformed data stored in DynamoDB. This will facilitate efficient querying and data exploration, enabling us to extract meaningful insights and make informed decisions based on cryptocurrency data.

By combining these AWS services and technologies, our aim is to create a robust and scalable solution for cryptocurrency data analysis, enabling comprehensive data processing, transformation, and analysis.

## Architecture
<img src='https://github.com/diegovillatoromx/Incremental_ETL_Pipeline/blob/main/incremental-etl.gif' alt="incremental_etl_alpha_api">

## Data Description

[Alpha Vantage](https://www.alphavantage.co/documentation/) offers enterprise-grade financial market data via a collection of robust and developer-friendly data APIs and spreadsheets. Alpha Vantage is your one-stop shop for real-time and historical global market data delivered through REST stock APIs, Excel, and Google Sheets, ranging from traditional asset classes (e.g., stocks, ETFs, commodities) to economic metrics, foreign exchange rates to cryptocurrencies, fundamental data to technical indicators.


## Modular_Code_Overview

```
  Data-Batch-Spotify-API
    |_credentials.csv

  DE_Pipeline
    |_IAM
    |_s3
    |_Lambda
    |_CloudWatchEvents
    |_GlueCatalog

Tutorial
    |_tutorial_aws.ipynb

  spotipy_library
    |_spotipy_layer.zip 
```
## Installation
 
Below are the steps required to set up the environment and run this Data Science project on your local machine. Make sure you have the following installed:
- Python 3.x: You can download it from [python.org](https://www.python.org/downloads/). 
- Pip: In most cases you can install [here](https://pip.pypa.io/en/stable/installing/).
- AWS CLI: you can download it from [AWSCLI.com](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html).

## Usage
`

## Contribution
  1. Focus changes on spec ific improvements.
  2. Follow project's coding style.
  3. Provide detailed descriptions in pull requests.
## Reporting Issues
  Use "Issues" to report bugs or suggest improvements.
# Contact
For questions or contact, my [Mail](diegovillatormx@gmail.com) or [Twitter](https://twitter.com/diegovillatomx). 
