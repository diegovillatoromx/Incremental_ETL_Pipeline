# AWS CDK Cryptocurrency Exchange Rate Data Producer

## Overview

This code is developed using the AWS Cloud Development Kit (CDK) and is designed to create an AWS stack responsible for setting up a Lambda function that produces cryptocurrency exchange rate data. The stack defines various AWS resources and configurations required for the Lambda function to execute at specific intervals.

### DataProducerStack Class

The `DataProducerStack` class represents the AWS CDK stack and extends the `Stack` class. Within the constructor method:

- An AWS Lambda function (`crypto_data_producer`) is set up to handle data production. This function is configured with a specific runtime (`LAMBDA_RUNTIME`) and associated code. It has a timeout of 60 seconds to complete its execution.
- The Lambda function requires permissions to access other AWS services, which are defined in the `lambda_role` IAM role. This role is assumed by the `lambda.amazonaws.com` service principal and is granted managed policies for full access to S3, CloudWatch, and Kinesis.

### Alpha Vantage Layer

The code includes an Alpha Vantage layer (`alpha_vantage_layer`) which provides additional functionality to the Lambda function. The layer's code is sourced from a local directory.

### Environment Variables

The Lambda function's environment variables are configured using the `ENVIRONMENT` dictionary, which retrieves values from corresponding environment variables using the `config` function.

### Event Rule

Furthermore, the code sets up an event rule (`intraday_rule`) that defines a schedule for executing the Lambda function at regular intervals. In this case, the rule is configured to trigger every minute (`Duration.minutes(1)`).

For each cryptocurrency conversion defined in the `CRYPTO_CONVERSIONS` list, a Lambda function target (`intraday_target`) is created and associated with the event rule. This ensures that the Lambda function is triggered with the appropriate input parameters for each cryptocurrency conversion, enabling the production of exchange rate data.

In summary, this code creates an AWS stack with the necessary resources and configurations to establish a Lambda function responsible for producing cryptocurrency exchange rate data at regular intervals. The stack encompasses IAM roles, event rules, and Lambda function settings to enable the execution and scheduling of the data production process.
