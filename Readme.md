# Jenkins Pipeline for Docker Image Build and Push

This Jenkins Pipeline script automates the process of building a Docker image from a provided Dockerfile and pushes it to Docker Hub. The pipeline consists of three stages: Git Checkout, Build Docker Image, and Push to Docker Hub.

## Prerequisites

- Jenkins installed and configured with necessary plugins (e.g., Docker, Git).
- A Dockerfile located at the specified path (`path/to/your/Dockerfile`).
- A GitHub repository with the Dockerfile and any other necessary files to build the Docker image.
- A Docker Hub account and credentials to log in and push the Docker image.

## Instructions

1. **Configure Environment Variables**: Before running the pipeline, make sure to set the following environment variables in Jenkins:

   - `DOCKERFILE_PATH`: The path to your Dockerfile inside the repository.
   - `DOCKER_IMAGE_NAME`: The Docker image name in the format `your-dockerhub-username/your-image-name`.
   - `DOCKER_HUB_CREDENTIALS`: Jenkins Global credential name for Docker Hub to authenticate during the push.

2. **Create Jenkins Pipeline**: Create a new Jenkins pipeline job and copy-paste the provided script into the Jenkinsfile section of the pipeline configuration.

3. **Configure GitHub Credentials**: Make sure to set up the GitHub credentials (`your-github-credentials`) in Jenkins to allow the pipeline to access the GitHub repository.

4. **Run the Pipeline**: Trigger the pipeline manually or set up a webhook to automatically trigger the build whenever changes are pushed to the repository.

5. **Build and Push Docker Image**: The pipeline will automatically check out the repository, build the Docker image, and push it to Docker Hub using the provided credentials.

6. **Cleanup**: After the image is pushed to Docker Hub, the pipeline will remove the locally built Docker image to clean up the system resources.

> **Note**: It is essential to ensure that the Jenkins server has access to Docker and necessary permissions to perform Docker-related operations during the pipeline execution.

> **Disclaimer**: This pipeline is provided as a reference and may require adjustments based on your specific setup and requirements.
