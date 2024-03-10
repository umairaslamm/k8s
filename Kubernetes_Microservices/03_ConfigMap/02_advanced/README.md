## Setup
Create the deployment by running 

`kubectl apply -f wishlist-deployment-configmap-advanced.yaml`

Switch namespace

`kubectl config set-context --current --namespace=configmap-advanced`

## 2

Get pods info

`kubectl get pods`
```
└─(17:24:41 on main ✭)──> kubectl get pods                                                                                                                                                                                                    ──(Sun,Mar10)─┘
NAME                                   READY   STATUS    RESTARTS   AGE
wishlist-deployment-69bc4c4fcd-rmvfr   3/3     Running   0          50s
wishlist-deployment-69bc4c4fcd-shrgk   3/3     Running   0          50s
wishlist-deployment-69bc4c4fcd-vfslt   3/3     Running   0          50s
```
Exec into the wishlist pod with a command like:

`kubectl exec -it wishlist-deployment-69bc4c4fcd-rmvfr -c wishlist -- /bin/bash`

To look find your env variable run:

`cat /var/lib/wishlist/log.properties`

## Cleanup

`kubectl delete -f wishlist-deployment-configmap-advanced.yaml`