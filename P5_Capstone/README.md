## Capstone Project: Deploy CV App  
Setup CI/CD pipeline for a Computer Vision (CV) App  

#### Note
This page is for submission report only because I want to keep all projects of each nanodegree in a single repo.  
All code work can be found in https://github.com/na6an/CDevOps_Capstone so it can run it's own in Jenkins.  

#### Background Introduction
A modern warehouse process from tens of thousands to millions of shipments every day.  
Barcode reading - whether from a razer scanner or camera - is a crucial part of the warehouse operation  
but often requires shipment packages to be in a specific position, so it can be read correctly and further processed.  

The purpose of this Computer Vision (CV) app is to check the package position on a (fake) conveyor from pictures taken by a camera.  

For this project submission, however, the CV app is not the essential part of CI/CD pipeline creation and deployment.  
Thus, the CV app will be a functional basecode to demonstrate a proof of concept.  

Here are some examples of what this CV app does:
Original input images:
  <img src="https://github.com/na6an/CDevOps_Capstone/tree/master/img/IMG_20200811_121501.jpg" alt="alt text">  
  <img src="https://github.com/na6an/CDevOps_Capstone/tree/master/img/2020_07_23_10_08_55_color_place.png" alt="alt text">  

Output:
  <img src="https://github.com/na6an/CDevOps_Capstone/tree/master/img_out/IMG_20200811_121501.jpg" alt="alt text">  
  <img src="https://github.com/na6an/CDevOps_Capstone/tree/master/img_out/2020_07_23_10_08_55_color_place.png" alt="alt text"> 



#### Jenkins Pipeline structure  
JenkinsPipeline is a simple multi-branch pipeline with 2 branches that acts like a blue/green deployment: master and dev.  
Both branches contains same Jenkinsfile that has 4 stages.  
First two are default stages used in course material: 1. "Build" and 2. "Lint CV App (Python)"  
Step 3 and 4 are for the multi-branch Blue/Green deployments.  
The third is the dev test stage, 3. "master branch as dev", which tests the app deployment through docker build.  
The last is the deploy test stage, 4. "deploy", which tests the kubernetes deployment.  


### Pipeline Setup  
#### IAM Credential
IAM role with EC2 and S3 access created. (Reuse existing from Project 3)  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-01.png" alt="alt text">  
  
  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/IAM%20log-in.png" alt="alt text">  

#### Github repository
As mentioned in the note section, all code work can be found here:  
https://github.com/na6an/CDevOps_Capstone

#### Docker Image Repository
https://hub.docker.com/repository/docker/na6an/cv-app


### Container Build
#### Command steps in ssh of EC2 instance
From the host computer dir where pem key is stored:  
`ssh -i "[key-name].pem" ubuntu@ec2-[ec2 IP].us-east-2.compute.amazonaws.com`  
`sudo chmod 666 /var/run/docker.sock` #provides docker enough access right   

Install Jenkins in EC2, then go to the browser, enter `[ec2 IP]:8080` to complete the installation.  
Jenkins plug-ins I added:
pipeline AWS steps
CloudBee AWS Credentials
Blue Ocean

Add the IAM credentials in the environment variables.

### Jenkins Troubleshoot
You also might want to add jenkins user to the sudoers file, disable the confirmation prompt when installing a package.  
Otherwise, any package isntallation can exit during the jenkins run, throwing a permission error.  
You can use `add_jenkins.sh` command in this case.


#### Linter as part of a Continuous Integration step  


#### Build docker container in a pipeline  



### Deployment
#### Command steps in ssh of EC2 instance
Get into EC2 by ssh same as above.

Install `kubectl` and `kubectl` in the EC2 instance.

git clone this repo or scp to copy yaml files to EC2.

Add credential info in the `secret.sh` file inside of EC2, `source secret.sh`, then run this sh file by `./secret.sh`.  


`eksctl create cluster -f cluster.yaml`

`kubectl create secret docker-registry regcred --docker-server=https://index.docker.io/v1/  --docker-username=${username} --docker-password=${password} --docker-email=${email}`

`kubectl get secret regcred --output=yaml`

`kubectl apply -f stack.yaml`

`kubectl delete daemonsets,replicasets,services,deployments,pods,rc,secrets --all`

`eksctl delete nathan-udacity-cluster` (replace the name of cluster and edit the name of cluster in the "cluster.yaml" if cluster name is not available)



#### Docker container deployed to a kubernetes cluster
A kubernetes cluster is created and the deployment was made using kubectl command.  


  <img src="https://github.com/na6an/CDevOps/blob/master/P3_Jenkins_Pipeline/pic/screenshot-02.png" alt="alt text">  


#### Blue/Green Deployment



#### Kubernetes Troubleshoot
If the deployment doesn't get ready and you see the status of the pods "CrashLoopBackOff",  
it's likely either:  
1. the secret was not set correctly, or
2. pod exiting too quickly. (See https://stackoverflow.com/questions/31870222/how-can-i-keep-a-container-running-on-kubernetes)

