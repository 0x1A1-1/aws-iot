# AWS-IOT
===========
Steps for creating lambda function for Alexa Skill Set

* Amazon Echo/ Alexa Skill Set
* AWS account

AWS console Setup
------------------
Console[https://console.aws.amazon.com/lambda]
Login and create a new custom lambda fucntion

1. Zip up and upload the js file in this folder for starting. 
2. Creat app name and set app handler to index.handler
3. The "Role" is the Identity and Access Management (IAM) role for the associated Lambda function. Choose " Basic Execution Role." 
4. Once the function is created, click on the "Event Sources" tab and add an "Alexa" event source.

Adding the ASK configuration
--------------------------------
Once the Lambda function is configured.

1. Log in to the Amazon Echo Skills Console and click "Get Started" under the Alexa Skills Kit.
2. Set name, invocation name (what users will say to activate your application), version string and the endpoint for the application. For the endpoint, get the APN number in your AWS console.
3. For the Intent Schema, copy in the content of intent file in this folder
4. Next setup is the "Sample Utterances," which helps Alexa determine which intent to fire and what text to add to each argument.

Enable incoming webhooks in Slack:
----------------
You’ll also need to enable incoming webhooks (requests) in your Slack channel
  Copy and paste the credential from webhook url to the js file in AWS console

Try it!
--------
1. Invoke your Alexa by saying "Alexa +[ur invoking name]"
2. Say" send What's for lunch? "
3. Go to your slack channel and enjoy your swag
