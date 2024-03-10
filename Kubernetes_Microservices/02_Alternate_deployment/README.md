# Alternate Universe!

Ref: [Two K8s Deployments, One Service, and a Persistent Volume](https://medium.com/nerd-for-tech/two-k8s-deployments-one-service-and-a-persistent-volume-c007e22ac303)

## Step 1: Create deployment

`kubectl apply -f wishlist-deployment-alternate.yaml`

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

`kubectl delete -f wishlist-deployment-alternate.yaml`

