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


<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/7b123c03-1d94-4fd3-9ff8-0a27c1830ac9" />

## 2. Start Minikube

Start a local Kubernetes cluster using Minikube:

```bash
minikube start
```

This sets up the local Kubernetes environment.

**Screenshot:** Minikube Running in Docker Desktop

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/b5655355-a1af-405d-aced-0d69c1454109" />

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


<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/4cb3586a-e685-4e45-8729-a3f530d70b92" />
<img width="1366" height="1299" alt="Image" src="https://github.com/user-attachments/assets/90b991a6-4497-4d6a-8e75-0749348fe0b1" />
<img width="1366" height="1057" alt="Image" src="https://github.com/user-attachments/assets/27cbc32c-cf2f-436e-8665-cc99b2fb8183" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/3da1aeb7-e326-42e6-a64f-67be866f11b5" />
<img width="1366" height="1057" alt="Image" src="https://github.com/user-attachments/assets/f3492329-3a76-4c75-a39a-2e5d4db04d63" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/27ebd8e2-9a57-4230-b936-fe2d0d059f47" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/bfeb9489-2109-4277-a9e1-afdf2b0f2ebb" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/271326fa-aa04-472f-90c9-4f0334be075f" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/b3312494-94d9-4d13-84ff-f13ce2234db4" />

## 5. Test Result - Screenshots (Postman & Kafka UI)

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/92041297-2a7d-4625-ba7b-ef1c28b58bbe" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/a05ac167-7dee-413d-9c9e-b867453ebe24" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/c7b69ba9-ee3b-4cfb-9c44-a3718e82f630" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/567458dc-1dc9-418f-98df-d462ac8734cb" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/76c73862-7bf2-4f42-9adf-7f0e47722eee" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/39a3f18c-e9f9-4981-b345-1a08e1f4b3ca" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/fd4a051c-1121-414f-9286-b1c63601fd69" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/0b18f4ec-7094-4340-9541-15819d24f978" />

<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/be17e5df-7200-4a48-9c06-3d0b288f25de" />
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/590a841b-6296-474d-b528-16425dfb7746" />

## Accessing Services in Minikube via Port Forward

When running Minikube using Docker as the driver, sometimes the Minikube IP is not directly accessible in the browser. In this scenario, we can use `kubectl port-forward` to access Kubernetes services locally.

**Command Used:**

```bash
kubectl port-forward -n ingress-nginx svc/ingress-nginx-controller 8080:80
```
