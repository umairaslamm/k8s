# Deploying our application to Kubernetes

## Objectives:
1. Take a look at wishlist-deployment.yaml
3. Deploy our application into kubernetes and verify we can see our API's working.


## Step 1: Create deployment

`kubectl create -f wishlist-deployment.yaml`

Switch namespace

`kubectl config set-context --current --namespace=microservices`

## Step 2: Verify deployment

To verify that the deployment is online:

`kubectl get deployments`

To verify that the replica sets are running:

`kubectl get rs`

To verify that the pods are running:

`kubectl get pods`

To see the services:

`kubectl get services`

To interact with your API's in the minikube environment:

`minikube service wishlist-service -n microservices`

## Step 3: Cleanup

`kubectl delete -f wishlist-deployment.yaml`
