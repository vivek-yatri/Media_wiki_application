
# MEDIAWIKI PROBLEM STATEMENT
To automate the deployment of MediaWiki using. Kubernetes with Helm Chart/ any equivalent automation with own Dockerfiles for application and database. Terraform or any IaC tool with any Configuration Management tool integrated. Choose only one of your comfort. The above automation should support CI/CD practices of chosen deployment style like Rolling Update or BlueGreen Deployment.


# SOLUTION STATEMENT
To automate the deployment of MediaWiki in AWS using Kubernetes with Helm chart, using our own Dockerfiles for the application and database, and incorporating Blue-Green deployment (Using Jenkins) in a CI/CD pipeline, follow the below step-by-step instructions:

{Advantage of using this approach - It provides flexibility and allows you to customize the deployment according to your specific requirements.}

High level overview of the assignment:

Set up the AWS infrastructure:

Create an Amazon EKS cluster to host your Kubernetes cluster.
Set up the required AWS resources like VPC, subnets, security groups, and IAM roles.
Install and configure Jenkins:

Launch an EC2 instance to host Jenkins.
Install Jenkins and set up necessary plugins and configurations.
Configure Jenkins to access your AWS resources.
Create Docker images:

Write Dockerfiles for the MediaWiki application and database.
Build and tag the Docker images for both components.
Push the Docker images to a container registry (e.g., Amazon ECR).
Set up Helm chart for MediaWiki:

Create a Helm chart with the necessary configurations for the MediaWiki deployment.
Customize the chart to use your Docker images for both the application and the database.
Configure Blue-Green deployment in the Helm chart:

Modify the Helm chart to support Blue-Green deployment.
Create two sets of Kubernetes resources:one for the "blue" environment and another for the "green" environment.
Set up Ingress or a Load Balancer to handle traffic routing between environments.
Set up Jenkins Pipeline:

Create a Jenkins Pipeline in your MediaWiki project repository.
Define stages for the CI/CD pipeline, including building Docker images, deploying to "green" environment, switching traffic.
Integrate AWS services in the pipeline:

Use AWS CLI within your Jenkins Pipeline to interact with AWS services.
Trigger the Jenkins Pipeline:

Configure webhook triggers to start the pipeline whenever there are changes to the MediaWiki project repository.
Execute the CI/CD pipeline:

Save and run the Jenkins Pipeline to initiate the deployment process.
Jenkins will build the Docker images, deploy the "green" environment, run tests, switch traffic, and clean up the "blue" environment automatically.
By following these steps, you can automate the deployment of MediaWiki in AWS using Kubernetes with Helm chart, your own Dockerfiles, and the Blue-Green deployment approach in a CI/CD pipeline.