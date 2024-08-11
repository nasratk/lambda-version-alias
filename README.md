# AWS SAM Lambda Function with Versioning and Aliases

## Overview

This AWS Serverless Application Model (SAM) template sets up an AWS Lambda function with support for versioning and aliases. It helps manage different environments (development and production) by using Lambda versions and aliases.

### Features

- **Lambda Function**: Defines a basic AWS Lambda function.
- **Versioning**: Optionally creates a new version of the Lambda function.
- **Aliases**: Creates `prod` and `dev` aliases to manage different environments.

## Template Structure

The template includes:
- **Parameters**: Customize function creation and versioning.
- **Conditions**: Control version creation.
- **Resources**:
  - Lambda function
  - Lambda version (conditionally created)
  - `prod` alias (points to a specific version or the latest)
  - `dev` alias (always points to the latest version)

## Parameters

- **FunctionName**
  - **Type**: `String`
  - **Default**: `MyLambdaFunction`
  - **Description**: The name of the Lambda function.

- **CreateNewVersion**
  - **Type**: `String`
  - **Default**: `'true'`
  - **AllowedValues**: `'true'`, `'false'`
  - **Description**: Determines if a new version of the Lambda function should be created.

- **ProdAliasVersion**
  - **Type**: `String`
  - **Default**: `'$LATEST'`
  - **Description**: Specifies the version of the Lambda function to which the `prod` alias should point if not creating a new version.

## Usage

### Prerequisites

- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html) installed and configured.
- [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html) installed.
- An S3 bucket for deploying Lambda code (if not using the default).

### Steps to Deploy

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-repo/lambda-sam-template.git
   cd lambda-sam-template

2. **Build the project**

   ```bash
   sam build

3. **Deploy the stack**

   ```bash
   sam deploy --guided

### Contributing

If you have suggestions or improvements, please create a pull request or open an issue.