# CircleCI pipeline to deploy your application on AKS

## Overview
This CircleCI pipeline automates the deployment of a Dockerized application on Azure Kubernetes Service (AKS). The pipeline consists of two main jobs: **buildAndPush** and **deployment**. The buildAndPush job builds the Docker image of the application, pushes it to Docker Hub, and triggers the deployment to AKS.

## Requirements
- [CircleCI account](https://circleci.com/)
- [Azure account](https://portal.azure.com/)
- [Docker Hub account](https://hub.docker.com/)

## Setup
### 1. Environment Variables
Make sure to set the following environment variables in your CircleCI project settings:

- **DOCKERHUB_USERNAME**: Your Docker Hub username.
- **docker_password**: Your Docker Hub password.
- **client_id, client_secret, tenant_id**: Azure service principal credentials.
- **subscription**: Azure subscription ID.

### 2. CircleCI Configuration

**`.circleci/config.yml`**<br>
Use config.yml file from this repository and commit it to your github project.

**Note** - Use Image in place of <docker_image> which have all the configuration installed (eg. Azure CLI)

## Workflow
- The **buildAndPush** job is triggered on each push to the repository. It builds the Docker image, pushes it to Docker Hub, and caches the Docker layers for future builds.
- The **deployment** job is triggered after the **buildAndPush** job. It deploys the updated image to the AKS cluster using Kubernetes manifests.<br>
- Adjust the placeholders (<...>) in the configuration to match your specific project details and file paths.

That's it! You now have a CircleCI pipeline for deploying your Dockerized application to Azure Kubernetes Service.


