# AWS Lambda

- AWS Lambda is a `serverless` compute service.
- you dont need to manage or provision the servers.
- AWS Lambda is `Event Driven` serverless compute service
- `with Lambda `, you can execute your code in response to specific events,such as `changes to data` in an `Amazon S3 buckets` or `updates to a DynamoDB tables`

![lambda1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/c05792d6-f580-4569-aa20-da80adc2c522)



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

![lambda2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/0f579184-1eb5-4979-ad88-3bfd919b323f)


## AWS Lambda function configuration

![lambda3](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/31580743-de5a-4b27-b895-82bdbee3aa7a)


## UseCase Example Diagram

![lambda4](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/3c505ab5-978b-4fcb-b8be-939f4731ccea)


![lambda5](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/bef8297d-6882-41c0-a561-a3914de936d2)

## AWS Lambda Quotas

![lambda6](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/160fccb7-0033-4342-a92d-22c37d3a8f8f)



## Lambda Practise

- Lambda is just an executor

### LAB

![lambda7](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/86a4e247-6d1a-4fbe-9207-7fd95fef8604)
