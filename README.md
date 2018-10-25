# Serverless Timer - api
Simple timer app that works without server, using AWS Ramda to handle user's requests

## Example site
[Serverless-timer](http://serverless-timer-client.s3-website.ap-northeast-2.amazonaws.com/)
You can use this web app after signup or login by guest. 

## Getting Started
This api is bulit on severless framework to bulid infrastructure of AWS as code

### Prerequisites
* AWS account and IAM user with admin access
[official guide to create IAM user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)


### Installing
1. Install the dependencies.
```
npm install
```
1. Set up credential for AWS(your IAM Key & Secret) to use AWS with serverless.
```
serverless config credentials --provider aws --key YOUR-IAM-KEY --secret YOUR-IAM-SECRET
```
1. Change your AWS region in serverless.yml.
```
# inside serverless.yml
provider:
  name: aws
  runtime: nodejs8.10
  stage: dev
  region: YOUR-AWS-REGION
  # To load environment variables externally
  # rename env.example to env.yml and uncomment
  # the following line. Also, make sure to not
  # commit your env.yml.
  #
  environment:
    tableName: ${self:custom.tableName}

```

## Deployment
```
serverless deploy -v
```
After deployment you can see the API end point on your terminal, use it to communicate with client side. 

## Built With
* [Serverless Node.js Starter](https://github.com/AnomalyInnovations/serverless-nodejs-starter)
* [AWS sdk](https://github.com/aws/aws-sdk-js)
* [npm](https://npm.community/)

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments
* Hat tip to anyone whose code was used
* Inspire from [Serverless Stack](http://serverless-stack.com) guide.
* etc
