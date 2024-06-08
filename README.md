# Step-by-Step Guide to Using Amazon Elastic Beanstalk Using the AWS CLI

## Step 1: Set Up Your AWS Account
  -> Sign Up: If you don't have an AWS account, sign up at aws.amazon.com.
  
  -> IAM Users and Roles: Create IAM users and roles with appropriate permissions to use Elastic Beanstalk.


## Step 2: Install the AWS CLI and EB CLI
  -> AWS CLI: Install the AWS CLI.
  
  -> EB CLI: Install the EB CLI.


## Step 3: Create an Elastic Beanstalk Application

### Create the required working directory: 

  -> mkdir eb-nodejs

  -> cd eb-nodejs

### Initialize the Application: 

  -> eb init


## Step 3: Create and Deploy an Environment

### Create an Environment: 

  -> eb create <environment-name>


### Deploy Your Application: 

  -> eb deploy


## Managing Environments

### List Environments: 

  -> eb list


### Open Environments: 

  -> eb open


### Terminate Environments: 

  -> eb terminate <environment-name>

---------------------------
## Working with Node.js Applications

#### Step 1: Create a project directory
  -> mkdir eb-nodejs
  
  -> cd eb-nodejs

#### Step 2: Creating an Application to deploy
  -> nano server.js

  Add the following content: 
    
    const http = require('node:http');

    const hostname = '127.0.0.1';
    const port = 8080;

    const server = http.createServer((req, res) => {
      res.statusCode = 200;
      res.setHeader('Content-Type', 'text/plain');
      res.end('Hello Elastic Beanstalk!\n');
    });

    server.listen(port, hostname, () => {
      console.log(`Server running at http://${hostname}:${port}/`);
    });

  The application will open a listener on port 8080, and Elastic Beanstalk will forward requests to the application on port 8080 by default for Node.js. 


#### Step 3: Test your application locally
   -> node server.js

You will see this: 
    **Server running at http://127.0.0.1:8080/**


#### Step 4: Deploy your Node.js application with the EB CLI

  -> eb init 

  The command will initialize your EB CLI repository with the "eb init" command. Follow the prompts. 


#### Step 5: Create the environment for your App

  -> eb create nodejs-env


#### Step 6: Open your website App

  -> eb open

     The above command will open the Application on a Web browser. 


  --> curl http://nodejs-env.eba-xqpgtp47.us-east-1.elasticbeanstalk.com/ 
     
     You get this from the Environments Dashboard under "Domain."

  
#### Step 7: Clean Up

  -> eb terminate

--------
# If deployment fails, SSH into the instance for troubleshooting
eb ssh

# Check logs for errors
sudo cat /var/log/eb-engine.log

sudo cat /var/log/eb-activity.log

sudo cat /var/log/web.stdout.log

sudo cat /var/log/web.stderr.log


--- 
Documentation: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html
