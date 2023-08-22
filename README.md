# Git_Flow_CI-CD_Guide

# GitFlow: Ngrok, Jenkins & Docker CI/CD Guide

This guide provides step-by-step instructions for setting up an automated CI/CD workflow using Ngrok, Jenkins and Docker from a local host. It covers the integration of ngrok for webhook testing and provides a comprehensive walkthrough of the entire process.


## Prerequisites

Before you begin, make sure you have a basic understanding of terminal commands.

## Installation and Setup

Follow the steps in this section to set up your environment.

Docker: Download and Install Docker:
![docker-install](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/3d61b5fc-2435-48e3-8ab7-5b68cbabf06a)

#Pull the Jenkins image from Docker Hub by running the following command:
docker pull jenkins/jenkins:lts-jdk11
docker images
![jenkins-image](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/1e4990bd-cad1-4b5b-9a56-b1aa2e8f7360)

#Start a Jenkins volume and container using the following command:
docker run -p 8081:8080 -p 50000:50000 -v en4l3_home:/var/en4l3_home --name en4l3-Jen jenkins/jenkins:lts-jdk11
docker volume ls
docker ps -a
![jenkins-container](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/f3c3b96c-f242-4f50-8c2d-29f2298760fe)
![jenkins-admin](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/70361aab-b42b-4017-a2fb-2dc732cb3d2e)


#Setup and Integrating Ngrok:
Ngrok: Download and Install Ngrok:
![ngrok-install](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/de8691f0-160b-49b4-b182-e203b64f2bfb)

Open a terminal and navigate to the directory where ngrok is installed.
Run the following command to create a secure tunnel to your Jenkins instance:
ngrok http 8081 - same port mapped to Jenkins container:
![ngrok-cmd](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/f3449de6-7147-4d22-b38e-c86a15d2a672)

In your Jenkins web interface,follow set up steps and create username and password.
Create New Item, Free Project - Name your project set up with a GitHub webhook.
![Jenkins-Logins](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/21f04793-01ee-4721-a6d6-d3e1890eb057)
![Jenkins-New_Item](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/ca7e46d2-d432-43fc-a3c9-790264b27395)

Scroll down to the "Build Triggers" section and select "GitHub hook trigger for GITScm polling."
Paste your git repo link
![Jenkins_Page](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/feacf163-132f-41fe-a66b-8e0b2febdb29)
![Jenkins_Page2](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/a066ea54-cfe4-48cd-894d-5b0fc2c7cc1d)
![Jenkins-Page2a](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/79333221-28ad-4ce0-a460-d24ead2cd9be)
![Jenkins-Page3](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/98527d1f-37df-4508-af54-01d8b2eabef7)

Save your changes.

## Webhook Integration
Configure GitHub Webhook:
![webhook-settings](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/efd554b4-72a2-4b15-979b-d0bfd86cd461)
#Integrate Ngrok and GitHub webhooks for testing and automation. Test your setup by triggering webhook events.
![Ping_test_webHook](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/7c92a05f-2d42-4508-a99c-5ff24662bde9)

#Create or Edit a file in your repo.
![Test_file_to_edit](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/fda74721-998b-4357-a973-f7fadff0568f)
![Commit_readme](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/b74e06f8-33c9-463c-8e45-b250ec3136d3)


##STATUS
![ngrok-status](https://github.com/EN4L3/Git_Flow_CI-CD_Guide/assets/123630651/59210810-8015-4dad-9e93-035a92c79613)


## Contact

For questions or feedback, you can reach out to en4l3

## References
https://www.kali.org/docs/containers/installing-docker-on-kali/
https://docs.docker.com/desktop/install/ubuntu/
https://ngrok.com/docs/getting-started/
https://www.jenkins.io/doc/book/installing/linux/
https://octopus.com/blog/jenkins-docker-install-guide

