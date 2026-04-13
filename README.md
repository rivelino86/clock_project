# Deploy containerized application to EC2 VM using Github Actions.

## The Current Issue

The Dev Team is developing an application and need to do a quick test on their Dev EC2 machine before submitting it for testing. This application is a html based application that will ultimately be deployed on a kubernetes cluster. 

Their current process is to make updates to the application, build a Docker image on the Dev EC2 machine, then spin up a container using the new image. Once the application looks good on the browser, they will then send a notification to the QA team to start testing. This process takes a few days because different team members are in charge of different aspects of this process.

As a DevOps Engineer, this project is to simplify and automate the process using GitHub Action as the Build and Automation tool. Once the developer sends the application to the repository, we need to have a pipeline triggered that will build the docker image, push to the repository (so we have a versioned copy), deploy to Dev EC2 and ready for the developer to view his changes on the browser in minutes rather than days.

## Requirements:
To keep with best practices and organizational policy, please note

- We need the EC2 VM to only give access to the required port 8085 for the application (in addition to port 22)
- Consider scanning the code and image with SonarQube and Trivy respectively - for this step, run a SonarQube container with access on port 9000
- We need to secure sensitive information throughout the CI/CD process
- We need to manage variable values in a way that makes it easier to change
- Make sure GitHub Actions access to AWS account is secure using best practices - OIDC preferred to Access/Secret Keys
- Image will be sent to your private repository so you have a secure copy - look into AWS ECR
- We need to ensure your Dev EC2 can communicate with your ECR to pull the newly created images - IAM AWS Service role


## Aim for success:

The plan is for a hands-on learning experience. There is more opportunity to learn from this project if you have the basic understanding of what is going on. Before the project, research on why it is important to use CI/CD pipelines instead of manual workflows. That way, you can build on your knowledge and understand how to explain the concepts in an interview. 

Be ready to follow along on your computer, troubleshoot on the spot and take lots of notes and screenshots of your work for your revision. 
