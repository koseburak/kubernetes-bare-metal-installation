# Installation the kubernetes dashboard

install the kubernetes dashboard to manage and monitor the cluster from web ui

## Installation

run this command to install kubernetes dashboard
```
$ kubectl apply -f deploy.yaml
```

run this command to get the token required in login from web ui for only default namespace permission
```
$ kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep kubernetes-dashboard | awk '{print $1}')
```

or

run this command to create cluster-admin user
```
$ kubectl apply -f cluster-admin-account.yaml
```

run this command to get the token required in login from web ui for cluster-admin permissions
```
$ kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')
```

run this command and start the proxy tunnel to access dashboard web ui from local browser
 ```
$ kubectl proxy
```

you can access your kubernetes dashboard with the below url address via your local browser
```
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
```
