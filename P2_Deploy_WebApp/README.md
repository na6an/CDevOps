## Deploy WebApp

Deploy infrastructure/web server using CloudFormation

  <img src="https://github.com/na6an/CDevOps/blob/master/P2_Deploy_WebApp/img/diagram.png" alt="alt text">  
* The diagram is created in ppt with the default aws template provided here: https://aws.amazon.com/architecture/icons/

### The Basics  
#### Parameters  
Here it has parameters for VPC, 2 public subnets and 2 private subnets.  
All parameter values are in `parameter.json` for easier reference instead of hard-coding.

#### Resources  
Recources contains all LoadBalancer, Launch Configuration, AutoScaling, Security Groups, Listener and Target Group.

#### Outputs  
`Value: !GetAtt WebAppLB.DNSName` dispalys DNS name in the output

#### Working Test
  <img src="https://github.com/na6an/CDevOps/blob/master/P2_Deploy_WebApp/img/stacks.png" alt="alt text">  

  <img src="https://github.com/na6an/CDevOps/blob/master/P2_Deploy_WebApp/img/udagram.png" alt="alt text">  

### Load Balancer  
#### Target Group, Health Check and Listner
  <img src="https://github.com/na6an/CDevOps/blob/master/P2_Deploy_WebApp/img/target_health.png" alt="alt text">  

### Auto-Scaling  
#### Subnets  
Auto-scaling is using PRIV-NET, but this can be switched to PUB-Net for testing purpose.

#### Machine Spec (EC2 instance)  
EC2 instance is t3.small with 10GB ssd, but t2.micro is also available to be eligible for free-tier and save money.  

#### SSH Key 
`cloudformation-key` should be created as a key. Otherwise, should be disabled by commenting out or delete.  

### Troubleshoot  
In case UserData from LaunchConfiguration didn't apply, aws credential has to be configured for EC2 instances. For the testing purpose, you can also manually execute the UserData code and/or upload udacity.zip and see target group turns to healthy condition.  
Also, make sure to select correct ami image id (especially if you're in different AZ).

