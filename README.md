# Yusuf WebApp - Helm Chart Practical

## About the Project

This is my Helm Chart practical project. I created a simple web application and deployed it on Kubernetes using Docker and Helm.

The main purpose of this project is to understand how Helm Charts work and how we can deploy and update an application in Kubernetes.

## Technologies Used

- Docker
- Kubernetes
- Minikube
- Helm
- NGINX
- HTML and CSS
- Git and GitHub

## Project Structure

```text
Yusuf-Helm-WebApp/
│
├── my-webapp/
│   ├── app/
│   │   └── index.html
│   │
│   ├── templates/
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│   │   ├── _helpers.tpl
│   │   └── other Helm templates
│   │
│   ├── Chart.yaml
│   ├── values.yaml
│   └── Dockerfile
│
└── README.md
```

## Application Details

I created a simple webpage named Yusuf WebApp.

The application contains:
- Welcome page
- Application online status
- Docker information
- Kubernetes information
- Helm information
- NGINX information

The webpage is served using an NGINX Docker container.

## Steps to Run the Project

### 1. Start Minikube

```bash
minikube start --driver=docker
```

### 2. Build Docker Image

```bash
docker build -t yusuf-webapp:v1 ./my-webapp
```

### 3. Load Image into Minikube

```bash
minikube image load yusuf-webapp:v1
```

### 4. Install Helm Chart

```bash
helm install my-webapp ./my-webapp
```

### 5. Check Deployment

```bash
kubectl get deployments
kubectl get pods
kubectl get services
```

### 6. Open Application

```bash
kubectl port-forward service/my-webapp 8081:80
```

Open this URL in your browser:

http://localhost:8081

## Helm Upgrade Demonstration

I also tested the application upgrade using Helm.

First, I made a small change in the webpage and created a new Docker image.

```bash
docker build -t yusuf-webapp:v2 ./my-webapp
```

Loaded the updated image into Minikube:

```bash
minikube image load yusuf-webapp:v2
```

Then I updated the image tag in `values.yaml` from `v1` to `v2`.

Finally, I upgraded the application:

```bash
helm upgrade my-webapp ./my-webapp
```

### Check Upgrade History

```bash
helm history my-webapp
```

The application was successfully upgraded from version v1 to v2.

## Useful Helm Commands

```bash
helm list
helm status my-webapp
helm history my-webapp
helm get values my-webapp
helm lint ./my-webapp
```

## GitHub Repository

https://github.com/yusufali110/Yusuf-Helm-WebApp

## Project Information

**Project Name:** Yusuf WebApp

**Practical:** Helm Chart and Kubernetes Deployment

**Application:** Custom NGINX Web Application

**Chart Version:** 0.3.0

**Application Version:** v2

**Status:** Successfully deployed and upgraded on Minikube.
