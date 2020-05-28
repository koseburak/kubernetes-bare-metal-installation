# Installation the kubernetes cluster

install the kubernetes cluster using Ansible, Vagrant and Virtualbox

## requiremenst to installation

* [Docker](https://docs.docker.com/install/) - for install Docker Desktop
* [Virtualbox](https://www.virtualbox.org/wiki/Downloads) - for install Virtualbox
* [Vagrant](https://www.vagrantup.com/docs/installation/) - for install Vagrant
* [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) - for install kubectl client

## installation and configuration

Run this command to clone the git repo of project
```
$ git clone https://github.com/koseburak/hello-py.git
```

Run this command to start installation in the same directory as Vagrantfile
```
$ vagrant up
```

Copy created kube "config" file into the "$HOME/.kube/" folder to manage provisioned K8s cluster
 ```
$ cp ansible-playbooks/config ~/.kube/config
```

run this command and see nodes of your kubernetes cluster like the below;
```
$ kubectl get nodes -o wide
![alt text](https://github.com/koseburak/kubernetes/feature/kubernetes-install/01-kubernetes-install/images/01-get-nodes.png?raw=true)
```
