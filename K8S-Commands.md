# Kubernetes Commands for DevOps Engineers

This document contains commonly used Kubernetes commands using **kubectl** and **eksctl**.
These commands help manage Kubernetes clusters, deploy applications, and troubleshoot issues.

---

# 1. EKS Cluster Management (eksctl)

## Create an EKS Cluster

```bash
eksctl create cluster \
--name my-demo-cluster \
--region us-east-1 \
--nodegroup-name standard-nodes \
--node-type t3.small \
--nodes 2 \
--managed
```

Creates a Kubernetes cluster on AWS using managed node groups.

---

## List EKS Clusters

```bash
eksctl get cluster
```

Displays all EKS clusters in your AWS account.

---

## Delete an EKS Cluster

```bash
eksctl delete cluster --name my-demo-cluster --region us-east-1
```

Deletes the EKS cluster and associated resources.

---

## Create Node Group

```bash
eksctl create nodegroup \
--cluster my-demo-cluster \
--name my-nodes \
--node-type t3.small \
--nodes 2
```

Adds worker nodes to the cluster.

---

# 2. Configure kubectl for EKS

Update kubeconfig to access the EKS cluster.

```bash
aws eks update-kubeconfig --region us-east-1 --name my-demo-cluster
```

Verify cluster connectivity:

```bash
kubectl get nodes
```

---

# 3. Cluster Information

## Check Cluster Info

```bash
kubectl cluster-info
```

Displays control plane information.

---

## Get Nodes

```bash
kubectl get nodes
```

Lists all worker nodes in the cluster.

---

# 4. Pod Management

## List Pods

```bash
kubectl get pods
```

---

## List Pods in All Namespaces

```bash
kubectl get pods -A
```

---

## Describe Pod

```bash
kubectl describe pod <pod-name>
```

Shows detailed pod information including events.

---

## View Pod Logs

```bash
kubectl logs <pod-name>
```

Useful for troubleshooting application issues.

---

## Execute Command Inside Pod

```bash
kubectl exec -it <pod-name> -- /bin/bash
```

Allows you to access the container shell.

---

# 5. Deployment Management

## Create Deployment

```bash
kubectl create deployment nginx --image=nginx
```

---

## List Deployments

```bash
kubectl get deployments
```

---

## Scale Deployment

```bash
kubectl scale deployment nginx --replicas=3
```

---

## Delete Deployment

```bash
kubectl delete deployment nginx
```

---

# 6. Services

## List Services

```bash
kubectl get svc
```

---

## Expose Deployment

```bash
kubectl expose deployment nginx \
--type=LoadBalancer \
--port=80
```

Creates an external load balancer.

---

# 7. Apply YAML Configuration

Deploy resources using YAML files.

```bash
kubectl apply -f deployment.yaml
```

Delete resources:

```bash
kubectl delete -f deployment.yaml
```

---

# 8. Namespace Management

## List Namespaces

```bash
kubectl get namespaces
```

---

## Create Namespace

```bash
kubectl create namespace dev
```

---

## Run Pod in Namespace

```bash
kubectl get pods -n dev
```

---

# 9. Troubleshooting Commands

## Check Cluster Events

```bash
kubectl get events
```

---

## Check Resource Usage

```bash
kubectl top nodes
```

```bash
kubectl top pods
```

---

# 10. Useful DevOps Workflow

Example deployment workflow:

```bash
kubectl apply -f deployment.yaml
kubectl get pods
kubectl get svc
kubectl describe pod <pod-name>
kubectl logs <pod-name>
```

---

# Conclusion

Kubernetes commands help DevOps engineers manage clusters, deploy applications, and troubleshoot issues efficiently.

Key tools used:

* **kubectl** → Kubernetes cluster management
* **eksctl** → Create and manage Amazon EKS clusters
* **AWS CLI** → Configure cluster access

Maintaining command references improves operational efficiency and DevOps productivity.
