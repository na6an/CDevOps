## Deploy Static Website on AWS

A static website (given in this project directory) to AWS using S3, CloudFront, and IAM.

### Website Files Specification  
The S3 bucket in the AWS Management console.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P1_Deploy_Static_Website/img/bucket_creation.PNG" alt="alt text">  
  
Screenshot of the website files uploaded to the S3 bucket.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P1_Deploy_Static_Website/img/bucket_upload.PNG">  

The S3 bucket configured to support static website hosting.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P1_Deploy_Static_Website/img/bucket_hosting.PNG">
Webhost address:
http://nathan-udacity-static-website.s3-website.us-east-2.amazonaws.com

The S3 bucket has an IAM bucket policy that makes the bucket contents publicly accessible.  
Note that policy is created with policy generator.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P1_Deploy_Static_Website/img/bucket_policy.PNG">

# Website Distribution  
CloudFront has been configured to retrieve and distribute website files.  
  <img src="https://github.com/na6an/CDevOps/blob/master/P1_Deploy_Static_Website/img/Website_distribution.PNG">
  
# Web Browser Access  
The CloudFront endpoint URL:  
d1er9qy4ujpu4y.cloudfront.net
