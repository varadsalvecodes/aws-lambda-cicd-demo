# Automated CI/CD Pipeline for AWS Lambda Using GitHub and AWS CodePipeline

## Project Overview

This project demonstrates how to automatically execute an AWS Lambda function whenever new code is pushed to a GitHub repository using AWS CodeConnections and AWS CodePipeline.

Instead of manually invoking the Lambda function after every code change, the CI/CD pipeline automatically:

* Connects the GitHub repository with AWS using CodeConnections
* Detects new commits pushed to the `main` branch
* Retrieves the latest source code
* Starts the AWS CodePipeline execution
* Invokes the AWS Lambda function
* Records Lambda execution logs in Amazon CloudWatch
* Provides an automated GitHub-to-AWS CI/CD workflow

## Technologies Used

* GitHub
* AWS CodeConnections
* AWS CodePipeline
* AWS Lambda
* Amazon CloudWatch
* AWS IAM
* AWS CLI
* Python
* PowerShell
* Git

## CI/CD Architecture

```text
GitHub Repository
       │
       │ Git Push
       ▼
AWS CodeConnections
       │
       ▼
AWS CodePipeline
       │
       ├── Source Stage
       │
       ▼
   Lambda Stage
       │
       ▼
AWS Lambda Function
       │
       ▼
Amazon CloudWatch
```

## Project Structure

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/499dbd95-832e-49cb-a7d8-56fe8c6a661d" />



## AWS CodeConnections

AWS CodeConnections is used to connect the GitHub repository with AWS CodePipeline.

The configured repository is:

```text
varadsalvecodes/aws-lambda-cicd-demo
```

Branch:

```text
main
```

CodeConnections allows AWS CodePipeline to automatically detect new commits from GitHub.

## AWS CodePipeline

The pipeline is named:

```text
aws-lambda-cicd-demo-pipeline
```

The pipeline contains two stages:

### Source Stage

The Source stage retrieves the latest commit from the GitHub repository using AWS CodeConnections.

### Lambda Stage

The Lambda stage invokes the AWS Lambda function:

```text
aws-lambda-cicd-demo
```

## CI/CD Workflow

When a new change is made to the project, the following process occurs automatically:

```text
Developer
    │
    │ git add .
    │ git commit
    │ git push
    ▼
GitHub
    │
    ▼
CodeConnections
    │
    ▼
CodePipeline
    │
    ▼
Lambda Function
    │
    ▼
CloudWatch Logs
```
## Project Structure

```text
aws-lambda-cicd-demo/
││
├── codepipeline-connection-policy.json
├── codepipeline-lambda-policy.json
├── codepipeline-s3-policy.json
├── codepipeline-trust-policy.json
│
├── lambda-codepipeline-policy.json
├── lambda-s3-policy.json
├── lambda-trust-policy.json
│
├── response.json
│
└── README.md
```


