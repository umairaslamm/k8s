# Working with kubectl

Install minikube
    `brew install minikube`

Start minikube
    `minikube start`

Check deployments `kubectl get deployments` (also tells the current namespace)

## Goals
Lets cover the different ways to create objects in Kuberentes - the variations of the create command, and the apply command.

`kubectl get namespaces`

Create a namespace to hold all the work and easily cleanup when not needed

`kubectl create namespace native-tools`

Let's switch to operate in the development namespace.

`kubectl config set-context --current --namespace=native-tools`

You can verify your current namespace by doing the following:

`kubectl config view --minify -o jsonpath='{..namespace}'`

or `kubectl get deployments` (also tells the current namespace)

### Different ways to create objects

Simplest way: `kubectl run helloworld --image karthequian/helloworld:latest`

Verify: `kubectl get pods`

Common way (from file): `kubectl create -f red.yaml`

List deployments: `kubectl get deployments`

Multiple files: `kubectl create -f blue.yaml -f green.yaml`

Whole directory: `kubectl create -f ./colors`

URL: `kubectl apply -f https://raw.githubusercontent.com/karthequian/kubernetesHelloworld/master/hello.yaml`

Wide output: `kubectl get deployments -o wide`

Remove namespace: `kubectl delete namespace native-tools`

Delete cluster: `minikube delete`