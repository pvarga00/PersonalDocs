
## HAL Setup:

### Create your application's HAL entry and add it to the AWS - Liftoff Organization



HAL is used to deploy to the infrastructure you created in the infrastructure setup step. Just add a HAL app as normal and use these settings.

<ac:image ac:height="400"><ri:attachment ri:filename="cicd0.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>

### Create deployment targets for test and beta



Go to Application Dashboard

<ac:image ac:height="250"><ri:attachment ri:filename="cicd1.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Configure Deployments



<ac:image ac:height="250"><ri:attachment ri:filename="cicd2.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Manually Add Deployment Target

<ac:image ac:height="250"><ri:attachment ri:filename="cicd3.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Select environment. You will need to specify a test environment and a beta environment separately.

<ac:image ac:height="250"><ri:attachment ri:filename="cicd4.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Configure settings for deployment target. Do this for both test and beta.

<ac:image ac:height="400"><ri:attachment ri:filename="cicd5.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



You should now see your deployment targets in the application dashboard. They are now set up correctly in HAL. Click "Change environment" to switch between test and beta.

<ac:image ac:height="250"><ri:attachment ri:filename="cicd6.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Click the top right button in a deploy target to check your deployment target's details

<ac:image ac:height="250"><ri:attachment ri:filename="cicd7.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



You should see a screen like this. Copy the ID from both test and beta targets. This number will be used in the CircleCI setup later.

<ac:image ac:height="250"><ri:attachment ri:filename="cicd8.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



### Create HAL Access Token



CircleCI requires a personal access token from HAL in order to push builds to HAL. Your team may already have one, but if not, follow these steps to create one.

<ac:image ac:height="250"><ri:attachment ri:filename="cicd9.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Give your token a name and select Infrastructure Deployments (This selection may change in the future, but for now, we use this.) Copy the generated token and put it in SecretServer

<ac:image ac:height="228"><ri:attachment ri:filename="cicd10.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>





Put your api key in secret server under "TheBrain/AWS - Liftoff/(Your Appname Here)/(Appname) Nonprod HAL Token."

Resource should be named HAL\_API\_TOKEN

Username should be (appname)-nonprod

Password should be the key from HAL

Be sure to copy the notes section for clarity. CircleCI Administrators will use this to assign variables to the proper places in CircleCI.

You may need to ask someone on the Brain team for access to this SecretServer folder. At time of writing, Evan Parizot and Brian Raheb can grant access to this folder.

<ac:image ac:height="250"><ri:attachment ri:filename="cicd11.PNG"><ri:page ri:space-key="~pvarga" ri:content-title="LiftOff Service CI/CD Setup for Test/Beta using AWS"></ri:page></ri:attachment></ac:image>



Then, contact the Brain team again once your secret is in the folder and ask them to add it as an environment variable to a CircleCI Context with the username you specified in Secret Server. This will allow your CircleCI instance to deploy builds to HAL.



## 
Hal9000 files

