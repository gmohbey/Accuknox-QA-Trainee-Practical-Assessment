# Problem Statement 1 : Accuknox QA Trainee Practical Assessment/Problem Statement 1/wisecow-app
Objective: To containerize and deploy the Wisecow application, hosted in the above-mentioned GitHub repository, on a Kubernetes environment with secure TLS communication.

End Goal: The successful containerisation and deployment of the Wisecow
application to the Kubernetes environment with an automated CI/CD pipeline and
secured with TLS communication.

# CI/CD Pipeline Configuration for Wisecow Application

## Overview
This document outlines the CI/CD pipeline configuration for deploying the Wisecow application using GitHub Actions.

## Components
- **Source Code**: [GitHub Repository](https://github.com/nyrahul/wisecow)
- **Dockerfile**: Located in the `Problem Statement 1/wisecow-app/k8s` directory.
- **Kubernetes Configuration Files**:
  - `wisecow-deployment.yaml`
  - `wisecow-service.yaml`
  - `wisecow-ingress.yaml`
  - `tls-secret.yaml`
- **GitHub Actions Workflow**: `.github/workflows/ci-cd-for-wisecow-app.yaml`

## Workflow Steps
1. **Code Commit**: Changes are pushed to the `main` branch.
2. **Build Docker Image**: The Docker image is built using the Dockerfile.
3. **Push Docker Image**: The image is pushed to the GitHub Container Registry.
4. **Deploy to Kubernetes**: The application is deployed using the Kubernetes manifest files.
5. **Verify Deployment**: Ensure the application is running and accessible.


# CI-CD for Wisecow Application "ACHIEVED GOAL"

This document outlines the CI/CD pipeline for the Wisecow application, detailing the steps for building, pushing, and deploying the Docker image, as well as  wisecow application supports secure TLS communication,deploying the application on a Kubernetes cluster.

## Build and Push

### 1. Set up job
This step initializes the CI job. It defines the environment, triggers, and conditions for running the CI/CD pipeline.

### 2. Checkout code
This step checks out the latest code from the repository, ensuring the pipeline works with the most recent version of the application.

### 3. Set up Docker Buildx
Docker Buildx is set up to enable advanced Docker build capabilities, such as multi-platform image building.

### 4. Log in to GitHub Container Registry
Logs in to GitHub's Container Registry to authenticate the pipeline, enabling the process to push Docker images to the container registry.

### 5. Build Docker image
Builds the Docker image of the Wisecow application using the latest code and specified Dockerfile in the repository.

### 6. Push Docker image
Pushes the built Docker image to the GitHub Container Registry, making it available for deployment.

### 7. Post Set up Docker Buildx
Cleans up or finalizes any Docker Buildx-related tasks after the image has been pushed.

### 8. Post Checkout code
Cleans up after the code checkout step, releasing any resources or temporary files.

### 9. Complete job
Finalizes the job and marks the build-and-push section as complete. All logs are reviewed, and the job status is updated.

---

## Deploy

### 1. Set up job
This step initializes the deployment job, defining the environment, triggers, and conditions for the deployment of the Wisecow application.

### 2. Checkout code
This step checks out the latest code from the repository to deploy the most recent version of the Wisecow application.

### 3. Install Kind
Installs **Kind** (Kubernetes in Docker), a tool for running local Kubernetes clusters using Docker.

### 4. Create Kind cluster
Creates a local Kubernetes cluster using Kind for deployment testing and validation.

### 5. Check Kubernetes cluster info
Displays and verifies the current Kubernetes cluster configuration, ensuring that the cluster is correctly set up before deployment.

### 6. Generate self-signed TLS certificate
Generates a self-signed TLS certificate for secure communication, which will be used by the Wisecow application.

### 7. Create TLS Secret
Creates a Kubernetes secret to securely store the generated TLS certificate, which is required for the Wisecow application to run with HTTPS.

### 8. Deploy Wisecow App
Deploys the Wisecow application to the Kubernetes cluster, using the newly created TLS certificate and secret for secure communication.

### 9. Post Checkout code
Cleans up after the code checkout step, releasing any resources or temporary files.

### 10. Complete job
Finalizes the deployment process. The job status is updated, and the cluster is ready for application testing or further operations.

---

## Conclusion

This CI/CD pipeline automates the process of building, pushing, and deploying the Wisecow application, ensuring seamless and efficient deployment using Kubernetes and secure TLS communication.
