# Alexa Skill boilerplate using serverless (on a Mac)

Assumes: node (brew install node), serverless (npm i serverless -g) are installed

The is repo shows how to set up an Alexa Skill using the serverless framework using AWS.

# Step 1a: set up AWS credentials for IAM user
  - Users -> Add user --> example name: SKILL_NAME-sls
  - enable **Programmatic acess**
  - create policy with **Admin access**

# Step 1b: set up AWS credentials for IAM user
```
serverless config credentials --provider aws --key ACCESS_ID --secret SECRET
```
