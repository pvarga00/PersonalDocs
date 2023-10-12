
CIRCLE CI:

[https://circleci.foc.zone/](https://circleci.foc.zone/)

[https://confluence/display/circleci](https://confluence/display/circleci)



## Please follow this workflow for git:

<ac:link><ri:page ri:space-key="~pvarga" ri:content-title="The Brain GIT Workflow"></ri:page></ac:link>

When about to merge, please re-base and run tests again to verify that rebase hasn't broken tests.



#### <u>Setting up CircleCI for your branch/fork:</u>

##### Step One:

Go to circleci. Switch to your personal user view (Top left corner)

##### <ac:image ac:height="400"><ri:attachment ri:filename="image2018-11-19_11-43-55.png"><ri:page ri:space-key="~pvarga" ri:content-title="Code Review Process Meeting Notes"></ri:page></ri:attachment></ac:image>

##### Step Two:

Make sure that you are "following" the project that you want circleci to run on whenever you push code to your fork/branch. For this case it would be "Liftoff-ProcessEngine". CircleCI should setup an initial process and try to go through the build process. It should fail on a step that doesn't have environment variables setup:

<ac:image ac:height="250"><ri:attachment ri:filename="image2018-11-19_11-45-40.png"><ri:page ri:space-key="~pvarga" ri:content-title="Code Review Process Meeting Notes"></ri:page></ri:attachment></ac:image>

##### Step Three:

To allow for the process engine to resolve Camunda mvn dependencies, you will need the camunda login information setup in CircleCI for your fork. In your Circleci user repository, click the **gear** icon while in the "workflows" view. Go to "Environment Variables" and setup the CAMUNDA\_USER and CAMUNDA\_PASSWORD credentials. These are the same that used for local development [setup](https://confluence/display/BRAIN/Updating+Camunda+for+Devs). (You may have to refresh the page to verify variables saved)

<ac:image ac:thumbnail="true" ac:height="181"><ri:attachment ri:filename="image2018-11-19_11-47-9.png"><ri:page ri:space-key="~pvarga" ri:content-title="Code Review Process Meeting Notes"></ri:page></ri:attachment></ac:image><ac:image ac:height="250"><ri:attachment ri:filename="image2018-11-19_11-47-23.png"><ri:page ri:space-key="~pvarga" ri:content-title="Code Review Process Meeting Notes"></ri:page></ri:attachment></ac:image>

##### Step Four:

When opening a pull request (on a branch or master) Circleci will try to go through the workflow for that branch. You should check that any new changes don't break the build process:

<ac:image ac:height="250"><ri:attachment ri:filename="image2018-11-19_11-51-50.png"><ri:page ri:space-key="~pvarga" ri:content-title="Code Review Process Meeting Notes"></ri:page></ri:attachment></ac:image>



Other notes:

- Please try to work off of branches rather than master. This is due to how circleci filters out different branches and what steps will run
- **Please do not add any environment variables other than the Camunda Maven dependency information**(This only applies to your circle ci workflows)



