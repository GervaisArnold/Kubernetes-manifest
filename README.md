# Kubernetes Manifests

This repository contains Kubernetes manifests for deploying a sample web application on a Kubernetes cluster.

## Prerequisites

Before deploying the manifests, you need to ensure that the following prerequisites are met:

- A Kubernetes cluster is set up and running.
- `kubectl` command-line tool is installed and configured to communicate with the Kubernetes cluster.
- The Docker image for the web application is available on a container registry.

## Deployment

To deploy the web application, follow these steps:

1. Clone the repository:

```
git clone https://github.com/GervaisArnold/Kubernetes-manifests.git
cd Kubernetes-manifests
```

2. Replace the image name in the deployment manifest with your own Docker image:

```
sed -i 's/image: gervaisarnold\/sample-webapp/image: YOUR_DOCKER_IMAGE_NAME/g' deployment.yaml
```

3. Apply the manifests:

```
kubectl apply -f .
```

This will deploy the web application along with a service that exposes it to the internet.

## Accessing the Application

To access the application, you need to obtain the external IP address of the service. You can do this by running:

```
kubectl get svc sample-webapp
```

This will output the external IP address of the service.

You can now access the application by visiting the URL `http://<EXTERNAL_IP_ADDRESS>:8080` in your web browser.

## Cleaning Up

To remove the deployed resources, run:

```
kubectl delete -f .
```

This will delete the deployment and service for the web application.

## Contributing

If you have any improvements or suggestions, feel free to create a pull request or open an issue.
