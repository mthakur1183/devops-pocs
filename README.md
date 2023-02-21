# K8-deployment

This project uses Kubernetes and Minikube to deploy a simple web application and a MongoDB database on a local cluster. The web application is built using Node.js, and uses the MongoDB database to store data. The project is intended to demonstrate a basic deployment pipeline on a MiniKube cluster for a web application and database .

Prerequisites
Before running this project, ensure you have the following installed:

Docker
Kubectl
Minikube

Getting Started
To deploy the web application and MongoDB database, follow these steps:

1.Start the Minikube cluster:
Minikube start

2.Apply the Kubernetes manifests to deploy the web application and MongoDB:
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f webapp.yaml

3.Verify the deployment:
minikube service webapp-service

Clean Up
To remove the deployment, run:
kubectl delete -f app.yaml
kubectl delete -f mongo.yaml

To stop the Minikube cluster, run:
minikube stop

Architecture
The following components are deployed in this project:

A single MongoDB with 1 replica set.
A single instance of the web application, with 1 replica and a service to expose it to the cluster.

Troubleshooting
If the web application fails to start, check the logs of the pods:
kubectl logs <pod-name>

