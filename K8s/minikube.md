minikube is local [[K8s|Kubernetes]], focusing on making it easy to learn and develop for Kubernetes.

All you need is Docker (or similarly compatible) container or a Virtual Machine environment, and Kubernetes is a single command away: `minikube start`

- [[#Installation]]
- [[#Start your cluster]]
- [[#Interact with your cluster]]

---
## Installation
The following script installs the stable, dpkg, for x86-64(Linux) machines 

```shell
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
```

---
## Start your cluster

From a terminal with administrator access (but not logged in as root), run:

```shell
minikube start
```

If minikube fails to start, see the [drivers page](https://minikube.sigs.k8s.io/docs/drivers/) for help setting up a compatible container or virtual-machine manager.

---
## Interact with your cluster

If you already have [[kubectl-setup|kubectl]] installed, you can now use it to access your shiny new cluster:

```shell
kubectl get po -A
```

Alternatively, minikube can download the appropriate version of kubectl and you should be able to use it like this:

```shell
minikube kubectl -- get po -A
```


You can also make your life easier by adding the following to your shell config: (for more details see: [[kubectl]])

```shell
alias kubectl="minikube kubectl --"
```


Initially, some services such as the storage-provisioner, may not yet be in a Running state. This is a normal condition during cluster bring-up, and will resolve itself momentarily. For additional insight into your cluster state, minikube bundles the Kubernetes Dashboard, allowing you to get easily acclimated to your new environment:

```shell
minikube dashboard
```

