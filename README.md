# CircleCI pipeline to deploy your application on AKS

## Overview
This CircleCI pipeline automates the deployment of a Dockerized application on Azure Kubernetes Service (AKS). The pipeline consists of two main jobs: buildAndPush and deployment. The buildAndPush job builds the Docker image of the application, pushes it to Docker Hub, and triggers the deployment to AKS.
