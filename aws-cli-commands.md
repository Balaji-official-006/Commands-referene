# AWS CLI Commands for DevOps Engineers

This document contains commonly used AWS CLI commands for managing AWS resources such as EC2, S3, ECR, and EKS.
These commands are useful for DevOps engineers to automate infrastructure and perform cloud operations.

---

# 1. AWS CLI Configuration

## Configure AWS CLI

```bash
aws configure
```

You will be prompted to enter:

* AWS Access Key
* AWS Secret Access Key
* Default region
* Output format

Example:

```
AWS Access Key ID: ********
AWS Secret Access Key: ********
Default region name: us-east-1
Default output format: json
```

---

# 2. Check AWS CLI Version

```bash
aws --version
```

Example output:

```
aws-cli/2.x.x Python/3.x
```

---

# 3. List Available Regions

```bash
aws ec2 describe-regions
```

Displays all AWS regions available for deployment.

---

# 4. EC2 Commands

## List EC2 Instances

```bash
aws ec2 describe-instances
```

---

## Start EC2 Instance

```bash
aws ec2 start-instances --instance-ids i-1234567890abcdef0
```

---

## Stop EC2 Instance

```bash
aws ec2 stop-instances --instance-ids i-1234567890abcdef0
```

---

## Reboot EC2 Instance

```bash
aws ec2 reboot-instances --instance-ids i-1234567890abcdef0
```

---

# 5. S3 Commands

## List S3 Buckets

```bash
aws s3 ls
```

---

## Create S3 Bucket

```bash
aws s3 mb s3://my-devops-bucket
```

---

## Upload File to S3

```bash
aws s3 cp file.txt s3://my-devops-bucket/
```

---

## Download File from S3

```bash
aws s3 cp s3://my-devops-bucket/file.txt .
```

---

## Sync Local Folder to S3

```bash
aws s3 sync ./website s3://my-devops-bucket
```

---

# 6. IAM Commands

## List IAM Users

```bash
aws iam list-users
```

---

## List IAM Roles

```bash
aws iam list-roles
```

---

# 7. ECR Commands (Docker Registry)

## Login to ECR

```bash
aws ecr get-login-password \
--region us-east-1 | docker login \
--username AWS \
--password-stdin <account-id>.dkr.ecr.us-east-1.amazonaws.com
```

---

## List ECR Repositories

```bash
aws ecr describe-repositories
```

---

## Create ECR Repository

```bash
aws ecr create-repository --repository-name my-app
```

---

# 8. ECS Commands

## List ECS Clusters

```bash
aws ecs list-clusters
```

---

## List Services in Cluster

```bash
aws ecs list-services --cluster my-cluster
```

---

# 9. EKS Commands

## List EKS Clusters

```bash
aws eks list-clusters
```

---

## Describe EKS Cluster

```bash
aws eks describe-cluster --name my-demo-cluster
```

---

## Update kubeconfig

```bash
aws eks update-kubeconfig \
--region us-east-1 \
--name my-demo-cluster
```

This allows kubectl to communicate with the EKS cluster.

---

# 10. Useful DevOps Workflow Example

Example: Deploy application to EKS.

```
aws configure
aws eks update-kubeconfig --name my-demo-cluster
kubectl get nodes
kubectl apply -f deployment.yaml
kubectl get svc
```

---

# Conclusion

AWS CLI helps DevOps engineers automate cloud infrastructure and manage AWS services efficiently.

Common services managed using AWS CLI include:

* EC2
* S3
* IAM
* ECR
* ECS
* EKS

Maintaining AWS CLI command references helps improve operational efficiency and automation workflows.
