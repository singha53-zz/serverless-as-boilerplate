# Alexa Skill boilerplate using serverless (on a Mac)

Assumes: node (brew install node), serverless (npm i serverless -g) are installed

The is repo shows how to set up an Alexa Skill using the serverless framework using AWS.

## Step 1a: set up AWS credentials for IAM user
  - Users -> Add user --> example name: SKILL_NAME-sls
  - enable **Programmatic acess**
  - create policy with **Admin access**
  - Download credentials.csv and store in a SAFE place!

## Step 1b: configure the Serverless Framework to use AWS API KEY and Secret
```
serverless config credentials --provider aws --key ACCESS_ID --secret SECRET
```
## Step 2: create new service
  - to see available templates (NOTE: serverless is the same as sls)
```
sls create --help
```
  - use NodeJS
```
sls create --template aws-nodejs --path SERVICE_NAME
```
  - you should get the following message:
```
 _______                             __
|   _   .-----.----.--.--.-----.----|  .-----.-----.-----.
|   |___|  -__|   _|  |  |  -__|   _|  |  -__|__ --|__ --|
|____   |_____|__|  \___/|_____|__| |__|_____|_____|_____|
|   |   |             The Serverless Application Framework
|       |                           serverless.com, v1.44.1
 -------'

Serverless: Successfully generated boilerplate for template: "aws-nodejs"
```
## Step 3: add new event (trigger lambda functions)
  - modify *functions* of the serverless.yml file (make sure to get the indentation correct):
from
```
functions:
  hello:
    handler: handler.hello
```
to
```
functions:
  hello:
    handler: handler.hello
    events:
      - alexaSkill
      - http:
          path: hello/world
          method: get
```

