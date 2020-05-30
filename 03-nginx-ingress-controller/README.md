# Installation the nginx ingress controller

install the nginx ingress controller using helm3 in kubernetes cluster

## Requiremenst to installation

* [helm3](https://helm.sh/docs/intro/install/) - for install Helm 3

run this command to check installed helm repositories
```
$ helm repo list
```

If no stable repo is defined, run the below command to add stable helm repository
```
$ helm repo add stable https://kubernetes-charts.storage.googleapis.com/
```

## Installation and Configuration

run this command to create ingress-nginx namespace
```
$ kubectl create namespace ingress-nginx
```

run this command to install nginx ingress controller in kubernetes cluster
```
$ helm install nginx-ingress stable/nginx-ingress --version 1.38.0 -n ingress-nginx \
    --set controller.kind=DaemonSet \
    --set controller.hostNetwork=true \
    --set controller.daemonset.useHostPort=true \
    --set controller.service.enabled=false
```

you will see output like the below;
```
NAME: nginx-ingress
LAST DEPLOYED: Sat May 30 20:47:24 2020
NAMESPACE: ingress-nginx
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
The nginx-ingress controller has been installed.
It may take a few minutes for the LoadBalancer IP to be available.
You can watch the status by running 'kubectl --namespace ingress-nginx get services -o wide -w nginx-ingress-controller'

An example Ingress that makes use of the controller:

  apiVersion: extensions/v1beta1
  kind: Ingress
  metadata:
    annotations:
      kubernetes.io/ingress.class: nginx
    name: example
    namespace: foo
  spec:
    rules:
      - host: www.example.com
        http:
          paths:
            - backend:
                serviceName: exampleService
                servicePort: 80
              path: /
    # This section is only required if TLS is to be enabled for the Ingress
    tls:
        - hosts:
            - www.example.com
          secretName: example-tls

If TLS is enabled for the Ingress, a Secret containing the certificate and key must also be provided:

  apiVersion: v1
  kind: Secret
  metadata:
    name: example-tls
    namespace: foo
  data:
    tls.crt: <base64 encoded cert>
    tls.key: <base64 encoded key>
  type: kubernetes.io/tls

```

add kubernetes node ip addresses in your local /etc/hosts file like the below;
```
192.168.50.50   example.com
192.168.50.51   example.com
```

try to access http://example.com/ from browser and will see default backend response like the below;
```
default backend - 404
```

you can see and try an nginx example from [here](example#section)...
