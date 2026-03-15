# Deployment Microservices Linkedin Clone - Kubernetes & Minikube

This repository demonstrates the deployment of a containerized application using Minikube, Docker, Kubernetes.

## 1. Build and Push Docker Image

We use the jlib Google plugin to build and push Docker images.

**Steps:**

```bash
./mvnw clean package -DskipTests
```

After building, the image is pushed to Docker Hub.



**Screenshot:** Docker Hub Image

## 2. Start Minikube

Start a local Kubernetes cluster using Minikube:

```bash
minikube start
```

This sets up the local Kubernetes environment.

**Screenshot:** Minikube Running in Docker Desktop

## 3. Apply Kubernetes Configurations

Apply all Kubernetes manifests inside the `k8s` directory:

```bash
kubectl apply -f k8s/
```

This creates all necessary deployments, services, and configurations.

## 4. Minikube Dashboard

Start the Minikube dashboard to monitor your cluster:

```bash
minikube dashboard
```

the dashboard will open in your default browser.

**Screenshot:** Minikube Dashboard 

## 5. Kafka UI 

The application also integrates Kafka for messaging. Access the Kafka UI to monitor topics and messages.

**Screenshot:** Kafka UI 

## Additional Notes 
Ensure Minikube and Docker Desktop are installed and running.djust your Kubernetes manifests if needed before applying.or faster packaging, Maven skips tests with `-DskipTests`; remove this option if you want to run tests.
