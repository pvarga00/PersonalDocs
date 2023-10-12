
In order to deploy to Amazon infrastructure, you must first set up the infrastructure. With new Liftoff standards, all infrastructure setup is done through code. This is known as infrastructure as code, aka Terraforming.

When terraforming, use a separate repo to do hold your infrastructure code and have a HAL app set up for it. HAL manages the deployment of this code, which results in your infrastructure being set up in AWS.

# Git Repo - API infrastructure

## Setup your Terraform repo with the ECS-API module

1. Clone [https://git.rockfin.com/terraform/terraform-starter-kit](https://git.rockfin.com/terraform/terraform-starter-kit) repo to start your terraform project
2. Create the terraform repo for your project. (For Copilot BFF, we are using [https://git.rockfin.com/liftoff-iac/copilot-bff-api](https://git.rockfin.com/liftoff-iac/copilot-bff-api) )
3. Copy the contents of the terraform starter kit to your repo
4. Rename the folder named "1234567890" to the Liftoff Nonprod account number in AWS (661865515693)
5. Find the appropriate terraform script you want to use in [https://git.rockfin.com/terraform](https://git.rockfin.com/terraform) (In most cases, this will be [https://git.rockfin.com/terraform/aws-ecs-app-tf](https://git.rockfin.com/terraform/aws-ecs-app-tf) - this script is used to deploy a docker container as an ECS service on an ECS cluster in AWS)
6. Navigate to the appropriate module for your project (In most cases, this will be in **modules/****ecs-api**in the [https://git.rockfin.com/terraform/aws-ecs-app-tf](https://git.rockfin.com/terraform/aws-ecs-app-tf) repo. Some repos may have the module in the root folder.)
7. Within the module folder, navigate to examples/default to find your example terraform.tfvars file and copy that file.
8. Create a folder in the 661865515693/us-east-2/test directory with your app name here. (Example for copilot bff- 661865515693\us-east-2\test\copilot-bff-api)
9. Paste the terraform.tfvars file from step 7 into that directory.
10. Edit the terraform.tfvars file's placeholder content with the information specific to your app. Use the following values for vpc\_id and subnet\_ids

    1. vpc\_id = "vpc-088c47f3b0a342bcd"
    2. subnet\_ids = [ "subnet-0ec91e0e7974b5653", "subnet-07626e952914c9536" ]
11. Check line 1 of the terraform.tfvars file and specify the latest version of the terraform starter module you are referencing here.
12. Specify test as the environment in the terraform.tfvars file.
13. Perform steps 8-12 using beta as the environment
14. Push your changes to the terraform repo.




# HAL


## Configure HAL to deploy infrastructure

1. Create a HAL app for your infrastructure repo and put it under the AWS - Liftoff Organization
2. Additional details for HAL app entry:
    1. Provider: AWS
    2. Platform: Infrastructure as Code
    3. Language: Terraform
3. Go to Configure Deployments → Manually Add Deployment Target
4. Under AWS, click test-aws or beta-aws
    1. Server or Service type: Script
    2. Name: "Your app name here"
    3. URL: Can be blank
    4. Script Context: Name of the last folder you created for your app in Terraform Step 7. (copilot-bff-api in the case of the Copilot BFF)
5. Go to Manage Application → Edit Application
6. Scroll down to Required Build Parameters and add two parameters: "module" and "region"


## Build infrastructure


1. You can now start your build in HAL. When you start the build, it will ask you for a module and region. Module is the name of the last folder you created in Terraform Step 7. (**copilot-bff-api** for example.) Region is **us-east-2**.
2. Once your build is complete, contact a System Engineer to have them deploy the build. Deploying the build should result in your API infrastructure being created.




# API Gateway Setup


## Add the API Gateway module to your Terraform repo

1. Create a folder in the 661865515693/us-east-2/test directory with your app name here and the suffix "-gw". (Example for copilot bff- 661865515693\us-east-2\test\copilot-bff-api-gw)
2. Copy the terraform.tfvars file from here [https://git.rockfin.com/terraform/aws-apigw-lambda-proxy-tf/blob/master/examples/default/terraform.tfvars](https://git.rockfin.com/terraform/aws-apigw-lambda-proxy-tf/blob/master/examples/default/terraform.tfvars) into your -gw directory
3. Edit the terraform.tfvars file's placeholder content with the information specific to your app. Use the following values for vpc\_id and subnet\_ids

    1. vpc\_id = "vpc-088c47f3b0a342bcd"
    2. subnet\_ids = [ "subnet-0ec91e0e7974b5653", "subnet-07626e952914c9536" ]
4. Check line 1 of the terraform.tfvars file and specify the latest version of the terraform starter module you are referencing here.
5. Specify test as the environment in the terraform.tfvars file.
6. Ask a System Engineer for and r53\_zone\_id and stage\_address for your application
7. Overwrite the custom\_domain entry with your custom url that contains "test" and ends with ".foc.zone"
8. Perform steps 1-7 using beta as the environment and have "beta" in the url
9. Push your changes to the Terraform Repo


## Build Gateway infrastructure


1. Build your infrastructure code in HAL. Use the folder name you created in step 1 of the Gateway setup step as the module, (**copilot-bff-api-gw**for example.) Region is **us-east-2**.
2. Once your build is complete, contact a System Engineer to have them deploy the build. Deploying the build should result in your gateway being created.






Reference material:

[https://git.rockfin.com/liftoff-iac/copilot-bff-api](https://git.rockfin.com/liftoff-iac/copilot-bff-api) Copilot BFF API Infrastructure code repo

[https://hal9000.rockfin.com/applications/1476](https://hal9000.rockfin.com/applications/1476)Copilot BFF API Infrastructure HAL App


