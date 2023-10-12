
PreReq: Assuming Your Solution is cloned and available in your local and your solution has config.yml file under .circleci folder

- Go to your solution in local and open config.yml file using any of the Editors
- Add this Sonar Step in config.yml file and make sure you change your file path for your Test Project according to your solution structure
- Add this step under Jobs in config.yml file



| sonar-scanner: |
| --- |
| <br> | docker: |
| <br> | - image: [qldockerdtr.rockfin.com/jcherry/dotnet:2.1-sdk-openjdk](http://qldockerdtr.rockfin.com/jcherry/dotnet:2.1-sdk-openjdk) |
| <br> | <br> |
| <br> | working\_directory: /app |
| <br> | <br> |
| <br> | environment: |
| <br> | - SONAR\_URL: [https://sonarqube.rockfin.com](https://sonarqube.rockfin.com) |
| <br> | - CORE\_ID: 202926 |
| <br> | <br> |
| <br> | steps: |
| <br> | - \*enterprise\_setup |
| <br> | - checkout |
| <br> | - run: |
| <br> | name: Download sonar tool |
| <br> | command: dotnet tool install dotnet-sonarscanner --tool-path ~/tools |
| <br> | - run: |
| <br> | name: Run sonar scanner |
| <br> | command: | |
| <br> |  ~/tools/dotnet-sonarscanner begin /k:"QL.$CORE\_ID" /n:"LOD Listener" /v:"$CIRCLE\_SHA1" /d:sonar.host.url="$SONAR\_URL" /d:sonar.login="$SONAR\_TOKEN" /d:sonar.cs.opencover.reportsPaths="\*\*/coverage.opencover.xml" /d:sonar.cs.vstest.reportsPaths="\*\*/TestResults/testresults.trx" |
| <br> |  dotnet build ./LODListenerTests/LODListenerTests.csproj --configuration release  |
| <br> |  dotnet test ./LODListenerTests/LODListenerTests.csproj --configuration release --logger "trx;LogFileName=testresults.trx" /p:CollectCoverage=true /p:CoverletOutputFormat=opencover  |
| <br> |  ~/tools/dotnet-sonarscanner end /d:sonar.login="$SONAR\_TOKEN |




- Add Sonar step under workflow in config.yml,notice Sonar step,workflow will look like this for most



| workflows: |
| <br> | version: 2 |
| <br> | pipeline: |
| <br> | jobs: |
| <br> | - build |
| <br> | - sonar-scanner: |
| <br> | requires: [ build ]  |
| <br> | - publish\_build\_to\_hal: |
| <br> | requires: [ sonar-scanner ] |
| <br> | filters: |
| <br> | branches: |
| <br> | only: master  |
| <br> | - deploy\_test: |
| <br> | requires: [ publish\_build\_to\_hal ] |
| <br> | - approve\_deploy\_beta: |
| <br> | requires: [ deploy\_test ] |
| <br> | type: approval |
| <br> | - deploy\_beta: |
| <br> | requires: [ approve\_deploy\_beta ] |


- Save config.yml file
- Now Go to your solution in Visual Studio
- Add Coverlet Package using Manage Nuget to all the Projects
- Add following three lines to all .cs project in your solution under &lt;PropertyGroup&gt;,make sure GUID should be unique for each .cs project


&lt;CopyLocalLockFileAssemblies&gt;true&lt;/CopyLocalLockFileAssemblies&gt;
    &lt;IsPackable&gt;false&lt;/IsPackable&gt;
    &lt;ProjectGuid&gt;GUID values&lt;/ProjectGuid&gt;

- Go to CirceCI and under your Project→Gear icon settings→ Click on Environment Variables and add following values for these


SONAR\_URL= [https://sonarqube.rockfin.com](https://sonarqube.rockfin.com/)

SONAR\_TOKEN = **f396b04e64ef68e4592268db828db4945dbb74d3**

CORE\_ID = Your CoreID

- Once all the changes are done request for PR
- Once Changes are merged go to circleci and look at your project CI/CD pipeline,make sure pipeline is working showing sonar layer with no errors







