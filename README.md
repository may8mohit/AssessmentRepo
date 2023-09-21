# AssessmentRepo


# Terraform deployment - host a stateless application in AWS


Steps to be performed are as follows:

Created a docker file and used https://hub.docker.com/r/nginxdemos/hello/ and create a basic index.html page

build the image and ran the docker container in the local machine and then used http://localhost:8080 to confirm if the container is running properly.

create a user Terraform_ECS and downloaded the access credentials.

The next steps I performed:

Started creating the main.tf file for Terraform, the following resources I created using the terraform scripts

provided AWS resource provider from hasicorp

added default AWS region and IAM access keys 

created an AWS ECR repository in AWS, before continuing to next steps, push docker image from local to ECR repo.

created AWS ECS cluster and ECS task definition and add a parameter for the ECR repo image uri

created a IAM role for ECS to execute the task execution

added the VPC ,Subnets and Application Load Balancer in the file

created SG for the LB for the ports required for the application to run 

created LB listners and target groups

created ECS app service with launch type Fargate and desired count as 3 and added the network configurations by passing subnet details and Security Groups.

created a security group for the aws services so that traffic is only allowed from the LB security group.

added the output parameter to get the LB url to open the application




After creation of the main.tf file, we may run run the below commands on terraform:

terraform validate (to check if all is good in the main.tf file)

terraform plan (to see all the resources that are getting created)

terraform apply (to create all the resources in AWS)




