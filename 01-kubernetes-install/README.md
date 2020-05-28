# Installation the kubernetes cluster

install the kubernetes cluster using Ansible, Vagrant and Virtualbox

## Installation

* [Docker](https://docs.docker.com/install/) - for install Docker Desktop
* [Virtualbox](https://www.virtualbox.org/wiki/Downloads) - for install Virtualbox
* [Vagrant](https://www.vagrantup.com/docs/installation/) - for install Vagrant
* [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) - for install kubectl client

## Preparing environment

Clone the git repository and install the K8s cluster

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
