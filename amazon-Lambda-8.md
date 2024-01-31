# AWS Lambda

- AWS Lambda is a `serverless` compute service.
- you dont need to manage or provision the servers.
- AWS Lambda is `Event Driven` serverless compute service
- `with Lambda `, you can execute your code in response to specific events,such as `changes to data` in an `Amazon S3 buckets` or `updates to a DynamoDB tables`

#img


- `Features` of AWS Lambda
    - `Serverless Architecture`
        - Lambda abstracts the underlying infrastructure allowing developers to focus on writing code without worrying about server provisioning,scaling or maintenance.
    - `Event-Driven Programming`
        - `Lambda functions `can be `triggered `by various AWS services such as `API Gateways`,`S3`,`DynamoDB`,`SNS `and more.This event-driven model enables you to build application that repond to changes in the AWS environment.
    - `Programming Languages`
        - Lambda supports multiple programming languages including Node.js,Python,Java,C#,Go and Ruby.
    - `Stateless Execution`
        - Lambda function are designed to be stateless meaning they `don't retain any state between executions.`However,you can use other AWS services like `DynamoDB or S3 ` to `store and retrive presistent data.`
    - `Pay-per-Use Model`

## AWS Lambda event sources

- `Configure other AWS services as event source to invoke your function.`
-Alternatively,invoke a lambda function from the Lambda console,AWS SDK or AWS CLI.

#img

## AWS Lambda function configuration

#img

## UseCase Example Diagram

#img

#img


## AWS Lambda Quotas

#img