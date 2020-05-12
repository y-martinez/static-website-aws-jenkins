# Jenkins Pipelines on AWS

## Problem



## Project Requirements

> #### AWS Setup

|CRITERIA|MEETS SPECIFICATIONS|COMPLETED|GRADED|
|---|---|---|---|
|Set up IAM credentials properly| A new user with EC2 and S3 access is created that is not the root/admin user in AWS. A screenshot with the unique AWS URL showing should be provided.|||
|Launch EC2 instance|An Ubuntu 18.04 t2.micro is launched and can be accessed via SSH using the PEM file. A screenshot with the unique AWS URL showing should be provided.|||

> #### Running Jenkins

|CRITERIA|MEETS SPECIFICATIONS|COMPLETED|GRADED|
|---|---|---|---|
|Jenkins is installed and running|The Jenkins instance can be reached over HTTP publicly, a login screen should show if not logged in. A screenshot with unique AWS url should be provided.|||
|'Blue Ocean' is enabled|The 'Blue Ocean' link should show in the sidebar and should load its interface, which is completely different from the standard Jenkins. A screenshot with unique AWS url should be provided.|||
|Barebones Pipeline is added|The GitHub repository is added and shows in the BlueOcean dashboard, automatically recognizing the Jenkinsfile and setting up the initial pipeline that has 1 stage. A screenshot with unique AWS url should be provided.|||

> #### Working Pipeline

|CRITERIA|MEETS SPECIFICATIONS|COMPLETED|GRADED|
|---|---|---|---|
|Publishes the static site to S3|The index.html file is published to the correct bucket in the right region, and the url is accessible via HTTP from anywhere. A screenshot with unique AWS url should be provided.|||
|Linter catches issues with HTML|After adding a linter, it catches HTML problems with the sample index.html, after addressing the problems with the html, the job passes and publishes the contents once again - build is passing. A screenshot with unique AWS url should be provided.|||
|Jenkinsfile is demonstrated|A Jenkinsfile exists, that has the stages and steps defined that match how the pipeline looks in the Jenkins dashboard. For example 'stage('Lint HTML')' should show as  'Lint HTML' in the pipeline. The AWS credentials and bucket name should all map to an existing S3 bucket that is publicly accessible and that it displays the contents of the index.html file. A screenshot with the S3 URL should be provided.|||

## Solution

> ### Diagram

![Diagram](/docs/Project_3_Udacity_CDE_nanodegree.png)