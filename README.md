# Full-CI-CD-Pipeline
A complete creation of CI CD Pipeline using GitHub, Jenkins, Maven, SonarQube, creating a docker image and pushing it on DockerHub.   Then take the updated Image and push it to a seperate Git Folder, SetUp a Kubernetes cluster with ArgoCD for continuous Deployment.

Step 1:
Set up GitHub:

   Created a repository on GitHub to store your application code.
   Commit and push your code to the repository.

Step 2:
Set up AWS resources:

   Create an EC2 instance (I have used t2.large). 
   SetUp VPC, a public subnet
   Created a Secutity Group with Inbound rules for:
             Jenkins: Port 8080
             SonarQube: Port 9000
             Docker Port 2375 
             ArgoCD: Port 8080
             Kubernetes: Port 6443
             SSH: 22
             HTTPS: 443

Step 3:
Configure Jenkins:

   Installed and configure Jenkins on an EC2 instance
   Installed required plugins: Git, Pipeline, AWS, Docker, SonarQube
   Configured GitHub Webhook for triggering Jenkins
   
Step 4:
Written the Jenkinsfile for my Pipieline from the create pipeline
 
           Written line for creating image with Maven and Docker.
           SetUp Maven for clean Package
           SonarQube testing for code quality
           Creation of Docker image and pushed to DockerHub.

Step 5:
SetUp of Continuous Deployment in Kubernetes

         Shell Script will Notify Git Repository to update its files with the new files from the DockerHub.
         New .yaml file is pushed to git to commit change.
         This is then Pushed to Kubernetes with ArgoCD to complete the Pipeline.
         
.........................................................................................................................
  
  
               
