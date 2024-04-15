# CI/CD Pipeline with Monitoring for Django Notes App

This repository contains a Jenkins pipeline script (written in Groovy) for Continuous Integration and Continuous Deployment (CI/CD) of a Django Notes App. Additionally, it integrates monitoring using Prometheus and Grafana to provide enhanced observability of the deployment process.

## Pipeline Overview

The pipeline automates the following stages:

1. **Clone Code:** Clones the code from the GitHub repository.
2. **Build:** Builds a Docker image for the Django Notes App.
3. **Push to Docker Hub:** Tags and pushes the Docker image to Docker Hub.
4. **Deploy:** Updates the deployed container on an EC2 instance using Docker Compose.

## Monitoring Overview

Additionally, Prometheus and Grafana monitoring tools are integrated into the pipeline to monitor the health and performance of the deployment.

## Pipeline Stages

- **Clone Code:** Git is used to clone the code from the specified GitHub repository.
- **Build:** Docker is used to build the Docker image named `my-app`.
- **Push to Docker Hub:** The Docker image is tagged and pushed to Docker Hub using provided credentials.
- **Deploy:** Docker Compose is used to manage the deployment on an EC2 instance in AWS.

## Monitoring Setup

To enable monitoring, follow these steps:

1. **Install Prometheus:**
   - Create a system user and directories for configuration files and libraries.
   - Download and extract Prometheus files.
   - Move the configuration file, binaries, and create a service file for Prometheus.
   - Reload system and start Prometheus.

2. **Install Node Exporter:**
   - Download and extract Node Exporter files.
   - Move the binary file, create a Node Exporter user, and custom service file.
   - Reload system and start Node Exporter.

3. **Install Grafana:**
   - Download GPG keys, add them to trusted keys list.
   - Add Grafana repository to package sources, update packages, and install Grafana.
   - Start and enable Grafana service.
   - Access Grafana in the browser, set username and password, and update password for security.
   - Access Grafana dashboard to monitor Node Exporter metrics.

## How to Run

1. Set up Jenkins and configure necessary credentials.
2. Create a new pipeline job in Jenkins.
3. Copy and paste the provided Groovy script into the pipeline configuration.
4. Save the pipeline job and manually trigger the build, or set up webhooks for automatic triggering.

## Notes

- Ensure that the specified AWS EC2 instance is running and accessible.
- Make sure Docker Compose is installed on the EC2 instance.
- Adjust the GitHub repository URL and branch as needed.
- Customize Docker image names and tags according to your requirements.
