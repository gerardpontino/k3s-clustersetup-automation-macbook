# Automate K3s Cluster Setup on Multipass using Ansible (MacBook)

This project automates the provisioning of a lightweight K3s Kubernetes cluster using Multipass and Ansible on macOS.
It creates one master node and 3 worker nodes, installs K3s, and joins them into a single cluster — fully automated from start to finish.

This setup is perfect for learning, testing, and experimentation.
If you want to:

Try out Kubernetes use cases or practice scenarios,

Run certification practice tests (CKA/CKAD/CKS), or

Quickly spin up a fresh environment for hands-on work —

you can simply run the playbook again to delete and recreate your entire cluster from scratch.

| Node Name       | vCPU | RAM | Disk | Role   |
| --------------- | ---- | --- | ---- | ------ |
| `k3s-master`    | 2    | 4GB | 20GB | Master |
| `k3s-worker-01` | 1    | 1GB | 4GB  | Worker |
| `k3s-worker-02` | 1    | 1GB | 4GB  | Worker |
| `k3s-worker-03` | 1    | 1GB | 4GB  | Worker |

###Prerequisites

Before you begin, make sure you have the following installed on your MacBook:

```bash
brew install --cask multipass
```

```bash
brew install ansible
```

```bash
brew install kubectl
```

###Clone the repository

git clone https://github.com/gerardpontino/k3s-clustersetup-automation-macbook.git
cd <your-repo-name>





