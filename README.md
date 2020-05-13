# seedsgateway-iac# Seeds Gateway Infrastructure as Code

This is an **AWS CodeBuild** pipeline for the SeedsGateway project. It creates a variable number of **AWS CloudFormation** stacks (Depending on environments) that create **AWS Lambdas** and **AWS API Gateways** depending on a file in the back-end repository called "*template.yaml*".

## Components
### Parameters
A series of parameters the person using the stack should provide, such as: **Project name**, **Stage**, **Code Locations** and **Default Branches**.

### What this creates:

 - Back-end CodeBuild project
	 - Continuous deployment (On merges)
 - Front-end CodeBuild Project
	 - Continuous Integration (On pull requests)
	 - Continuous Deployment (On merges)
 - S3 Bucket for build artifacts
 - S3 Bucket for website deployment

### Privileges
This **AWS CodeBuild** stack needs to assume a role so that it can have proper privilege to create and delete those resources on the spot. The stack creates the role on it is on, it just needs to be run with a user who has higher privileges so that the stack created by him can be granted a privilege to assume such role.
 
