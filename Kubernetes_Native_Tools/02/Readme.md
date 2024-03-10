# Working with kubectl

Start minikube
    `minikube start`

## Goals
Real world example using namespaces

`kubectl get namespaces`

### Create multiple namespaces with their own deployments

`kubectl apply -f sample-infrastructure.yaml`

`kubectl get pods`

`kubectl get namespaces`

`kubectl get pods -n cart`

`kubectl get pods --all-namespaces`

### Searching, Sorting & Filtering apps

`kubectl get pods -o wide --all-namespaces`

`kubectl get pods -o json --all-namespaces`

`kubectl get pods --sort-by=.metadata.name --all-namespaces`

`kubectl get pods -o=jsonpath="{..image}" -l env=staging -n cart`

all container images running

`kubectl get pods --all-namespaces -o jsonpath="{.items[*].spec.containers[*].image}"` 


### Deleting strategies for apps

`kubectl get pods -n cart`

`kubectl delete pods -n cart --all`

`kubectl get pods -n cart -w`

`kubectl delete pods -n auth --all --grace-period=0 --force`

`kubectl get pods -l env=staging -n social`

`kubectl get pods -n social`

`kubectl delete  pods -l env=staging -n social`

`kubectl delete -f sample-infrastructure.yaml`

