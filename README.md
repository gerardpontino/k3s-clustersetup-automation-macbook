# Automate K3s Cluster Setup on Multipass using Ansible (MacBook)

This Ansible playbook automates the creation of a lightweight K3s Kubernetes cluster on Multipass using your MacBook.
It provisions one master node and three worker nodes, installs K3s, and configures your local kubeconfig automatically.

This setup is perfect if you want to:

Practice Kubernetes use cases or certification labs (CKA, CKAD, CKS)

Quickly spin up a fresh K3s environment for testing

Tear down and recreate the cluster anytime by simply rerunning the playbook

| Node Name       | vCPU | RAM | Disk | Role   |
| --------------- | ---- | --- | ---- | ------ |
| `k3s-master`    | 2    | 4GB | 20GB | Master |
| `k3s-worker-01` | 1    | 1GB | 4GB  | Worker |
| `k3s-worker-02` | 1    | 1GB | 4GB  | Worker |
| `k3s-worker-03` | 1    | 1GB | 4GB  | Worker |


### Prerequisites

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

### Clone the repository

git clone https://github.com/gerardpontino/k3s-clustersetup-automation-macbook.git
cd <your-repo-name>

### Update configuration (optional)

If you want to modify node specs, names, or counts, update the variables in your playbooks or inventory file.

### Run the Ansible playbook

```bash
ansible-playbook -i inventory.yml k3s_provision.yaml
```

This playbook performs the following steps automatically:

- Deletes any existing k3s-master or k3s-worker-* instances (for a clean start)

- Creates one master and three worker nodes on Multipass

- Installs K3s on the master and joins worker nodes to the cluster

- Retrieves and updates your local kubeconfig file (~/.kube/config)

- Displays your K3s cluster node information

You can rerun this playbook anytime to delete and rebuild your cluster — perfect for a fresh lab environment or repeated practice runs.

### Accessing the Cluster

After the setup finishes, you can check your cluster status using:

```bash
kubectl get nodes
```

```bash
NAME            STATUS   ROLES                  AGE     VERSION
k3s-master      Ready    control-plane,master   2m      v1.29.0+k3s1
k3s-worker-01   Ready    <none>                 1m      v1.29.0+k3s1
k3s-worker-02   Ready    <none>                 1m      v1.29.0+k3s1
k3s-worker-03   Ready    <none>                 1m      v1.29.0+k3s1
```






