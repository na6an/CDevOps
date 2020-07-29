[![CircleCI](https://circleci.com/gh/na6an/Microservice.svg?style=svg)](https://circleci.com/gh/na6an/Microservice)


Note
This page is for submission report only because I want to keep all projects of each nanodegree in a single repo.
All code work can be found in https://github.com/na6an/Microservice so it can run it's own in CircleCI.


## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

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