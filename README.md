\# My WebApp - Helm Chart



\## Project Overview

This project demonstrates how to deploy an NGINX web application on Kubernetes using a custom Helm Chart.



\## Technologies Used

\- Kubernetes

\- Helm

\- Docker

\- Minikube

\- NGINX



\## Project Structure

```text

Yusuf-Helm-WebApp/

└── my-webapp/

&#x20;   ├── Chart.yaml

&#x20;   ├── values.yaml

&#x20;   └── templates/

&#x20;       ├── deployment.yaml

&#x20;       ├── service.yaml

&#x20;       └── ...

```



\## Prerequisites

\- Docker Desktop

\- Minikube

\- kubectl

\- Helm



\## Installation



Start Minikube:



```bash

minikube start --driver=docker

```



Install Helm Chart:



```bash

helm install my-webapp ./my-webapp

```



\## Verify Deployment



```bash

kubectl get deployments

kubectl get pods

kubectl get services

```



\## Upgrade Application



```bash

helm upgrade my-webapp ./my-webapp --set replicaCount=2

```



\## Access Application



```bash

kubectl port-forward service/my-webapp 8081:80

```



Open http://localhost:8081 in your browser.



\## Helm History



```bash

helm history my-webapp

```



\## Uninstall



```bash

helm uninstall my-webapp

```



\## Author

Yusuf Khayyat

