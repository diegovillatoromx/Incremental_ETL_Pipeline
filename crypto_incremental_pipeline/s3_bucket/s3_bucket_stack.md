# AWS CDK Amazon S3 Bucket Creation

## Overview 

This Python script employs the AWS Cloud Development Kit (CDK) to define an AWS stack responsible for creating an Amazon S3 bucket. The stack is constructed using the `Stack` class from the AWS CDK and is named `S3BucketStack`.

### S3BucketStack Class

The `S3BucketStack` class represents the AWS CDK stack and extends the `Stack` class. Within the stack's constructor method:

- An Amazon S3 bucket resource is defined using the `Bucket` class from the `aws_s3` module. The bucket is assigned the logical ID "PrimaryBucket," and its name is set to the value of the `PRIMARY_BUCKET_NAME` constant. The constant is retrieved from environment variables using the `config` function from the `decouple` library.

By creating this stack, the code establishes the necessary infrastructure to create an S3 bucket with the specified name. The AWS CDK simplifies the management and deployment of AWS resources, and this code snippet illustrates the creation of an S3 bucket resource within an AWS CDK stack.
