# Operationalize a Machine Learning Microservice API

[![CircleCI](https://circleci.com/gh/na6an/Microservice.svg?style=svg)](https://circleci.com/gh/na6an/Microservice)

Note
This page is for submission report only because I want to keep all projects of each nanodegree in a single repo.  
All code work can be found in https://github.com/na6an/Microservice so it can run it's own in CircleCI.


## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Docker Configuration  
#### Make Lint on Dockerfile
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/make_lint.png">  

#### run_docker.sh & make_prediction.sh
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/run_docker.png">  

#### upload_docker.sh
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/upload_docker.png">  
Able to confirm docker image upload from docker hub  
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/docker_hub.png">  
  
### Kubernetes Configuration
#### kubectl
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/kubectl.png">  
  
#### run_kubernetes.sh
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/run_kub.png">  
  
#### make_prediction.sh
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/make_pred.png">  

### CircleCI Build Result
  <img src="https://github.com/na6an/CDevOps/blob/master/P4_ML_Microservice_API/pic/circleci_build.png">  
