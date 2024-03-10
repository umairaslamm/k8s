# Secrets!


## Goals
1. Create a secret that can be referenced by the application via env variables
2. Create a secret that can be referenced by the application via a volume mounted file

## Setup

Create the deployment by running 

`kubectl apply -f wishlist-deployment-secret.yaml`

Switch namespace

`kubectl config set-context --current --namespace=secrets`

decode secret

`echo c2VydmVyPTEyNy4wLjAuMTt1aWQ9cm9vdDtwd2Q9MTIzNDU7ZGF0YWJhc2U9dGVzdA== | base64 --decode`

## Goal 1

`kubectl get pod` 

```
└─(17:59:54 on main ✭)──> kubectl get pods                                                                                                                                                                                                    ──(Sun,Mar10)─┘
NAME                                   READY   STATUS    RESTARTS   AGE
wishlist-deployment-5f746bddcd-bk462   3/3     Running   0          2m56s
wishlist-deployment-5f746bddcd-d4mwn   3/3     Running   0          2m56s
wishlist-deployment-5f746bddcd-wnt5c   3/3     Running   0          2m56s
```

`kubectl exec -it wishlist-deployment-5f746bddcd-bk462 -c auth -- /bin/bash`

To look find your env variable run:

`env | grep MYSQL_CONNECTION_STRING`


## Goal 2

To look find your env variable run:

`cat /etc/mysql/connection-string`


## Cleanup

`kubectl delete -f wishlist-deployment-secret.yaml`
