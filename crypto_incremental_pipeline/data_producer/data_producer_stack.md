# AWS CDK Cryptocurrency Exchange Rate Data Producer

## Overview

This code, developed using the AWS Cloud Development Kit (CDK), establishes an AWS stack responsible for creating a Lambda function that produces cryptocurrency exchange rate data. The stack encompasses various AWS resources and configurations essential for the Lambda function's execution at specified intervals. 

### DataProducerStack Class

The `DataProducerStack` class represents the AWS CDK stack and extends the `Stack` class. Within the constructor method:

- An AWS Lambda function (`crypto_data_producer`) is established to handle data production. This function is configured with a specific runtime (`LAMBDA_RUNTIME`) and associated code. It has a timeout of 60 seconds for completing execution.

- The Lambda function requires permissions to access various AWS services. These permissions are defined in the `lambda_role` IAM role, which is assumed by the `lambda.amazonaws.com` service principal. The role is granted managed policies providing full access to S3, CloudWatch, and Kinesis.

### Alpha Vantage Layer

The code includes an Alpha Vantage layer (`alpha_vantage_layer`), which is a pre-packaged dependency that enhances the Lambda function's functionality. The layer's code is sourced from a local directory.

### Environment Variables

The Lambda function's environment variables are configured using the `ENVIRONMENT` dictionary. These variables retrieve values from corresponding environment variables using the `config` function.

### Event Rule

Furthermore, the code configures an event rule (`intraday_rule`) that defines a schedule for executing the Lambda function at regular intervals. In this case, the rule is set to trigger every minute (`Duration.minutes(1)`).

For each cryptocurrency conversion specified in the `CRYPTO_CONVERSIONS` list, a Lambda function target (`intraday_target`) is created and associated with the event rule. This ensures that the Lambda function is triggered with appropriate input parameters for each cryptocurrency conversion, enabling the production of exchange rate data.

In summary, this code establishes an AWS stack with the requisite resources and configurations for configuring a Lambda function to produce cryptocurrency exchange rate data at specified intervals. The stack encompasses IAM roles, event rules, and Lambda function settings to enable the execution and scheduling of the data production process.
