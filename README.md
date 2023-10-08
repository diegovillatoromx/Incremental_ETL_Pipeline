# Incremental ETL Pipeline with AWS CDK
Cryptocurrency, represented by digital or virtual currencies utilizing cryptographic techniques for secure transactions and asset verification, operates on decentralized blockchain technology. Bitcoin, introduced in 2009 as the pioneering decentralized cryptocurrency and the largest by market capitalization, paved the way for numerous alternative cryptocurrencies or "altcoins."

In the domain of Data Engineering within AWS, cryptocurrency data analytics involves systematic examination and interpretation of cryptocurrency and market data. This plays a pivotal role in understanding market trends, making informed decisions, and discovering opportunities within the cryptocurrency landscape. Key aspects encompass *market data analysis*, *blockchain analysis*, *sentiment analysis*, *trading strategies*, *predictive modeling*, and *risk assessment*. Employing data analytics in AWS enables data-driven decision-making, facilitating effective navigation of the dynamic cryptocurrency domain and risk management.  


## Table of Contents

- [Description](#description)
- [Architecture](#architecture)
- [Modular_Code_Overview](#modular-code-overview)
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

Within the context of this financial data engineering project in AWS, we are acquiring valuable information through the [Alpha Vantage API](https://www.alphavantage.co/documentation/). Alpha Vantage is positioned as a financial data provider that furnishes us with real-time and historical data for a broad spectrum of financial assets, encompassing stocks, indices, currencies, and cryptocurrencies. This API is employed for the purpose of accessing historical closing prices of stocks, enabling our analysis and predictive modeling within the AWS environment. This information becomes paramount for making well-informed decisions in financial markets.

## Modular Code Overview

 - 📂 docs
   - 📜 README.md (Main Documentation Page)
   - 📜 Architecture.md (Data Architecture)
   - 📜 Design.md (Pipeline Design)
   - 📜 Configuration.md (AWS Configuration)
   - 📜 Testing.md (Testing and Validation)
   - 📜 UserGuide.md (User Guide)
   - 📜 CostManagement.md (Cost Management)
   - 📜 ...
 - 📂 src
   - 📂 etl_pipeline
     - 📜 etl_script.py (Pipeline Code)
     - 📜 transform_functions.py (Transformation Functions)
     - 📜 ...
 - 📂 data
   - 📜 sample_data.csv (Sample Data)
   - 📜 ...
 - 📂 tests
   - 📜 unit_tests.py (Unit Tests)
   - 📜 integration_tests.py (Integration Tests)
   - 📜 ...
 - 📂 assets
   - 🖼️ architecture_diagram.png (Architecture Diagram)
   - 📷 screenshots
     - 🖼️ screenshot1.png
     - 🖼️ screenshot2.png
     - ...
 - 📜 LICENSE.txt (License)
 - 📜 .gitignore (Ignore File Configuration)
 - 📜 README.md (Repository Main Page)


## Installation
 
Below are the steps required to set up the environment and run this Data engineering project on cloud9 on aws.
To create an AWS Cloud9 environment, you can follow these steps:

1. Open the AWS Management Console: Go to the AWS Management Console (https://console.aws.amazon.com) and sign in to your AWS account.
2. Navigate to Cloud9: Use the AWS services search bar or navigate to the "Developer Tools" category and select "Cloud9."
3. Click "Create environment": On the Cloud9 dashboard, click the "Create environment" button.
4. Provide environment details:
 - Enter a name for your environment. Optionally, enter a description.
 - Choose the environment type (new or clone an existing environment).
 - Select the instance type based on your requirements.
 - Choose the platform (Amazon Linux 2 or Ubuntu).
5. Configure settings:
 - Choose the network settings (either create a new Amazon VPC or use an existing one).
 - Select the subnet for your environment.
 - Choose the IAM role that Cloud9 will use to access AWS resources on your behalf.
 - Configure additional settings as needed.
6. Review and create:
 - Review the configuration details.
 - Enable the option to create an AWS CloudFormation stack if desired.
 - Click "Create environment" to start the provisioning process.
7. Wait for the environment to be created: The Cloud9 environment creation process may take a few minutes. You can monitor the progress on the Cloud9 dashboard.
8. Access the Cloud9 IDE: Once the environment is created, you can click on its name in the Cloud9 dashboard to access the Cloud9 integrated development environment (IDE) in your web browser.

## Usage


## Contribution
  1. Focus changes on spec ific improvements.
  2. Follow project's coding style.
  3. Provide detailed descriptions in pull requests.
## Reporting Issues
  Use "Issues" to report bugs or suggest improvements.
# Contact
For questions or contact, my [Mail](diegovillatormx@gmail.com) or [Twitter](https://twitter.com/diegovillatomx). 
