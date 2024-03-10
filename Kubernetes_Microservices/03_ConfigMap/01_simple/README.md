## Setup
Create the deployment by running 

`kubectl apply -f wishlist-deployment-configmap-simple.yaml`

Switch namespace

`kubectl config set-context --current --namespace=configmap-simple`


## 1

Get pods info

`kubectl get pods`
```
(17:06:55 on main ✭)──> kubectl get pods 

NAME                                   READY   STATUS    RESTARTS   AGE
wishlist-deployment-8487c4555c-msbtx   3/3     Running   0          50s
wishlist-deployment-8487c4555c-vd6hp   3/3     Running   0          50s
wishlist-deployment-8487c4555c-wgmcg   3/3     Running   0          50s
```
Exec into the auth container in the wishlist pod with a command like:

`kubectl exec -it wishlist-<podid> -c wishlist bash`

Deprecated as of 1.28

`kubectl exec -it wishlist-deployment-8487c4555c-msbtx -c wishlist bash`

Current way of exec

`kubectl exec -it wishlist-deployment-8487c4555c-msbtx -c wishlist -- /bin/bash`

To look find your env variable run:

`env | grep LOG_LEVEL`

## Cleanup

`kubectl delete -f wishlist-deployment-configmap-simple.yaml`
