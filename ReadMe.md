# HTTP API VPC Links for Private Integrations
This project demonstrates how to use AWS HTTP API VPC Links for API Gateway private integrations. It includes all the necessary AWS resources and configurations to create a private, secure integration between an API Gateway and an internal web application hosted on an EC2 instance behind an Application Load Balancer (ALB).

## Overview
The repository is organized into the following directories:

1. `vpc/`: Contains a SAM template to create a VPC with public and private subnets.
2. `ec2/`: Contains a SAM template to create a private/internal EC2 instance running an Apache server. This web application will be used to test the private integration.
3. `alb/`: Contains a SAM template to create an internal Application Load Balancer (ALB).
4. `http-api/`: Contains a SAM template to build the API Gateway HTTP API and the VPC link.

## Prerequisites
Before deploying the resources, ensure you have the following installed and configured:

- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)
- Python virtual environment (e.g., [Conda](https://docs.conda.io/projects/conda/en/stable/))
- [AWS Credentials](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) set up to deploy to your AWS environment

## Deployment Instructions
Each directory contains a template.yaml (SAM template) and a samconfig.toml file to predefine parameters for the SAM CLI. The resources must be deployed in the following order:

1. **VPC**: Navigate into the `vpc/` directory and run the following commands:
    ```bash
    sam package
    sam deploy
    ```

2. **EC2**: Navigate into the `ec2/` directory and run the same commands:
    ```bash
    sam package
    sam deploy
    ```

3. **ALB**: Navigate into the `alb/` directory and run the same commands:
    ```bash
    sam package
    sam deploy
    ```

4. **HTTP API**: Navigate into the http-api/ directory and run the same commands:
    ```bash
    sam package
    sam deploy
    ```
## Post-Deployment Steps
After deploying the resources, update the ALB security group's inbound rule to only accept traffic on port 80 from the VPC link security group. Redeploy the ALB stack.

This ensures that only requests routed through the API Gateway can reach the web application.

## Testing the Integration
Once everything is deployed and configured:

Open a web browser.
Invoke the API Gateway HTTP API endpoint.
If everything is configured correctly, you should see the page load with the message: "Welcome to the HTTP Server".

## Note on Custom Stages
The solution described in this project works with the `$default` stage in API Gateway. To define a custom stage, additional steps are required. Please refer to the [AWS documentation on Private Integrations](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-develop-integrations-private.html#:~:text=secure%20server%20name.-,Note,-For%20private%20integrations) for further instructions.

