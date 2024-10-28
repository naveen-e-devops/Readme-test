# AWS Lambda Terraform Module
This module deploys an AWS Lambda function with flexible configuration options for VPC integration, IAM roles, environment variables, logging, monitoring, and various event triggers.

## Resources
- Lambda Function: The aws_lambda_function resource defines the core Lambda function. This resource is responsible for deploying an AWS Lambda function with customizable configurations, including VPC integration, environment variables, error handling, and secure storage of sensitive variables via AWS Secrets Manager or Parameter Store. You can configure deployment from a local file, S3 bucket, or container image. This module supports triggers from multiple AWS services such as S3, SQS, DynamoDB Streams, and API Gateway.

    - Key Configurations: function_name, runtime, handler, memory_size, timeout, environment variables
    - Trigger Options: S3, SQS, DynamoDB Streams, and API Gateway for event-driven invocation.