1. Reference [https://git.rockfin.com/LiftOff/CoPilot-BFF-api/blob/master/.hal9000.yml](https://git.rockfin.com/LiftOff/CoPilot-BFF-api/blob/master/.hal9000.yml) for a starting point for your Hal9000 file. Simply replace the values in test-aws, beta-aws, and prod-aws with your project's values. i.e. "test-202794-copilot-bff-api" should read "test-YOUR CORE ID-YOUR APP NAME" from your API's terraform.tfvars file. Terraform file reference: [https://git.rockfin.com/liftoff-iac/copilot-bff-api/blob/master/661865515693/us-east-2/test/copilot-bff-api/terraform.tfvars](https://git.rockfin.com/liftoff-iac/copilot-bff-api/blob/master/661865515693/us-east-2/test/copilot-bff-api/terraform.tfvars)
2. Reference [https://git.rockfin.com/LiftOff/CoPilot-BFF-api/tree/master/.hal](https://git.rockfin.com/LiftOff/CoPilot-BFF-api/tree/master/.hal) for the files that should go in a folder called ".hal" in your project's base directory. These are deployment instructions for HAL.






## CircleCI Setup

Use the following template to set up your CircleCI jobs. Your project should be in the Liftoff organization for access to its context environment variables. The only environment variable you should have to manually enter is your SONAR\_TOKEN

```

```

### Top Level


> version: 2
> 
> machine:
>   services:
>     - docker


### Shared Jobs and Config

Overwrite anything in red with your project-specific settings




> netcore: &netcore
>   docker:
>     - image: **halplatform/hal-build-environments:dotnet2.1-debian8**
> 
> netcore\_sonar: &netcore\_sonar
>   docker:
>     - image: **qldockerdtr.rockfin.com/jcherry/dotnet:2.1-sdk-openjdk**
> 
> enterprise\_setup\_step: &enterprise\_setup\_step
>   run:
>     name: 'Prepare Enterprise Setup'
>     command: 'curl -sL "https://tools.circleci.foc.zone/install-certs" | bash -'
> 
> attach\_workspace\_step: &attach\_workspace\_step
>   attach\_workspace:
>     at: '.'
> 
> persist\_workspace\_step: &persist\_workspace\_step
>   persist\_to\_workspace:
>     root: '.'
>     paths: [ '.' ]
> 
> restore: &restore
>   run:
>     name: restore
>     command: dotnet restore -s https://api.nuget.org/v3/index.json -s https://qugetgal.rockfin.com/api/v2 --disable-parallel
> 
> # We do not need to persist the whole workspace for the hal build, we only need the build\_id
> persist\_hal\_build\_id\_to\_workspace: &persist\_hal\_build\_id\_to\_workspace
>   persist\_to\_workspace:
>     root: '.'
>     paths: [ '.hal\_build\_id\_test', '.hal\_build\_id\_beta' ]
> 
> publish\_build\_to\_hal\_job: &publish\_build\_to\_hal\_job
>   working\_directory: '~/project'
>   docker: [ { image: 'qldockerdtr.rockfin.com/circleci/hal-integration:hal-publisher'} ]
> 
> deploy\_nonprod\_job: &deploy\_nonprod\_job
>   docker: [ {image: 'qldockerdtr.rockfin.com/circleci/hal-integration:hal-publisher'} ]
>   steps:
>     - \*attach\_workspace\_step
>     - run: 'deploy-to-hal-passive-only'
>     - \*persist\_hal\_build\_id\_to\_workspace
> 
> deploy\_prod\_job: &deploy\_prod\_job
>   docker: [ {image: 'qldockerdtr.rockfin.com/circleci/hal-integration:hal-publisher'} ]
>   steps:
>     - \*attach\_workspace\_step
>     - run: 'deploy-to-hal'
> 
> 
> build\_and\_push\_image: &build\_and\_push\_image
>   docker:
>     - image: circleci/python:3.6.1
>   steps:
>       - \*attach\_workspace\_step
>       - \*enterprise\_setup\_step
>       - setup\_remote\_docker
> 
>       - run:
>           name: Set environment variable
>           command: |
>             echo 'export FULL\_IMAGE\_NAME="${AWS\_ACCOUNT\_ID}.dkr.ecr.${AWS\_DEFAULT\_REGION}.amazonaws.com/${ECR\_REPOSITORY}:${CIRCLE\_SHA1}"' &gt;&gt; $BASH\_ENV
> 
>       - run:
>           name: Build Docker image
>           command: |
>              cd **FOLDER\_CONTAINING\_DOCKER\_FILE** && docker build -t $FULL\_IMAGE\_NAME .
> 
>       - restore\_cache:
>           key: v1-awscli-deps
>       - run:
>           name: Install AWS CLI
>           command: |
>             python3 -m venv venv
>             . venv/bin/activate
>             pip install --upgrade pip
>             pip install awscli
>       - save\_cache:
>           key: v1-awscli-deps
>           paths:
>             - "venv"
> 
>       - run:
>           name: Configure AWS Access
>           command: |
>             . venv/bin/activate
>             aws configure set aws\_access\_key\_id $AWS\_ACCESS\_KEY\_ID --profile "Liftoff-Circle"
>             aws configure set aws\_secret\_access\_key $AWS\_SECRET\_ACCESS\_KEY --profile "Liftoff-Circle"
> 
>       - run:
>           name: Push image
>           command: |
>             . venv/bin/activate
>             eval $(aws ecr get-login --region $AWS\_DEFAULT\_REGION --no-include-email)
>             docker push $FULL\_IMAGE\_NAME




### Define Workflow

Overwrite anything in red with your project-specific settings


> workflows:
>   version: 2
>   pipeline:
>     jobs:
>       - build
>       - unit\_tests:
>           requires: [build]
>       - sonar\_scanner:
>           requires: [build]
>       - sonar\_validator:
>           requires: [unit\_tests, sonar\_scanner]
>       - publish\_build:
>           requires: [sonar\_validator]
> # ---------------------------------------------------
> # TEST
> # ---------------------------------------------------
>       - approval\_for\_test:
>           requires: [ publish\_build ]
>           type: approval
>           filters:
>             branches:
>               only:
>                 - master
> 
>       - build\_and\_push\_image\_test:
>           requires: [approval\_for\_test]
>           context: 'circleci-ecr-user'
>           filters:
>             branches:
>               only:
>                 - master
> 
>       - publish\_build\_to\_hal\_test:
>           requires: [build\_and\_push\_image\_test]
>           context: '**CIRCLECI CONTEXT FOR YOUR HAL API KEY**'
>       - deploy\_test:
>           requires: [publish\_build\_to\_hal\_test]
>           context: '**CIRCLECI CONTEXT FOR YOUR HAL API KEY**'
> 
> # ---------------------------------------------------
> # BETA
> # ---------------------------------------------------
> 
>       - approval\_for\_beta:
>           type: approval
>           requires: [deploy\_test]
>           filters:
>             branches:
>               only:
>                 - master
> 
>       - build\_and\_push\_image\_beta:
>           requires: [approval\_for\_beta]
>           context: 'circleci-ecr-user'
> 
>       - publish\_build\_to\_hal\_beta:
>           requires: [build\_and\_push\_image\_beta]
>           context: '**CIRCLECI CONTEXT FOR YOUR HAL API KEY**'
> 
>       - deploy\_beta:
>           requires: [publish\_build\_to\_hal\_beta]
>           context: '**CIRCLECI CONTEXT FOR YOUR HAL API KEY**'




### Define Jobs

Overwrite anything in red with your project-specific settings


> jobs:
>   build:
>     &lt;&lt;: \*netcore
>     steps:
>       - checkout
>       - \*enterprise\_setup\_step
>       - \*restore
>       - run: dotnet build **PROJECT FILENAME**
>       - \*persist\_workspace\_step
> 
>   unit\_tests:
>     &lt;&lt;: \*netcore
>     steps:
>       - \*attach\_workspace\_step
>       - \*enterprise\_setup\_step
>       - \*restore
>       - run:
>           name: 'Run unit tests'
>           command: 'dotnet test **TESTS PROJECT FILENAME** --filter Category!=Integration'
> 
>   sonar\_scanner:
>     &lt;&lt;: \*netcore\_sonar
>     working\_directory: ~/app/src
>     environment:
>       - SONAR\_URL: https://sonarqube.rockfin.com
>       - CORE\_ID: **CORE-ID**
>     steps:
>       - \*attach\_workspace\_step
>       - \*enterprise\_setup\_step
>       - run:
>           name: Download sonar tool
>           command: dotnet tool install dotnet-sonarscanner --tool-path ~/tools
>       - run:
>           name: Run sonar scanner
>           command: |
>             ~/tools/dotnet-sonarscanner begin /k:"QL.$CORE\_ID" /n:"$CIRCLE\_PROJECT\_REPONAME" /v:"`cat ~/app/env/build_number`" /d:sonar.host.url="$SONAR\_URL" /d:sonar.login="$SONAR\_TOKEN" /d:sonar.cs.opencover.reportsPaths="\*\*/coverage.opencover.xml" /d:sonar.cs.vstest.reportsPaths="\*\*/TestResults/testresults.trx" $(if [ -n "$CIRCLE\_PR\_NUMBER" ]; then echo /d:sonar.pullrequest.branch=\"$CIRCLE\_PR\_USERNAME/$CIRCLE\_BRANCH\" /d:sonar.pullrequest.key=$CIRCLE\_PR\_NUMBER; fi)
>             dotnet restore  -s https://api.nuget.org/v3/index.json -s https://qugetgal.rockfin.com/api/v2 --disable-parallel
>             dotnet build --configuration Release
>             dotnet test **TESTS.PROJECT.FOLDER/TESTS.PROJECT.FILE** --configuration Release --logger "trx;LogFileName=testresults.trx" /p:CollectCoverage=true /p:CoverletOutputFormat=opencover
>             ~/tools/dotnet-sonarscanner end /d:sonar.login="$SONAR\_TOKEN"
>       - \*persist\_workspace\_step
> 
>   sonar\_validator:
>     docker: [ {image: 'circleci/openjdk:8-jdk-browsers'} ]
>     steps:
>       - \*attach\_workspace\_step
>       - run:
>           name: 'Validate sonar quality gate'
>           command: |
>             sudo apt-get install python-pip
>             sudo pip install requests
>             python .circleci/sonar-check.py
> 
>   publish\_build:
>     &lt;&lt;: \*netcore
>     steps:
>       - \*attach\_workspace\_step
>       - \*enterprise\_setup\_step
>       - \*restore
>       - run: dotnet publish **PROJECT FILENAME** --output dist
>       - \*persist\_workspace\_step
> 
>   build\_and\_push\_image\_test:
>     &lt;&lt;: \*build\_and\_push\_image
>     environment:
>       ECR\_REPOSITORY: "**TEST** **VALUE FROM HAL9000 FILE**"
> 
>   publish\_build\_to\_hal\_test:
>     &lt;&lt;: \*publish\_build\_to\_hal\_job
>     environment:
>       - HAL\_APP\_ID: '**YOUR HAL APP ID**'
>       - HAL\_OUTPUT\_FILE: '.hal\_build\_id\_test'
>       - HAL\_ARTIFACT\_PATH: ''
>     steps:
>       - \*attach\_workspace\_step
>       - run:
>           name: 'Publish build to HAL9000'
>           command: 'publish-build-to-hal --environment "test-aws"'
>       - persist\_to\_workspace: { root: '.', paths: [ '.hal\_build\_id\_test']}
>   deploy\_test:
>     &lt;&lt;: \*deploy\_nonprod\_job
>     environment:
>       - HAL\_TARGETS: "**YOUR HAL TEST DEPLOYMENT TARGET ID**"
>       - HAL\_BUILD\_FILE: '.hal\_build\_id\_test'
> 
> 
> # ---------------------------------------------------
> # BETA
> # ---------------------------------------------------
> 
>   build\_and\_push\_image\_beta:
>     &lt;&lt;: \*build\_and\_push\_image
>     environment:
>       ECR\_REPOSITORY: "**BETA****VALUE FROM HAL9000 FILE**"
> 
>   publish\_build\_to\_hal\_beta:
>     &lt;&lt;: \*publish\_build\_to\_hal\_job
>     environment:
>       - HAL\_APP\_ID: '**YOUR HAL APP ID**'
>       - HAL\_OUTPUT\_FILE: '.hal\_build\_id\_beta'
>       - HAL\_ARTIFACT\_PATH: ''
>     steps:
>       - \*attach\_workspace\_step
>       - run:
>           name: Publish build to HAL9000
>           command: publish-build-to-hal --environment "beta-aws"
>       - persist\_to\_workspace: { root: '.', paths: [ '.hal\_build\_id\_beta']}
> 
>   deploy\_beta:
>     &lt;&lt;: \*deploy\_nonprod\_job
>     environment:
>       - HAL\_TARGETS: "**YOUR HAL BETA DEPLOYMENT TARGET ID**"
>       - HAL\_BUILD\_FILE: '.hal\_build\_id\_beta'

