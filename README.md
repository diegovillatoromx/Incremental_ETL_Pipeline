# Incremental ETL Pipeline with AWS CDK
Cryptocurrency, represented by digital or virtual currencies utilizing cryptographic techniques for secure transactions and asset verification, operates on decentralized blockchain technology. Bitcoin, introduced in 2009 as the pioneering decentralized cryptocurrency and the largest by market capitalization, paved the way for numerous alternative cryptocurrencies or "altcoins."

In the domain of Data Engineering within AWS, cryptocurrency data analytics involves systematic examination and interpretation of cryptocurrency and market data. This plays a pivotal role in understanding market trends, making informed decisions, and discovering opportunities within the cryptocurrency landscape. Key aspects encompass *market data analysis*, *blockchain analysis*, *sentiment analysis*, *trading strategies*, *predictive modeling*, and *risk assessment*. Employing data analytics in AWS enables data-driven decision-making, facilitating effective navigation of the dynamic cryptocurrency domain and risk management. 


## Table of Contents

- [Description](#description)
- [Architecture](#architecture)
- [Modular_Code_Overview](#modular_code_overview)
- [Installation](#installation)
- [Usage](#usage) 
- [Contribution](#contribution)
- [Contact](#contact)

## Description

In the context of AWS data engineering, cryptocurrency data analytics involves building an incremental Extract, Transform, Load (ETL) solution using AWS CDK. This entails using Lambd a functions to collect cryptocurrency data from an API and stream it into Kinesis streams, where transformations are applied and data is stored in DynamoDB. Subsequently, tools like Apache Flink and Apache Zeppelin are leveraged for analyzing the data within the Kinesis streams, while AWS serverless services like Lambda and Glue efficiently process data from diverse sources. Additionally, Amazon Athena is used to query and explore data stored in DynamoDB, extracting insights and enabling data-driven decision-making in the cryptocurrency realm, providing a comprehensive and scalable solution for cryptocurrency data analysis.

## Architecture
<img src='https://github.com/diegovillatoromx/ETL-Pipeline-Spotify/blob/main/architecture_diagram_spotify.gif' alt="architecture_diagram_spotify">

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
