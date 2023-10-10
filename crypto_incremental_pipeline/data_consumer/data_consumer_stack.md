# AWS CDK Cryptocurrency Data Consumer

## Overview

This code is developed using the AWS Cloud Development Kit (CDK) and is designed to define an AWS stack responsible for creating a Lambda function that consumes and processes data from a Kinesis data stream. The code encompasses several AWS services and configurations to set up the required resources for data consumption.

### DataConsumerStack Class

The `DataConsumerStack` class represents the AWS CDK stack and extends the `Stack` class. Within the constructor method:

- A DynamoDB table (`dynamodb_table`) is created with the specified table name (`DYNAMO_TABLE_NAME`). The table is configured with a partition key named "ticker" and a sort key named "last_refreshed." This table is intended for storing the processed data.

- An IAM role (`lambda_consumer_role`) is created with the necessary permissions to access AWS services, including S3, CloudWatch, Kinesis, and DynamoDB. These permissions are granted through AWS-managed policies, ensuring that the Lambda function has the required access for its operation.

- An instance of the Lambda function (`crypto_data_consumer`) is created. It is configured with the provided runtime (`LAMBDA_RUNTIME`), associated code, a timeout of 20 seconds, and an entry point defined as `data_consumer_lambda.handler`. The Lambda function's environment variables are set using the `ENVIRONMENT` dictionary, which includes the DynamoDB table name.

- The Kinesis data stream (`stream`) is retrieved based on the provided ARN (`STREAM_ARN`).

- The Lambda function is configured to consume events from the Kinesis data stream using the `add_event_source` method. The `KinesisEventSource` class from `aws_lambda_event_sources` is utilized to specify the event source details, including the batch size and the starting position for consuming the data. This ensures that the Lambda function receives events from the Kinesis stream and processes them accordingly.

In summary, this code sets up an AWS stack with the required resources and configurations to enable the consumption and processing of data from a Kinesis data stream. The stack includes a DynamoDB table, an IAM role, a Lambda function, and the necessary connections between them. The stack utilizes the boto3 library and the CDK's constructs and classes for creating and configuring the AWS resources.
