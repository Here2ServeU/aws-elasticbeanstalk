# Step-by-Step Guide to Using Amazon Elastic Beanstalk On CLI

## Step 1: Set Up Your AWS Account
  -> Sign Up: If you don't have an AWS account, sign up at aws.amazon.com.
  -> IAM Users and Roles: Create IAM users and roles with appropriate permissions to use Elastic Beanstalk.


## Step 2: Install the AWS CLI and EB CLI
  -> AWS CLI: Install the AWS CLI.
  -> EB CLI: Install the EB CLI.


## Step 3: Create an Elastic Beanstalk Application

### Initialize the Application: 

eb init



## Step 3: Create and Deploy an Environment

### Create an Environment: 

eb create <environment-name>


### Deploy Your Application: 

eb deploy



## Managing Environments

### List Environments: 

eb list


### Open Environments: 

eb open


### Terminate Environments: 

eb terminate <environment-name>


# If deployment fails, SSH into the instance for troubleshooting
eb ssh

# Check logs for errors
sudo cat /var/log/eb-engine.log
sudo cat /var/log/eb-activity.log
sudo cat /var/log/web.stdout.log
sudo cat /var/log/web.stderr.log
