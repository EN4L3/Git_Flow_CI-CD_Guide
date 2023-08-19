# Git_Flow_CI-CD_Guide

# GitFlow: Ngrok, Jenkins & Docker CI/CD Guide

This guide provides step-by-step instructions for setting up an automated CI/CD workflow using Jenkins and Docker from a local host. It covers the integration of ngrok for webhook testing and provides a comprehensive walkthrough of the entire process.


## Prerequisites

Before you begin, make sure you have a basic understanding of terminal commands.

## Installation and Setup

Follow the steps in this section to set up your Jenkins and Docker environment.
Docker: Install Docker
ngrok: Install Ngrok

#Pull the Jenkins image from Docker Hub by running the following command:

docker pull jenkins/jenkins:lts-jdk11

#Start a Jenkins container using the following command:

docker run -p 8081:8080 -p 50000:50000 -v en4l3_home:/var/en4l3_home --name en4l3-Jen jenkins/jenkins:lts-jdk11

docker volume ls

docker ps -a

#Integrating ngrok
Open a terminal and navigate to the directory where ngrok is installed.
Run the following command to create a secure tunnel to your Jenkins instance:

ngrok http 8081 - same port mapped to Jenkins container:



## Webhook Integration
Configure GitHub Webhook

In your Jenkins web interface,follow set up steps and create username and password.
Create New Item, Free Projectnavigate-Name your project set up with a GitHub webhook.

Scroll down to the "Build Triggers" section and select "GitHub hook trigger for GITScm polling."
Paste your git repo link

Save your changes.
Integrate ngrok and GitHub webhooks for testing and automation. Test your setup by triggering webhook events.
Create or Edit a file in your repo.


## Contact

For questions or feedback, you can reach out to en4l3

## References
https://docs.docker.com/desktop/install/ubuntu/
https://ngrok.com/docs/getting-started/
https://www.jenkins.io/doc/book/installing/linux/
https://octopus.com/blog/jenkins-docker-install-guide

