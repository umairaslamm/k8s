# [Liveness Probes](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#container-probes)

Liveness Probes are often used in deployments with many containers to help with startup and container running states.

## Setup

`kubectl apply -f wishlist-deployment-liveness.yaml`

`kubectl config set-context --current --namespace=liveness-probes`

To see if our probes are running:

`kubectl get pods`

`kubectl describe deployment wishlist-deployment`
