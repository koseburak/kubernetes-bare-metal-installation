# Deployment Nginx Ingress Controller

deployment and load balancing configuration using nginx of a simple web application

## Installation and Configuration

run this command to deploy web application;
```
$ kubectl apply -f deploy-apps.yaml
```

run this command to create a secret with a SSL crtificate and key;
```
$ kubectl apply -f secret.yaml
```

run this command to create ingress for web application load balancer configuration;
```
$ kubectl apply -f ingress.yaml
```

add new sub-domain addresses in your local /etc/hosts file like the below;
```
192.168.50.50   example.com dotnet.example.com
192.168.50.51   example.com dotnet.example.com
```

you can access the web apps via the below url addresses from the local browser;
```
https://dotnet.example.com/
https://dotnet.example.com/api/repository
```
