# API Gateway Private Integrations

## What is a VPC Link?

A VPC Link is a resource in Amazon API Gateway that allows you to connect your API to private resources inside a Virtual Private Cloud (VPC) in AWS. This enables secure communication between API Gateway and your backend services, such as applications running on EC2 instances, load balancers, or other services within the VPC. VPC Links are crucial for scenarios where you want to expose private applications through a public-facing API while maintaining network security and control.

## Explore More: In-Depth Analysis of VPC Links

For a thorough exploration of the patterns and best practices involved in API Gateway private integrations featured in this repository, we recommend reading the comprehensive article series by Serverless Guru:

- [Private Integrations in Amazon API Gateway: A Guide](https://www.serverlessguru.com/blog/deep-dive-into-vpc-links-in-amazon-api-gateway)

This series offers detailed insights into VPC links, demonstrating how they can be leveraged to enhance security and scalability in your AWS API integrations.

## Additional Resources and Deployment Guides

This repository is organized into several components, each with its own deployment instructions. To get started, refer to the relevant README files:

1. **[Shared Resources ReadMe](./SharedResources-ReadMe.md)**: Includes instructions for deploying the foundational VPC and EC2 resources. These resources are used by both the HTTP API and REST API integrations.

2. **[HTTP API ReadMe](./HttpApi-ReadMe.md)**: Provides step-by-step instructions for deploying the HTTP API and the Application Load Balancer (ALB) to create a secure, private integration with your backend services.

3. **[REST API ReadMe](./RestApi-ReadMe.md)**: Offers guidance on deploying the REST API and the Network Load Balancer (NLB) to establish a private integration with your backend services.

By following the instructions in each of these README files, you can set up and configure the necessary infrastructure and API Gateway integrations to meet your specific use case.




