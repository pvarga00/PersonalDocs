
The purpose of this documentation is to give a good overview of what it takes to fully deploy an application to the LiftOff ECS cluster. There are several parts to deploying an application and all should be covered in this page or in subsequent sub-pages.



<u><strong>Table of Contents</strong></u>

<ac:structured-macro ac:name="toc" ac:schema-version="1" ac:macro-id="df6bf3a7-24b3-4fc0-a985-edff091cd95a"><ac:parameter ac:name="style">square</ac:parameter></ac:structured-macro>

# **Terraform**
<ac:structured-macro ac:name="panel" ac:schema-version="1" ac:macro-id="d672f48e-a8ac-4c68-8857-3e172727dce2"><ac:parameter ac:name="titleBGColor">#36B37E</ac:parameter><ac:parameter ac:name="borderStyle">solid</ac:parameter><ac:parameter ac:name="title">Resource Links</ac:parameter><ac:rich-text-body><ul><li><a href="https://confluence/display/Cloud/Terraform">QuickenLoans Terraform Confluence</a></li><li><a href="https://git.rockfin.com/terraform">QuickenLoans Terraform Git Repository</a></li><li><a href="https://www.terraform.io/intro/index.html">HashiCorp Terraform Documentation</a></li></ul><ul><li><a href="https://git.rockfin.com/LiftOff-iac">LiftOff IAC Git Repository</a></li></ul></ac:rich-text-body></ac:structured-macro>



> So you have your application setup and ready to be deployed for the first time? Well here's where the whole DevOp's process starts. The first item on the agenda will be to Terraform your resources in AWS. The current standard for QuickenLoans is to utilize the QL published Terraform modules to requisition AWS services and just provide input variables to that module.




* * *

**Step One:**

Create your a corresponding IAC repository in this [organization](https://git.rockfin.com/LiftOff-iac). There is a naming convention of  **######-app-name**where "######" is the [core id](http://core/) of the application. Adhere to the folder structure located [here](https://git.rockfin.com/liftoff-iac/liftoff-iac-template) as this is how HAL will be locating the particular module to run. When creating specific modules under an environment please use effective names to make it clear what the intended usage of the module is without having to investigate specific code.



* * *

**Step Two:**

For ECS applications, first figure out if your service provides RESTful endpoints or not. If it **does** follow the examples located [here](https://git.rockfin.com/terraform/aws-ecs-app-tf/tree/master/modules/ecs-api) for creating your tfvars module. If it **does not**provide any endpoints (listener, message processor), what you'll want is an ecs-service. You can find examples [here](https://git.rockfin.com/terraform/aws-ecs-app-tf/tree/master/modules/ecs-service).

There is additional documentation for configuring your terraform module located here: <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service API and Gateway Infrastructure Setup for AWS in Test/Beta"></ri:page></ac:link>. Follow the instructions for both *Git Repo - API Infrastructure* and *HAL*. In HAL please make sure your app name is prefixed with iac similar to others in the org. Also make sure the app id you use is a combination of the core id and "iac" (eg. 204140iac or 204140-iac)



* * *

**Step Three:**

When setting up your HAL IAC application for the first time, you will have several options to chose from. Select *Terraform;*it should be the far right option. You will be greeted by the following screen:

<ac:image ac:align="left" ac:height="250"><ri:attachment ri:filename="image2019-5-14_9-54-48.png"><ri:page ri:space-key="~pvarga" ri:content-title="DevOps (Start here!)"></ri:page></ri:attachment></ac:image>



# 


# 


# 


# 


# 




Fill out the module names you created previously containing your tfvars files. Select "test-aws", "beta-aws", and "prod-aws". Make sure the corresponding credentials are correct.

<ac:image ac:height="250"><ri:attachment ri:filename="image2019-5-14_9-59-4.png"><ri:page ri:space-key="~pvarga" ri:content-title="DevOps (Start here!)"></ri:page></ri:attachment></ac:image>

Navigate to the deployment configuration for the specific environment you just created and start a build. The *build parameters* should be filled out based on the module name and region your deploying the module to.

<ac:image ac:height="250"><ri:attachment ri:filename="image2019-5-14_10-1-1.png"><ri:page ri:space-key="~pvarga" ri:content-title="DevOps (Start here!)"></ri:page></ri:attachment></ac:image>

Start the build. Once it's complete (and successful) you should be good to have anyone with proper permissions actually execute the Terraform plan. Once that's done, your app should be requisitioned in AWS and be ready to access deployments!



# **HAL**
<ac:structured-macro ac:name="panel" ac:schema-version="1" ac:macro-id="65b30b5d-0acc-47fd-bffb-5b6a5423b3f9"><ac:parameter ac:name="titleBGColor">#FF7452</ac:parameter><ac:parameter ac:name="borderStyle">solid</ac:parameter><ac:parameter ac:name="title">Resource Links</ac:parameter><ac:rich-text-body><ul><li><a href="https://hal9000.rockfin.com/">HAL9000</a></li><li><a href="https://hal9000.rockfin.com/groups/87">AWS - LiftOff HAL Group</a></li></ul></ac:rich-text-body></ac:structured-macro>



> So AWS is now ready to accept deployments of code. From this point on you'll be dealing with the pure Continuous Integration/Continuous Deployment. First we need to get setup with HAL to setup build definitions to publish and execute deployment builds.




* * *

**Step One:**

Go to [HAL](https://hal9000.rockfin.com/applications) and add an application. Follow the instructions here: <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ac:link>



* * *

**Step Two:**

For multi-region deployments for Beta and Prod in particular, you will need to setup multiple beta-aws and prod-aws HAL definitions. "Repeated" environment setups will be differentiated based on their context value (in this case being us-east-2 or us-west-2)

<ac:image ac:height="250"><ri:attachment ri:filename="image2019-5-14_10-45-39.png"><ri:page ri:space-key="~pvarga" ri:content-title="DevOps (Start here!)"></ri:page></ri:attachment></ac:image>



* * *

**Step Three:**

Take note of the deployment id's you setup for test, beta, and prod. You will need them later for CircleCI.

<ac:image ac:height="250"><ri:attachment ri:filename="image2019-5-14_10-46-21.png"><ri:page ri:space-key="~pvarga" ri:content-title="DevOps (Start here!)"></ri:page></ri:attachment></ac:image>



# **Circle CI and Code**
<ac:structured-macro ac:name="panel" ac:schema-version="1" ac:macro-id="9378a02a-66c6-423d-9454-853400f7aaf4"><ac:parameter ac:name="titleBGColor">#79E2F2</ac:parameter><ac:parameter ac:name="borderStyle">solid</ac:parameter><ac:parameter ac:name="title">Resource Links</ac:parameter><ac:rich-text-body><ul><li><a href="https://git.rockfin.com/LiftOff/liftofflib-cicd">LiftOffLib-CICD Git Repository</a></li><li><a href="https://circleci.com/docs/2.0/configuration-reference/">CircleCI Configuration Documentation</a></li></ul></ac:rich-text-body></ac:structured-macro>
Most of the instructions related to setting up CircleCI and Code is linked here: <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="Pipeline changes to push to BETA"></ri:page></ac:link>



You can also find instructions related to setting up and using Kraken to manage configuration variables located here: <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="Using Kraken and Parameter Store for Secrets"></ri:page></ac:link>


