## DevOps Project for Beginners   

[![Image](https://github.com/yankils/Simple-DevOps-Project/blob/master/Devops_course.PNG "DevOps Project - CI/CD with Jenkins Ansible Docker Kubernetes ")](https://www.udemy.com/course/valaxy-devops/?referralCode=8147A5CF4C8C7D9E253F)


# Instructions for the install of Akamai Siteshield in AWS account

## 1) Akamai API Keys creation on SSM Parameters (only needs to deploy in us-east-1, will replicate to us-west-2)
Upon completion of obtaining Akamai API Keys, see link below  

 
 Set environmental variables based on Akamai API Keys  
 
 ```
SET AKAMAI_CREDS_BASE_URL="https://akab-....."
SET AKAMAI_CREDS_CLIENT_TOKEN="akab-qhm...."
SET AKAMAI_CREDS_CLIENT_SECRET="A6mrqDb...."
SET AKAMAI_CREDS_ACCESS_TOKEN="akab-o4v...."
SET AKAMAI_CREDS_SITESHIELD_ID="46...."
```
 
 Deploy Cloudformation template:   
 ```
 nextgen\scripts\regional\akamai-siteshield\akamai_ssm_parameters.yml
 ```
 

## 2) Create IAM Role for Akamai Siteshield Lambda (deploy in us-east-1 and us-west-2)

Deploy Cloudformation template:  
```
nextgen\scripts\regional\akamai-siteshield\iam_siteshield_role.yml
```

## 3) Create Akamai Siteshield Lambda Function, Lambda Trigger and Security Groups (deploy in us-east-1 and us-west-2)  

Pull down latest zip package from GHE and save locally to "...\akamai-siteshield\src\siteshieldlambda.zip"  


Deploy Cloudformation template: 
```
nextgen\scripts\regional\akamai-siteshield\siteshieldsync_stack.yml
```
