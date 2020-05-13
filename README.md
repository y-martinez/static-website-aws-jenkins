# Jenkins Pipelines on AWS

## Problem
In this project, you will build on the skills acquired during this course. You will create and run an instance on AWS, configure Jenkins, and create a pipeline to deploy a static website on S3.

## Project Requirements

> #### AWS Setup

|CRITERIA|MEETS SPECIFICATIONS|COMPLETED|GRADED|
|---|---|---|---|
|Set up IAM credentials properly| A new user with EC2 and S3 access is created that is not the root/admin user in AWS. A [screenshot](#set-up-iam-credentials-properly) with the unique AWS URL showing should be provided.|:heavy_check_mark:||
|Launch EC2 instance|An Ubuntu 18.04 t2.micro is launched and can be accessed via SSH using the PEM file. A [screenshot](#launch-ec2-instance) with the unique AWS URL showing should be provided.|:heavy_check_mark:||

> #### Running Jenkins

|CRITERIA|MEETS SPECIFICATIONS|COMPLETED|GRADED|
|---|---|---|---|
|Jenkins is installed and running|The Jenkins instance can be reached over HTTP publicly, a login screen should show if not logged in. A [screenshot](#jenkins-is-installed-and-running) with unique AWS url should be provided.|:heavy_check_mark:||
|'Blue Ocean' is enabled|The 'Blue Ocean' link should show in the sidebar and should load its interface, which is completely different from the standard Jenkins. A [screenshot](#blue-ocean-is-enabled) with unique AWS url should be provided.|:heavy_check_mark:||
|Barebones Pipeline is added|The GitHub repository is added and shows in the BlueOcean dashboard, automatically recognizing the Jenkinsfile and setting up the initial pipeline that has 1 stage. A [screenshot](#barebones-pipeline-is-added) with unique AWS url should be provided.|:heavy_check_mark:||

> #### Working Pipeline

|CRITERIA|MEETS SPECIFICATIONS|COMPLETED|GRADED|
|---|---|---|---|
|Publishes the static site to S3|The index.html file is published to the correct bucket in the right region, and the url is accessible via HTTP from anywhere. A [screenshot](#publishes-the-static-site-to-s3) with unique AWS url should be provided.|:heavy_check_mark:||
|Linter catches issues with HTML|After adding a linter, it catches HTML problems with the sample index.html, after addressing the problems with the html, the job passes and publishes the contents once again - build is passing. A [screenshot](#linter-catches-issues-with-html) with unique AWS url should be provided.|:heavy_check_mark:||
|Jenkinsfile is demonstrated|A Jenkinsfile exists, that has the stages and steps defined that match how the pipeline looks in the Jenkins dashboard. For example 'stage('Lint HTML')' should show as  'Lint HTML' in the pipeline. The AWS credentials and bucket name should all map to an existing S3 bucket that is publicly accessible and that it displays the contents of the index.html file. A [screenshot](#jenkinsfile-is-demonstrated) with the S3 URL should be provided.|:heavy_check_mark:||

## Solution

> ### Diagram

![Diagram](/img/Project_3_Udacity_CDE_nanodegree.png)

> ### Description
The solution consisted of creating an instance EC2 with Jenkins installed and create a pipeline for deploy a static web on S3 bucket, with a Jenkinsfile, also, we connect to this instance by SSH using a KeyPair. Although in the project requirements it did not say about using a CloudFormation stack, instead it specified that everything had to be created through the AWS console, I decided to use a [CloudFormation stack](#cloudformation-stack) template to create the entire infrastructure, including the instance, the S3 bucket, the user and the group with the associated policies, seemed to be a better way since this way I can practice the knowledge acquired in the previous course and it is all more automated, also I installed Jekins using a docker container with docker-compose.
> ### Files structure
1. The `img` folder has screenshots of the whole process and the diagram solution.
2. The `src` folder has the website files to deploy.
3. The `utils` folder has the code files using to help such as utilities.
4. The `docker-compose` file is used to install a docker container (on EC2 instance created in the stack) with an image of Jenkins.
5. The `stack-template.yml` and `parameters.json` files are uses to deploy the stack in CloudFormation with all the requirements to this project.
6. The `Jenkinsfile` file specifies the stages of pipeline in Jenkins to deploy the webpage, this pipeline is created in a declarative way. There is a [webhook](#github-webhook) that was added to the repository, this is useful because any push active a trigger to deploy in Jenkins automatically.

You can access to the final website deployed using this S3 bucket [link](http://static-app-jenkins.s3-website-us-west-2.amazonaws.com/)

> ### Screenshots

#### Github webhook

![Github webhook](/img/screenshot-00a.png)

#### CloudFormation Stack

![CloudFormation Stack](/img/screenshot-00b.png)

#### Set up IAM credentials properly

![Group created](/img/screenshot-01a.png)


![User created](/img/screenshot-01b.png)


![Login with new user](/img/screenshot-01c.png)


#### Launch EC2 instance

![Instance](/img/screenshot-02.png)


#### Jenkins is installed and running

![First initial](/img/screenshot-03a.png)


![Jenkins dashboard](/img/screenshot-03b.png)


#### Blue Ocean is enabled

![Dashboard](/img/screenshot-04a.png)


![Pipeline blue ocean](/img/screenshot-04b.png)


#### Barebones Pipeline is added

![Pipeline example](/img/screenshot-05.png)


####  Publishes the static site to S3

![Pipeline pusblish 1](/img/screenshot-06a.png)


![Page deployed](/img/screenshot-06b.png)


#### Linter catches issues with HTML

![Errors in pipeline](/img/screenshot-07.png)


#### Jenkinsfile is demonstrated

![Errors fixed](/img/screenshot-08.png)
