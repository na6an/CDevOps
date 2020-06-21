## Jenkins Pipelines on AWS  
Deploy and run an EC2 instance on AWS, configure Jenkins, and create a multi-branch pipeline to deploy a static website on S3.  

#### Note  
This page is for submission report only because I want to keep all projects of each nanodegree in a single repo.  
All code work can be found in https://github.com/na6an/JenkinsPipeline so it can run it's own in Jenkins.  

#### Pipeline structure  
JenkinsPipeline is a multi-branch pipeline with 3 branches: master, dev, and prod.  
All 3 branches contains same Jenkinsfile that has 4 stages.  
First two are default stages used in course material: 1. "Build" and 2. "Lint HTML"  
The third is the dev test stage, 3. "Dev Test", that uploads the static website from Project 1 to S3 as a dev test.  
`dev_script.sh` simply git clone the whole CDevOps repo, then s3Upload uploads P1 directory with `path:'P1_Deploy_Static_Website/'`.  
At last, the fourth stage is the production stage, 4. "Prod, upload given", that uploads the given html file to the S3.  

So, basically in summary,  
master - stage 1, 2  
dev - stage 1, 2, 3  
prod - stage 1, 2, 4  


### AWS Setup  
#### IAM Credential
IAM role with EC2 and S3 access created.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-01.png" alt="alt text">  
  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/IAM%20log-in.png" alt="alt text">  
  
#### EC2 instance  
An Ubuntu 18.04 t2.micro is launched and can be accessed via SSH using the PEM file.

  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-02.png" alt="alt text">  

### Running Jenkins  
#### Jenkins installed and running   
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-03.png" alt="alt text">  

#### Blue Ocean  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-04.png" alt="alt text">  

#### Pipeline is added
The GitHub repository is added and shows in the BlueOcean dashboard  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-05.png" alt="alt text">  

### Working Pipeline  
#### Publishes the static site to S3  
statis sites are published to S3.  
Remember from the note, entire P1 was also added as a result of Dev test stage.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-06.png" alt="alt text">  

#### Linter catches issues with HTML  
There are 2 issues with HTML known - wrong bracket and tidy installation.  
In the github repo, bracket issue was already fixed.  
I don't want to roll back to that commit and come back, so the capture of tidy issue presented here.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-07.png" alt="alt text">  

#### Jenkinsfile demonstration  
Pipelines of all 3 branches described in the Note above.   
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-08-master.png" alt="alt text">  

  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-08-dev.png" alt="alt text">  

  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-08-prod.png" alt="alt text">  

