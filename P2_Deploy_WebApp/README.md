## Deploy WebApp

Deploy infrastructure/web server using CloudFormation

  <img src="https://github.com/na6an/CDevOps/blob/master/P2_Deploy_WebApp/img/diagram.png" alt="alt text">  
* The diagram is created in ppt with the default aws template provided here: https://aws.amazon.com/architecture/icons/

### The Basics  
# Parameters  
Here it has parameters for VPC, 2 public subnets and 2 private subnets.  
All parameter values are in `parameter.json` for easier reference instead of hard-coding.

# Resources  
Recources contains all LoadBalancer, Launch Configuration, AutoScaling, Security Groups, Listener and Target Group.

# Outputs  
  <img src="https://github.com/na6an/CDevOps/blob/master/P2_Deploy_WebApp/LB.PNG" alt="alt text">  
As you see, the stack is active in the load balancers page although it's not accessible through DNS address because it's connected to private subnets.

# 



[d1er9qy4ujpu4y.cloudfront.net](https://d1er9qy4ujpu4y.cloudfront.net)

The S3 bucket in the AWS Management console.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P1_Deploy_Static_Website/img/bucket_creation.PNG" alt="alt text">  
  
# Web Browser Access  
The CloudFront endpoint URL:  
[d1er9qy4ujpu4y.cloudfront.net](https://d1er9qy4ujpu4y.cloudfront.net)

