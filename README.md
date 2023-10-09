# Incremental ETL Pipeline with AWS CDK
Cryptocurrency, represented by digital or virtual currencies utilizing cryptographic techniques for secure transactions and asset verification, operates on decentralized blockchain technology. Bitcoin, introduced in 2009 as the pioneering decentralized cryptocurrency and the largest by market capitalization, paved the way for numerous alternative cryptocurrencies or "altcoins."

In the domain of Data Engineering within AWS, cryptocurrency data analytics involves systematic examination and interpretation of cryptocurrency and market data. This plays a pivotal role in understanding market trends, making informed decisions, and discovering opportunities within the cryptocurrency landscape. Key aspects encompass *market data analysis*, *blockchain analysis*, *sentiment analysis*, *trading strategies*, *predictive modeling*, and *risk assessment*. Employing data analytics in AWS enables data-driven decision-making, facilitating effective navigation of the dynamic cryptocurrency domain and risk management.  


## Table of Contents

- [Description](#description)
- [Architecture](#architecture)
- [Modular Code Overview](#modular-code-overview)
- [To create an AWS Cloud9 environment](#To-create-an-AWS-Cloud9-environment)
- [Cloning GitHub repository to AWS Cloud9](#Cloning-GitHub-repository-to-AWS-Cloud9)
- [Usage](#usage) 
- [Contribution](#contribution)
- [Contact](#contact)

## Description

The primary objective of this project is to develop an incremental Extract, Transform, Load (ETL) solution using AWS CDK for the analysis of cryptocurrency data. This process involves the construction of a serverless pipeline, in which Lambda functions are employed for data extraction from an API and subsequent streaming into Kinesis streams. Additionally, a standalone Lambda function will be created to consume data from the Kinesis stream, apply essential transformations, and store them in DynamoDB.

To conduct real-time data analytics within the Kinesis streams, we will utilize Apache Flink and Apache Zeppelin. These tools will empower us to extract insights and derive valuable information from the data. AWS serverless technologies, including Amazon Lambda and Amazon Glue, will be leveraged for efficient processing and transformation of data from three distinct data sources.

Furthermore, Amazon Athena, a query service, will be used to analyze the transformed data stored in DynamoDB. This will facilitate efficient querying and data exploration, enabling us to extract meaningful insights and make informed decisions based on cryptocurrency data.

By combining these AWS services and technologies, our aim is to create a robust and scalable solution for cryptocurrency data analysis, enabling comprehensive data processing, transformation, and analysis.

## Architecture
<img src='https://github.com/diegovillatoromx/Incremental_ETL_Pipeline/blob/main/etl-alpha.gif' alt="incremental_etl_alpha_api">

## Data Description

Within the context of this financial data engineering project in AWS, we are acquiring valuable information through the [Alpha Vantage API](https://www.alphavantage.co/documentation/). Alpha Vantage is positioned as a financial data provider that furnishes us with real-time and historical data for a broad spectrum of financial assets, encompassing stocks, indices, currencies, and cryptocurrencies. This API is employed for the purpose of accessing historical closing prices of stocks, enabling our analysis and predictive modeling within the AWS environment. This information becomes paramount for making well-informed decisions in financial markets.

## Modular Code Overview

```
  📂 crypto_incremental_pipeline
    |_📂 data_consumer
    |  |_📜 data_consumer_stack.py
    |_📂 data_producer
    |  |_📜 data_producer_stack.py
    |_📂 kinesis_stream
    |  |_📜 kinesis_stream_stack.py
    |_📂 lambda
    |  |_📜 data_consumer_lambda.py
    |  |_📜 data_producer_lambda.py
    |_📂 s3_bucket
    |  |_📜 s3_bucket_stack.py
    |_📂 scripts
    |  |_📜 CryptoHourlyETLJob.py
    |  |_📜 flink_script.sql
    |_📂 tests
    |  |_📜 __init__.py
    |  |_📂 unit
    |    |_📜 __init__.py
    |    |_📜 test_crypto_incremental_pipeline_stack.py
    | 📜 app.py
    | 📜 cdk.json 
    | 📜 requirements-dev.txt 
    | 📜 requirements.txt  
    | 📜 source.bat
```


## To create an AWS Cloud9 environment
 
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

## Cloning GitHub repository to AWS Cloud9 

1. Open your AWS Cloud9 environment: Access the [AWS Management Console](https://console.aws.amazon.com) and go to the Cloud9 service. Select the Cloud9 environment you wish to link with GitHub.
2. Configure Git credentials: In your Cloud9 environment, open a new terminal by clicking on the "Window" menu and selecting "New Terminal." Run the following commands to configure your Git credentials:
   ```bash
   git config --global user.name "Your GitHub Username"
   git config --global user.email "Your GitHub Email"
   ```
3. Generate and add an SSH key: To securely connect Cloud9 with your GitHub account, you need
to generate an SSH key pair and add the public key to your GitHub account. Run the following
command in your Cloud9 terminal:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "Your GitHub Email"
   ```
4. View and copy the public key: Run the following command to display your public key:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
   Copy the entire contents of the public key that is displayed in the terminal.
5. Add the public key to your GitHub account: Go to your [GitHub account settings](https://github.com/settings/profile) and navigate to the "SSH and GPG keys" section. Click on
"New SSH key" and give it a descriptive title. Paste the public key you copied in the previous step
and click "Add SSH key."
6. Test the connection: To test if the SSH connection between Cloud9 and GitHub is successful, run
the following command in the Cloud9 terminal:
   ```bash
   ssh -T git@github.com
   ```
   You should see a success message indicating that you've successfully authenticated with GitHub.
7. Clone a GitHub repository: In your Cloud9 environment, navigate to the directory where you want to clone the GitHub repository. Run the following command to clone the repository:
   ```bash
   git clone git@github.com:username/repository.git
   ```
   Replace username with your GitHub username and repository with the name of the repository you want to clone.

# Usage

The `cdk.json` file tells the CDK Toolkit how to execute your app.

This project is set up like a standard Python project. The initialization
process also creates a virtualenv within this project, stored under the `.venv`
directory. To create the virtualenv it assumes that there is a `python3`
(or `python` for Windows) executable in your path with access to the `venv`
package. If for any reason the automatic creation of the virtualenv fails,
you can create the virtualenv manually.

To manually create a virtualenv on MacOS and Linux:

```
$ python3 -m venv .venv
```

After the init process completes and the virtualenv is created, you can use the following
step to activate your virtualenv.

```
$ source .venv/bin/activate
```

If you are a Windows platform, you would activate the virtualenv like this:

```
% .venv\Scripts\activate.bat
```

Once the virtualenv is activated, you can install the required dependencies.

```
$ pip install -r requirements.txt
```

At this point you can now synthesize the CloudFormation template for this code.

```
$ cdk synth
```

Create a file called .env with the environment variables needed, make sure to can your own API Key from Alpha Vantage.

```
$ touch .env
$ echo 'INTRADAY_STREAM_NAME=kinesis-crypto-stream-intraday' >> .env
$ echo 'API_KEY=[YOUR_API_KEY]' >> .env
$ echo 'LAMBDA_PRODUCER_NAME=crypto_data_producer' >> .env
$ echo 'LAMBDA_CONSUMER_NAME=crypto_data_consumer' >> .env
$ echo 'DYNAMO_TABLE_NAME=crypto_intraday' >> .env
$ echo 'PRIMARY_BUCKET_NAME=crypto-incremental-project' >> .env
```

In order to install the Alpha Vantage Layer, do the following:

```
$ mkdir -p layers/alpha_vantage_layer/python
$ pip install -t layers/alpha_vantage_layer/python/ urllib3==1.26.16 alpha_vantage
```

## Contribution
  1. Focus changes on spec ific improvements.
  2. Follow project's coding style.
  3. Provide detailed descriptions in pull requests.
## Reporting Issues
  Use "Issues" to report bugs or suggest improvements.
# Contact
For questions or contact, my [Mail](diegovillatormx@gmail.com) or [Twitter](https://twitter.com/diegovillatomx). 
